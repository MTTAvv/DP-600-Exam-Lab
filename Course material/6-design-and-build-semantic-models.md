# 6 – Design and build semantic models

## 6.1 Semantic model storage modes (exam topic)

**Storage modes at a glance**

The storage mode defines where the data lives and how queries are answered. It is set per table.

| Mode        | How it works                                                                                            | Performance and freshness                                                                                                                 | Best for / watch out                                                                                                  |
| ----------- | ------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| Import      | Data is copied into the in-memory VertiPaq engine.                                                      | Fastest queries. Only as fresh as the last refresh (up to 8 scheduled refreshes a day on shared capacity, 48 on Premium/Fabric capacity). | Small to medium data, complex DAX, any source. Limited by model size per SKU; incremental refresh helps large tables. |
| DirectQuery | No data stored. Every visual sends a query to the source.                                               | Real-time data. Speed depends on the source and is usually the slowest.                                                                   | Very large data or live requirements. Some DAX and Power Query features are limited; adds load on the source.         |
| Dual        | The table acts as Import or DirectQuery depending on the query.                                         | Fast when the query can be answered from cache.                                                                                           | Dimension tables related to a DirectQuery fact table (avoids limited relationships). Only in composite models.        |
| Direct Lake | Reads Delta/Parquet files from OneLake straight into memory, column by column, on demand. No data copy. | Close to Import speed with near-real-time freshness: a refresh only reframes to the latest Delta version.                                 | Large Lakehouse/Warehouse data in Fabric. Constrained by SKU guardrails.                                              |

**Direct Lake in detail**

  - **Refresh = reframing:** a metadata-only operation that points the model at the latest Delta table version. It can run automatically when the data changes or be triggered at the end of a pipeline or notebook.

  - **Two variants:** Direct Lake on OneLake (one or more Fabric sources, never falls back to DirectQuery, Import tables can be added) and Direct Lake on SQL endpoint (a single source, can fall back to DirectQuery).

  - **Guardrails per SKU:** rows per table, Parquet files, row groups, memory and model size. Example F64: 1,500 million rows per table, 5,000 files, 25 GB max memory. Smaller SKUs have lower limits.

  - **When a guardrail is exceeded:** on SQL endpoint the model falls back to DirectQuery (slow). On OneLake, refresh fails and the model cannot be queried. The DirectLakeBehavior property controls fallback.

  - **Other fallback triggers (SQL endpoint variant):** RLS or column-level security defined on the SQL analytics endpoint, and SQL views. Define RLS in the semantic model instead.

  - **Keep it fast:** V-Order, OPTIMIZE and VACUUM, avoid many small files, use narrow data types.

**Composite models and hybrid tables**

  - **Composite model:** one model mixing storage modes and/or sources.

  - **Regular vs limited relationships:** aggregation hits need regular relationships. From the same source, regular means many-side Dual → one-side Dual, Import → Import or Dual, DirectQuery → DirectQuery or Dual. Across sources, a relationship is regular only if both tables are Import. Many-to-many is always limited.

  - **Hybrid table:** Import for historical partitions plus a DirectQuery partition for the latest data (incremental refresh with real-time data). Premium/Fabric capacity only.

**Aggregations**

**User-defined aggregations**

  - **Purpose:** speed up interactive queries on huge DirectQuery tables. Data is pre-summarized at a higher granularity and cached in memory. Users still query the detail table. Power BI redirects to the aggregation table when it can (hit) and goes to the source when it can't (miss).

  - **Typical design:** detail (fact) table in DirectQuery; aggregation table in Import (best performance) and hidden; related dimension tables in Dual.

  - **Setup:** in Power BI Desktop, right-click the aggregation table → Manage aggregations. For each column choose Summarization (GroupBy, Sum, Min, Max, Count, Count table rows), Detail table and Detail column.

Two techniques, which can be combined:

| Technique                | Used with                                                                                                        | GroupBy entries                                  |
| ------------------------ | ---------------------------------------------------------------------------------------------------------------- | ------------------------------------------------ |
| Based on relationships   | Star/snowflake schemas (data warehouses). Dimensions filter the aggregation table through regular relationships. | Optional (except for DISTINCTCOUNT)              |
| Based on GroupBy columns | Big-data models with denormalized fact tables and no relationships.                                              | Required, otherwise the aggregation is never hit |

