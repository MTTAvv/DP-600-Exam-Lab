# 4 – Transform data

## 4.1 T-SQL views, functions & stored procedures

**Views**

You can create a simple T-SQL View like this:

```sql
CREATE VIEW  dbo.vw_Employee_GetJack AS 
SELECT 
    EmployeeId
    , Name 
    , Age 
from dbo.Employees
WHERE Name like 'Jack%';

select * from dbo.vw_Employee_GetJack
```

  - Transformed data is not stored in a view, the result is calculated at query time.

  - You can create a View from another View (but be careful, this can lead to poor performance, and difficult to understand/ maintain)

  - you cannot specify parameters for a View (this is possible with functions and stored procedures)

  - Reading a SQL View into a semantic model will fall back to DirectQuery (Direct Lake not possible).

**T-SQL Functions**

```sql
CREATE FUNCTION dbo.fn_Employee_FirstNameSearch (  @firstname varchar(20) = ''  )  
RETURNS TABLE  
AS 
RETURN 
(
    SELECT 
        EmployeeId
        , Name 
        , Age 
    from dbo.Employees
    WHERE Name like @firstname + '%'
) ;

-- Test the function 
select * from dbo.fn_Employee_FirstNameSearch('Sarah')
```

  - Useful for **packaging up logic**, which can be **parameterized**

  - Only SELECT statements, can never edit the underlying data (using UPDATE/ INSERT etc)

  - Can be called from DDL statements, or from within Stored Procedures, or a View

  - Can't be orchestrated (directly) from a data pipeline (although you can embed in a stored proc).

  - Allows one or many input parameters

  - Output type should also be a Table

**Stored Procedures**

```text
-- stored procedure with input parameter 
CREATE PROCEDURE dbo.sp_Employee_GetByFirstName @firstname varchar(20)
as 
select * from dbo.Employees
where Name like @firstname + '%'

exec dbo.sp_Employee_GetByFirstName 'Jack'
```

  - Ability to define input AND OUTPUT parameters

  - Are called using EXEC (not as part of a select statement)

  - Can call other stored procedures

  - Can also give access to people to the Stored Procedure (and not the underlying dataset)

  - Can be embedded in a data pipeline (with parameters passed)

  - Ability to do INSERTS, UPDATES, DELETES

## 4.2 Enriching data (new columns and tables)

**Key points**

*Dataflow Gen2*

In a Dataflow Gen2, there are a number of methods for adding a column to your query:

![](img/image2.png)

  - Column from examples - allows you to give some expected values, and the Dataflow will try to guess the pattern, and generate your M query that outputs your expected values.

  - Custom Column - you can write Power Query formulas to create the logic you need for your new column

  - Conditional columns - allow you to write conditional logic to define your new column. For example, if the column value is greater than, or equal to x, the output value should be y.

*In a Data Warehouse*

You can add columns to a dataset, simply by declaring them in a SELECT statement. For example

```sql
SELECT [customer_id]
    ,[customer_name]
    ,[customer_city_id]
    ,[customer_email]
    , 'HubSpot' as [source_system]
    , YEAR(GETDATE()) as [current_year]
FROM [DW001_DWH].[raw].[hubspot_contacts]
```

this query adds a constant value of 'HubSpot' to the \[source\_system\] column, and the \[current\_year\] column as a Calculated column.

In this example, you can use a CASE statement to define a new column with conditional logic:

```sql
SELECT [customer_id]
    ,[customer_name]
    ,[customer_city_id]
    ,[customer_email]
    , 'HubSpot' as [source_system]
    , CASE WHEN [customer_id] <= 10 THEN 'GOLD'
           WHEN [customer_id] <= 20 THEN 'SILVER'
           WHEN [customer_id] <= 30 THEN 'BRONZE'
      ELSE 'No Prize'
      END AS 'promotion_category'
FROM [DW001_DWH].[raw].[hubspot_contacts]
```

## 4.3 Implementing STAR schema (LH & DWH)

**Key points**

  - You can define relationships between tables, within the Model Layouts section of the Data Warehouse (or Lakehouse SQL Endpoint).

When you create a relationship between two tables, it will do the following:

  - Set the physical relationships - primary and foreign key constraints in the database

  - Set the logical relationships - primary and foreign key constraints in the default Power BI semantic model.

Note: primary key constraints in Fabric are NOT ENFORCED

