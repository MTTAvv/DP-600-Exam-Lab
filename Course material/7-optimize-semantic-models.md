# 7 – Optimize semantic models

## 7.1 Find the slow part: Performance analyzer, DAX Studio and Server Timings

**Workflow to diagnose a slow report**

  1. In **Power BI Desktop**, open **Performance analyzer**, start recording, refresh the visuals (or interact with the page).
  2. The result lists each visual with its **duration**, split into *DAX query*, *Visual display* and *Other* (waiting). Sort by duration (descending) and find the slowest visual.
  3. **Copy the query** of that visual (to the clipboard or to DAX Studio).
  4. In **DAX Studio**, enable **Query Timings** and **Server Timings**, and run the query.
  5. Read **Server Timings**: the time is split between the **formula engine (FE)** (single-threaded, evaluates DAX) and the **storage engine (SE)** (multi-threaded, scans data). A high FE share points to a DAX/iterator problem; a high SE share points to model size or columns scanned.

**Other facts**

  - Visuals on a page run queries **in parallel** and compete for resources: when one visual is slow because of waiting, reducing the **number of visuals** on the page cuts the total time.
  - Changing the visual type, enabling automatic page refresh, or similar tweaks do not reduce DAX query time.

## 7.2 Model size and memory: VertiPaq Analyzer and DMVs

- **VertiPaq Analyzer** (in DAX Studio or Tabular Editor) shows, for every table and column, size in memory, cardinality and encoding. Use it to find big columns.
  - **DMVs** query the engine from SSMS or DAX Studio: `$SYSTEM.DISCOVER_STORAGE_TABLE_COLUMNS` and `DISCOVER_STORAGE_TABLE_COLUMN_SEGMENTS` show which columns are **resident in memory** (also for Direct Lake, to see which columns queries load). `DISCOVER_MEMORYGRANT` is about memory grants of running queries, not columns.
  - **Analyze in Excel** is a way to browse the model, not a diagnostic tool.

**Reduce the size of an Import model**

  - High **cardinality** columns compress badly. Split a **datetime** column into separate **date** and **time** columns (or keep only the date).
  - Replace calculated columns with **measures** (measures are computed at query time and store nothing).
  - Remove columns that are not used; avoid text keys; use integer surrogate keys.
  - Use the right data types and **disable Auto date/time** tables.

## 7.3 DAX performance patterns

| Slower | Faster | Why |
| --- | --- | --- |
| `FILTER(table, [Measure] > x)` or a nested `CALCULATE` inside `FILTER` | A column predicate `CALCULATE(..., KEEPFILTERS(Table[Col] > x))` | `FILTER` iterates row by row; a nested CALCULATE triggers a **context transition for every row**. Column predicates are optimized to the storage engine. |
| `COUNTROWS(RELATEDTABLE(T)) > 0` | `NOT ISEMPTY(RELATEDTABLE(T))` | `ISEMPTY` can stop at the first row instead of counting all rows. |
| Repeating the same expression | `VAR` | Calculated once. |

**Notes**

  - `ISEMPTY(...)` returns TRUE when there are **no rows**, which is the *opposite* of an existence test; use `NOT ISEMPTY(...)` to test that rows exist.
  - `COUNTROWS(...) >= 0` is always true (a count is never negative), so it changes the logic of the query.
  - `KEEPFILTERS` keeps the existing filter on a column and intersects it with the new one, instead of replacing it.

## 7.4 Aggregations, incremental refresh, scale-out and Direct Lake behaviour

**DirectQuery on large data**

  - **Aggregations** (user-defined or automatic) answer most queries from a small pre-aggregated table. Both help all pages of a report; **query caching** only applies to Import-style models and **OneLake integration** does not speed up DirectQuery queries.

**Incremental refresh**

  - Needs **query folding**, so that the date range filter is sent to the source and only the changed partitions are read.
  - File sources (for example CSV in OneLake) **do not fold**, so each partition reads all the data and the refresh is slow or fails. Fix: load the files into a lakehouse/warehouse table and base the model on it.
  - Setting *Only refresh complete days* or the type of the partition column does not cause a long-running refresh by itself.