**Rules to remember**

  - The detail table must be DirectQuery.

  - The aggregation column must have the same data type as the detail column, except for Count and Count table rows.

  - No chained aggregations (A → B → C) and no duplicate aggregations.

  - Once a table is set to Import, it cannot be switched back.

  - **Precedence:** with several aggregation tables, the one with the higher precedence value is evaluated first.

  - **RLS** must filter both the aggregation and the detail table. A filter on the aggregation table only is not allowed.

  - Check hits and misses with SQL Profiler (Aggregate Table Rewrite Query event). Import aggregation tables are ignored when the source uses single sign-on.

**Automatic aggregations**

  - Premium/Fabric feature, enabled in the semantic model settings, for DirectQuery models.

  - Power BI learns from the query history and creates and maintains in-memory aggregation tables for you. Less control, no manual design.

  - **User-defined vs automatic:** user-defined = you design and maintain; automatic = ML-managed.

**Exam scenario: which storage mode?**

**Question:** Workspace1 is on an F64 capacity and contains a lakehouse with one billion historical sales rows, plus up to 10,000 new or updated rows every 15 minutes. You need the best report performance with near-real-time reporting.

**Answer: Direct Lake.**

  - **Import:** fast, but data is stale between refreshes, and refreshing one billion rows is heavy. Not near-real-time.

  - **DirectQuery:** real-time, but slow on a billion rows.

  - **Dual:** a table-level mode for composite models, not a solution for freshness.

  - **Direct Lake:** Import-like speed, reads the lakehouse Delta tables directly, and reframing picks up the new rows. F64 allows 1.5 billion rows per table, so one billion fits (monitor growth).

**Decision rules**

  - Fabric lakehouse/warehouse + best performance + near-real-time → **Direct Lake**.

  - Best performance, freshness not critical → **Import**.

  - Live data from a source outside Fabric, or must query the source in real time → **DirectQuery** (add aggregations for speed).

  - Historical data fast plus latest data live → **hybrid table** (incremental refresh with a DirectQuery partition).

  - Dimension related to a DirectQuery fact or an Import aggregation table → **Dual**.

  - Slow dashboard on a huge DirectQuery table → **aggregations** (user-defined, or automatic on Premium/Fabric).

  - Direct Lake model slow or falling back → check guardrails: run OPTIMIZE/VACUUM, fix RLS location, or scale up the SKU.

## 6.2 DAX essentials for the exam

**Core functions**

| Function | Purpose |
| --- | --- |
| `CALCULATE(<measure>, <filters>)` | Evaluates an expression in a **modified filter context**. The most important DAX function. |
| `FILTER(table, condition)` | Iterates a table row by row and returns the rows that satisfy the condition. |
| `ALL`, `ALLEXCEPT`, `REMOVEFILTERS` | Remove filters. |
| `KEEPFILTERS` | Adds a filter **without replacing** the existing one on the same column. |
| `SUMX`, `AVERAGEX`, `COUNTROWS` | Iterators and row counting. |
| `VAR ... RETURN` | Variables: calculated once, reused, easier to read and faster. |
| `SELECTEDVALUE`, `HASONEVALUE` | Read the single value selected in the filter context. |
| `USERPRINCIPALNAME()` | Current user (dynamic RLS). |

**Time intelligence** (needs a proper date table marked as date table)

```dax
Sales LY  = CALCULATE([Total Sales], SAMEPERIODLASTYEAR('Date'[Date]))
Sales MTD = CALCULATE([Total Sales], DATESMTD('Date'[Date]))
Sales YTD = CALCULATE([Total Sales], DATESYTD('Date'[Date]))
```

**Context transition:** calling a measure (or `CALCULATE`) inside an iterator such as `FILTER` or `SUMX` turns each row into a filter context, which is expensive on large tables.

**Average of one question:** isolate the key first, then average in that context.