Further learning resources:

Define relationships in data models for data warehousing in Microsoft Fabric.

## 4.4 Denormalize data

**Key points**

Before we look at denormalizing data, it's important to understand what normalized data is, where is comes from, and what is looks like:

An important distinction to make is the difference between operational IT systems (referred to as OLTP: online transactional processing systems) and the analytical systems that we might build in Microsoft Fabric (sometimes referred to as OLAP: online analytical processing systems).

OLTP and OLAP systems are built for different use cases, and therefore their tables are designed in different ways. OLTP systems are built for to handle lots of transactions, very fast. The backend database tables are designed to be fully 'normalized'.

This means that entities in an OLTP application each have their own table in the backend. It might look something like this, which is an example of an entity-relationship diagram for a billing system:

This structure minimises redundancy - every value is only stored in one place, making it efficient, from a storage perspective. But this kind of heavily normalized structure is less optimal for analytics use cases. OLTP systems are commonly used as a data source for OLAP analytical systems, however, we must denormalize how the data is structured to make it more useful for analytical workloads.

*Denormalization of data*

Put simply, denormalizing data looks like this (below), two or more tables are 'denormalized' into a single table for analytics use cases. This can be done in a Data Warehouse using JOINs.

## 4.5 Aggregate data

**Key points**

*Dataflow Gen2*

In a Dataflow Gen2, you can click Group By in the ribbon, to see the following configuration options:

*T-SQL Data Warehouse*

Aggregating data using T-SQL is done using the GROUP BY syntax, and an aggregate function (such as MIN(), MAX(), SUM()). This is an example whereby I am grouping by the customer\_city\_id column, and performing a COUNT() aggregation:

```sql
SELECT customer_city_id
    , COUNT(customer_id) AS 'total_customers'
FROM raw.hubspot_contacts
GROUP BY customer_city_id
ORDER BY COUNT(customer_id) DESC
```

## 4.6 Merge and join data

*Dataflow Gen2*

In a Dataflow Gen2, in the ribbon, click on Merge Queries (or Merge Queries as New, if you want to generate a completely new merged query):

You will be asked to specify on which keys you wish to merge your two queries, as well as specifying a join type:

*T-SQL Data Warehouse*

In a T-SQL query, you can define a join between two (or more) tables, like this:

```sql
SELECT pv.ProductID, v.BusinessEntityID, v.Name
FROM Purchasing.ProductVendor AS pv 
INNER JOIN Purchasing.Vendor AS v
    ON (pv.BusinessEntityID = v.BusinessEntityID)
WHERE StandardPrice > $10
    AND Name LIKE N'F%';
```

## 4.7 Handling duplicates, missing values, nulls

*Dataflow Gen2*

Duplicates can be removed quite simply by right-clicking on a column (or selecting multiple columns, and then right-clicking), then selecting Remove Duplicates

Missing values can be handled either by:

  - Filtering out that row of data, if there is a missing or NULL value.

  - Replace Values - you can 'replace' the NULL value with a specific value. Or...

  - Fill Up/ Down - Fill Down fills empty cells with the value in the cell directly above the empty cell, starting from the top. Fill Up does the opposite.

*T-SQL Data Warehouse*

There are a number of methods for removing duplicate data using T-SQL.

Using SELECT DISTINCT col\_name FROM table is the simplest way.

You can update your data in a Data Warehouse table to handle/ replace NULL values, like so:

```sql
UPDATE table_name
SET column_name = 'Something Else' 
WHERE column_name IS NULL
```

Another method would be to remove these rows from your dataset entirely:

```sql
SELECT * from my_table 
WHERE important_column IS NOT NULL
```

## 4.8 Converting column data types

*Dataflow Gen2*

In a Dataflow Gen2, you can change the column data type by right-clicking on a column, clicking Change Type, like this:

Most of the Types above are self-explanatory, Using Locale is an interesting one to convert string values into a Date or DateTime, taking into consideration the formating of the DateTime in the string.

*T-SQL Data Warehouse*

Using T-SQL, you can CAST a column from one data type to another:

```sql
SELECT CAST(ROUND(SalesYTD / CommissionPCT, 0) AS INT) AS Computed
FROM Sales.SalesPerson
WHERE CommissionPCT != 0;
```

You can also use CONVERT:

```sql
SELECT TOP(1)
   SYSDATETIME() AS UnconvertedDateTime,
   CAST(SYSDATETIME() AS NVARCHAR(30)) AS UsingCast,
   CONVERT(NVARCHAR(30), SYSDATETIME(), 126) AS UsingConvertTo_ISO8601
FROM dbo.DimCustomer;
```

CONVERT is particularly useful for Datetime conversion in different formats - see documentation for more.

## 4.9 Filter data

*Dataflow Gen2*

Clicking on the disclosure arrow at the top of a column opens up the filtering options for that column:

*T-SQL Data Warehouse*

Filtering using T-SQL is done using the WHERE clause - there are many variations

```text
-- Filtering using < > <= >= != = AND OR BETWEEN 
SELECT customer_id
    , customer_name 
FROM raw.hubspot_contacts
WHERE customer_id > 50

--DW004_02
SELECT customer_id
    , customer_name 
FROM raw.hubspot_contacts
WHERE customer_id BETWEEN 10 AND 15
```

Filtering if in a list:

```text
--DW004_03
SELECT customer_id
    , customer_name 
    , customer_city_id
    , customer_email
FROM raw.hubspot_contacts
WHERE customer_id IN (1, 45, 78, 99)
```

Filtering string columns using the LIKE and the % operator:

```sql
SELECT customer_name
FROM raw.hubspot_contacts
WHERE customer_name LIKE 'P%'
```

## 4.10 Running a stored procedure from a pipeline

