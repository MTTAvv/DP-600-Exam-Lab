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