```dax
Avg Overall Satisfaction =
VAR _key = CALCULATE(MAX('Question'[QuestionKey]), 'Question'[Question Title] = "Overall Satisfaction")
RETURN CALCULATE(AVERAGE('Response'[Score]), 'Response'[QuestionKey] = _key)
```

## 6.3 DAX queries (EVALUATE) and the XMLA endpoint

A **DAX query** returns a table. It is run from **DAX query view** in Power BI Desktop, from DAX Studio, SSMS, or any client over the **XMLA endpoint**.

```dax
DEFINE
    VAR _SalesSince = DATE(2023, 12, 1)
EVALUATE
    FILTER(Store, Store[OpenDate] >= _SalesSince)
```

```dax
EVALUATE
VAR _LYSales = CALCULATE([Total Sales], SAMEPERIODLASTYEAR('Orders'[Order Date]))
RETURN { _LYSales }
```

  - Every DAX query that returns data **starts with `EVALUATE`**.
  - `DEFINE` (optional) declares query-scoped variables, measures and columns before `EVALUATE`.
  - `ORDER BY` goes after the EVALUATE expression.
  - `{ value }` returns a one-row table; `SUMMARIZECOLUMNS` is the usual way to group and aggregate.
  - To run queries through XMLA the capacity must allow it (**XMLA endpoint = Read Write or Read Only** in the capacity settings, and the tenant setting enabled).

## 6.4 Calculation groups

A **calculation group** is a set of **calculation items** that reuse the same logic for many measures (for example one group *Time Intelligence* with items Current, MTD, YTD, Prior Year), avoiding dozens of duplicated measures.

```dax
-- Calculation item "MTD" in the group "Time Intelligence"
CALCULATE(SELECTEDMEASURE(), DATESMTD('Date'[Date]))
```

  - `SELECTEDMEASURE()` is the measure the user (or the visual) is currently evaluating; the calculation item wraps it in `CALCULATE` with a time-intelligence function that changes the date context.
  - Calculation groups are created with **Tabular Editor** (connected to the model through the XMLA endpoint, also for Direct Lake models). Power BI Desktop has a calculation group feature in the model view, but **Tabular Editor** is the tool the exam expects, together with other advanced changes.
  - DAX Studio is for querying and tuning, not for creating calculation groups.
  - When a model contains calculation groups, **implicit measures are disabled**.

## 6.5 Model hygiene: implicit measures, Summarize By, Python visuals

- **Implicit measures** are created automatically when a user drags a numeric column into a visual (SUM, average...). To **prevent report creators from using them**, set the model property *Discourage implicit measures* (Power BI Desktop or **Tabular Editor**). Calculation groups also turn them off.
  - Key columns (CustomerKey, ProductKey...) should have **Summarize By = None** so that they are not summed. To find them across the whole model, use the **Best Practice Analyzer** in Tabular Editor (rules scan every column at once); to change many columns at once use a **C# script** in Tabular Editor.
  - **Model view** in Power BI Desktop shows the relationship diagram. Build a diagram with only one table and its related tables by selecting it and using *Add related tables*.
  - **Python/R visuals** receive **grouped and de-duplicated** rows: identical rows are collapsed. To get every row, add a **unique field** (such as an index column) to each row.
  - **Display folders, perspectives, hidden fields** reduce clutter for report creators; **PBIP** projects make TMDL/JSON definitions editable in VS Code and Git friendly.
  - Dynamic RLS must be tested for a **specific user**, see section 1.7.

## 6.6 Dynamic format strings

A **dynamic format string** is a DAX expression, attached to a measure, that returns the **format string** to use depending on context (for example the currency chosen in a slicer).

```dax
-- Format string expression of the measure TotalSalesAmount
SWITCH(SELECTEDVALUE('Currency'[Code]),
       "EUR", "#,0.00 €",
       "USD", "$#,0.00",
       "#,0.00")
```

  - The measure keeps its numeric type, so it can still be aggregated and sorted; only the display changes.
  - A **field parameter** lets users switch *which fields* a visual shows. A **linguistic schema** is for Q&A natural language. `WINDOW` is a window function and does not format values.
  - Calculation groups can also change the format string of the measures they modify.