A pipeline can run a stored procedure with the Stored procedure activity. This is the way to run T-SQL logic (loads, merges, cleanups) as one step in an orchestrated flow.

  - Add a **Stored procedure** activity to the pipeline canvas.

  - In Settings, connect to the warehouse: choose the Warehouse (connection type Fabric Warehouse).

  - **Stored procedure name:** pick the procedure from the list (or type it).

  - **Parameters:** select Import to read the parameters, then set name, type and value for each. Use dynamic content to pass a pipeline parameter or an expression (for example today's date).

  - Chain the activity with others using the success, failure or completion paths.

Only stored procedures can be called with this activity. To run a view or a function from a pipeline, wrap it in a stored procedure. The Script activity can also run T-SQL statements directly.

**Exam tip:** a pipeline step must run T-SQL with parameters against a warehouse → Stored procedure activity pointing to the warehouse, with the procedure name and its parameters.

## 4.11 Window functions, CTAS, SELECT INTO and table clones

**Window functions** compute a value per row over a group of rows without collapsing them. The pattern *"latest row per key"* numbers the rows and keeps number 1.

```sql
WITH CustomerBase AS (
    SELECT CustomerID, CustomerName, PostalCode, LastUpdated,
           ROW_NUMBER() OVER (PARTITION BY CustomerID ORDER BY LastUpdated DESC) AS x
    FROM dbo.CustomerChanges
)
SELECT CustomerID, CustomerName, PostalCode, LastUpdated
FROM CustomerBase
WHERE x = 1;
```

  - `PARTITION BY` = the group (one numbering per customer); `ORDER BY ... DESC` = newest first.
  - `ROW_NUMBER()` gives 1, 2, 3...; `RANK()`/`DENSE_RANK()` give ties the same number; `LAG()`/`LEAD()` read the previous/next row; `SUM() OVER (...)` gives running totals.
  - A window function cannot be used directly in `WHERE`: compute it in a CTE or subquery, then filter (`WHERE x = 1`). `HAVING` is for aggregates, not for window numbers.

**Creating a table from a query**

| Statement | Result | Notes |
| --- | --- | --- |
| `CREATE TABLE t AS SELECT ...` (**CTAS**) | New table filled with the query result. | Fabric warehouse. Can read a lakehouse in the same workspace with three-part names: `FROM lakehouse1.dbo.customer`. |
| `SELECT ... INTO t FROM ...` | New table from the query. | Also supported. |
| `INSERT INTO t SELECT ...` | Adds rows to an **existing** table. | Table must already exist. |
| `CREATE TABLE t2 AS CLONE OF t1` | **Zero-copy clone**: copies metadata and points to the same Parquet files. | Instant regardless of size, no extra storage until data diverges. |

**Clone details:** the clone is independent after creation. Later data changes or schema changes on the source are **not** applied to the clone, and changes to the clone do not affect the source. Time travel clone: `AS CLONE OF t1 AT '2024-05-01T10:00:00'`. Use it to copy a table with minimal data copying.

## 4.12 T-SQL functions for nulls, dates and choosing values

| Function | What it does | Example |
| --- | --- | --- |
| `COALESCE(a, b, c)` | Returns the **first non-NULL** value. | `COALESCE(Weight, Quantity, 1)` = weight if present, else quantity if present, else 1. |
| `ISNULL(a, b)` | Two-argument version of COALESCE. | `ISNULL(Price, 0)` |
| `NULLIF(a, b)` | Returns NULL if a = b (avoids divide by zero). | `x / NULLIF(y, 0)` |
| `GREATEST(a, b, c)` | Largest value among several **columns** (row-wise). | Highest of ListPrice, WholesalePrice, AgentPrice. |
| `LEAST(a, b)` | Smallest value among several columns; **ignores NULL**. | Lowest of ListPrice and SalePrice. |
| `MAX()` / `MIN()` | **Aggregates** over rows, not across columns. | Highest price of a group of rows. |
| `IIF(cond, a, b)` | Inline if/else. | |
| `CHOOSE(n, a, b, c)` | Picks the n-th item of a list. | |
| `DATETRUNC(month, d)` | Truncates a date to the **start of the period** (first day of the month). | `DATETRUNC(month, OrderDate)` |
| `DATE_BUCKET(...)` | Groups dates into fixed-size buckets. | |
| `DATEPART(part, d)` | Returns a **number** (year, month, weekday number). | `DATEPART(YEAR, SaleDate)` |
| `DATENAME(part, d)` | Returns the **name** as text (`weekday` → Monday). | `DATENAME(weekday, OrderDate)` |
| `DATEFROMPARTS(y, m, d)` | Builds a date from parts. | |

**Exam tips**

  - First non-null → `COALESCE`. Largest/smallest across columns → `GREATEST`/`LEAST`. `MAX`/`MIN` work across rows.
  - First day of the month → `DATETRUNC(month, ...)`. Day name → `DATENAME(weekday, ...)`.
  - Filters on aggregates (`SUM(Amount) > 10000`) go in `HAVING` after `GROUP BY`; filters on columns (`DATEPART(YEAR, d) = 2023`) go in `WHERE`.

## 4.13 Slowly changing dimensions (SCD)

A slowly changing dimension manages how a dimension row changes over time (for example a customer who moves to a new city).

| Type | Behaviour | History | Columns needed |
| --- | --- | --- | --- |
| **Type 1** | **Overwrite** the changed attributes in place. Insert rows for new natural keys. | None | None extra. |
| **Type 2** | **Add a new row** for every change and close the old one. | Full history | **Surrogate key**, **effective start date**, **effective end date** (or an *IsCurrent* flag). The natural (business) key stays, but is no longer unique. |
| **Type 3** | Keep the previous value in an extra column. | Limited (one previous value) | `PreviousCity`-style columns. |

**Type 2 example**

| CustomerSK | CustomerID | City | StartDate | EndDate | IsCurrent |
| --- | --- | --- | --- | --- | --- |
| 1 | C1 | Milan | 2022-01-01 | 2024-03-31 | 0 |
| 2 | C1 | Rome | 2024-04-01 | 9999-12-31 | 1 |

**Loading patterns**

  - **Type 1:** update rows when non-key attributes changed, insert rows when the natural key does not exist in the dimension. No end dates, no duplicate rows.
  - **Type 2:** when attributes change, update the effective end date of the current row, then insert a new row with the new values and a new surrogate key. Facts reference the surrogate key.
  - In Fabric this can be done with T-SQL (`UPDATE` + `INSERT`), a dataflow, or a Spark Delta `MERGE`.

**Exam tips**

  - "Keep history of every version" → Type 2 → needs surrogate key + start/end date columns (columns that do not already exist).
  - "Latest value only" → Type 1. "Current and previous value" → Type 3.

## 4.14 Dimensional modeling decisions and the date dimension

**Star schema design**

  - One **fact table** at a chosen **grain** (for example one row per order item) holding measures and foreign keys; several **dimension tables** (Date, Product, Customer) holding descriptive attributes.
  - Source tables are usually normalized (snowflake). Flatten them: **denormalize** parent tables into the dimension they describe, for example an entity such as *Company* is folded into the Product and Customer dimensions instead of staying as a separate table.
  - Relationships between fact and dimension are based on the **key that identifies the dimension row**. When the source key is composite (for example CompanyID + ProductID), the relationship must use **both columns**, or a new single surrogate key that combines them.
  - Use **surrogate keys** (integers) in dimensions, especially for SCD Type 2.

**Date dimension**

A date table has one row per day with attributes (year, quarter, month, month name, week, day name, fiscal period). It is needed for time intelligence. When there is no source for dates you must **generate** it:

  - **Dataflow Gen2 / Power Query:** `List.Dates(#date(2020,1,1), 3653, #duration(1,0,0,0))` converted to a table, then add columns.
  - **Stored procedure called from a pipeline** that fills the table with T-SQL (a loop or a recursive CTE / numbers table).
  - **Notebook** with Spark (`sequence`/`explode`) or pandas (`date_range`).
  - In a semantic model mark it as a date table (`Mark as date table`) so time-intelligence functions work.

## 4.15 Power Query: profiling, unpivot, query folding and native queries

**Data profiling (Data view options)**

  - **Column quality** (valid, error, empty %), **column distribution** (distinct/unique counts) and **column profile** (statistics and value histogram).
  - To see min and max of each column: enable **column profile**, enable the **details pane**, and show the **column profile in the details pane**.
  - By default profiling uses the **first 1,000 rows**; switch to "based on entire data set" to profile everything.
  - Distinct count lower than the row count → some values repeat (duplicates).
  - M function `Table.Profile(table)` returns, for every column: Min, Max, Average, StandardDeviation, Count, NullCount, DistinctCount. `Table.Max` returns a single **row**, `Table.MaxN` the top N rows, `Table.Range` a slice of rows.

**Unpivot** (columns → attribute/value rows)

| Command | Effect |
| --- | --- |
| **Unpivot columns** | Unpivots the **selected** columns. |
| **Unpivot other columns** | Select the identifier columns (for example VendorID) and unpivot **all the others**; new columns added later are unpivoted too. |
| **Unpivot only selected columns** | Same as unpivot columns but ignores new columns added later. |

**Query folding**

  - Folding means Power Query translates the steps into a **single query run by the source** (for example SQL), which is fast.
  - Steps that do not fold run in the **Power Query (mashup) engine**, after the data is downloaded. Once a step does not fold, the following steps usually do not fold either.
  - Sources that cannot fold: **files** (CSV, Excel, JSON). For them incremental refresh cannot push the date filter, so the refresh scans everything.
  - In Dataflow Gen2 you can see folding indicators and the query plan on each step.

**Native query and EnableFolding**

```m
let
    Source   = Sql.Databases("server.database.windows.net"),
    Database = Source{[Name = "db"]}[Data],
    Query    = Value.NativeQuery(
                   Database,
                   "SELECT * FROM customer WHERE country IN ('USA','UK')",
                   null,
                   [EnableFolding = true])
in
    Query
```

`Value.NativeQuery` runs your own SQL; **`EnableFolding = true`** lets later foldable steps be added on top and processed by the SQL engine.

## 4.16 Join types and merging queries

| Join | Returns |
| --- | --- |
| **Inner** | Only rows with a match in both tables. |
| **Left outer** | All rows of the left table + matches from the right. |
| **Right outer** | All rows of the right table + matches from the left. |
| **Full outer** | **All rows of both tables**, with NULL where there is no match. |
| **Left anti** | Rows of the left table with **no** match in the right. |
| **Right anti** | Rows of the right table with no match in the left. |
| **Cross** | Every combination (Cartesian product). |

These names are the same in the Fabric **visual query editor**, in Power Query **Merge queries** and (without "outer"/"anti" keywords) in T-SQL.

**Merge vs Append (Power Query)**

  - **Merge queries** = join (adds columns from another table based on matching keys).
  - **Append queries** = union (stacks rows of tables with the same columns).

**Fuzzy matching** (Merge with *Use fuzzy matching*): tolerates differences between keys. Options include **similarity threshold**, **ignore case**, **ignore spaces** and a transformation table. To join values that differ only by spaces with minimum effort → Merge queries + fuzzy matching with *ignore spaces*.

## 4.17 Exam quick reference

  - Run T-SQL from a pipeline → Stored procedure activity (connect to the warehouse, procedure name, parameters).