**Query scale-out**

  - Spreads read queries over read-only replicas of a semantic model on a Premium/Fabric capacity.
  - Requires the model storage format **Large semantic model storage format**: enable it **first**, at semantic model level, then enable scale-out.

**Direct Lake behaviour and fallback**

  - Setting **Direct Lake Behavior** (model property, edited with Tabular Editor through XMLA): *Automatic* (default, falls back to DirectQuery when needed), *Direct Lake only* (never falls back; queries fail instead), *DirectQuery only*.
  - To guarantee queries always use Direct Lake → **Direct Lake Behavior = Direct Lake only**.
  - Typical fallback reasons: SQL-level security (RLS) on the SQL endpoint, views, the data exceeds the SKU guardrails.
  - With a custom Direct Lake model that uses the warehouse's RLS, queries on the secured tables run in **DirectQuery**.

## 7.5 Delta table maintenance: OPTIMIZE, V-Order, VACUUM and history

Delta tables get slow when they contain **many small files** (frequent small appends, streaming) or lots of files no longer referenced by the log.

| Command / setting | What it does |
| --- | --- |
| `OPTIMIZE table` | **Compacts small files into larger ones** (target around 1 GB). Run it on a **schedule** (a notebook or pipeline). `OPTIMIZE table VORDER` applies V-Order; `ZORDER BY (col)` co-locates data for selective filters. |
| `VACUUM table [RETAIN n HOURS]` | **Deletes data files no longer referenced** by the Delta log and older than the retention period (default 7 days). Run on a schedule. Deleting files manually (OneLake file explorer) **corrupts the table**. |
| **V-Order** | Write-time Parquet optimization (sorting, encoding, compression) that makes reads faster for Fabric engines such as Direct Lake, SQL and Spark. |
| **Optimize write** (`delta.autoOptimize.optimizeWrite`) | Writes fewer, larger files during writes. |
| **Auto compaction** (`delta.autoOptimize.autoCompact`) | Compacts small files automatically after writes. |
| `DESCRIBE HISTORY table` | Lists the **operations performed** on the table (WRITE, MERGE, OPTIMIZE, VACUUM...), so it tells you whether maintenance was done. |
| `DESCRIBE DETAIL table` | Table metadata: size, number of files, partition columns. It does **not** show the operation history. |
| `REFRESH TABLE table` | Invalidates cached metadata/data. Reports nothing about maintenance. |
| `EXPLAIN` | Shows a query plan; not a table history. |

```sql
OPTIMIZE Customer;
VACUUM Customer RETAIN 720 HOURS;   -- keep 30 days of unreferenced files
DESCRIBE HISTORY Customer;
```

  - Lakehouse Explorer also has right-click **Maintenance** (OPTIMIZE, V-Order, VACUUM) on a table.
  - Warehouse tables are Delta too, but the warehouse engine optimizes and compacts them **automatically** with V-Order, which is why a warehouse needs no manual maintenance.
  - Remove unused files → **VACUUM** on a schedule. Combine small files into bigger ones → **OPTIMIZE** on a schedule.

## 7.6 Large semantic model storage format and XMLA operations

- The **Large semantic model storage format** (setting at workspace / model level on Premium or Fabric capacity) stores the model so that it can grow beyond 10 GB, and it makes **XMLA operations faster**: deployments, metadata writes and refreshes by tools such as Tabular Editor or ALM Toolkit finish sooner.
  - Choose the **Large** format (not *Small*) when the requirement is to **minimise the time to deploy** or increase the **speed of XMLA write operations**. It is also the prerequisite for **query scale-out**.
  - Deleting unused columns reduces size but does not change the storage format; the Direct Lake storage mode is a different setting.
  - With the **default (small) storage format** a published or refreshed model is limited to about **10 GB**; a model approaching tens of GB (for example ~50 GB on an F64) can only be published and refreshed if the **Large semantic model storage format** is enabled. The maximum size then depends on the capacity SKU. Parameters, scheduled refresh and query scale-out do not change the size limit.
