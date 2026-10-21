# 5 – Query and analyze data

## 5.1 Connecting to a data warehouse

A Fabric Warehouse is **queried with T-SQL through a TDS endpoint**, the same protocol used by SQL Server.

**How to connect**

  - **SQL connection string:** in the workspace, open the warehouse item menu (⋯) or its settings and copy the SQL connection string. Use it as the server name; the database is the warehouse name.

  - **Authentication:** Microsoft Entra ID only (including MFA). SQL logins are not supported.

  - **Clients:** the SQL query editor and visual query editor in the Fabric portal, SSMS, Azure Data Studio or VS Code (mssql extension), Power BI Desktop (OneLake catalog or SQL Server connector), and notebooks (T-SQL notebooks).

  - **Permissions:** a workspace role (Admin, Member, Contributor, Viewer) or access granted by sharing the item. Viewers can read through the endpoint but cannot create objects.

**Warehouse vs Lakehouse SQL analytics endpoint**

Both expose a T-SQL endpoint, but they do not allow the same operations.

| Capability                               | Warehouse | Lakehouse SQL analytics endpoint                                              |
| ---------------------------------------- | --------- | ----------------------------------------------------------------------------- |
| Read data (SELECT)                       | Yes       | Yes                                                                           |
| CREATE, INSERT, UPDATE, DELETE on tables | Yes       | No. Tables are read-only; data is written with Spark, pipelines or dataflows. |
| Views, functions, stored procedures      | Yes       | Yes                                                                           |
| Multi-table transactions                 | Yes       | No                                                                            |

## 5.2 Views

A view is a saved SELECT query with a name. When you need to query a result set again and again, you create a view and then query it like a table.

**Syntax**

Example: total sales per product, saved as a view.

```sql
CREATE VIEW dbo.vw_SalesByProduct AS
SELECT p.ProductName,
       SUM(s.SalesAmount) AS TotalSales
FROM dbo.FactSales 
```

Then query the view as if it were a table:

```sql
SELECT * FROM dbo.vw_SalesByProduct;
```

**Key points**

  - **No stored data:** The result is calculated every time you query it.

  - **No parameters:** you cannot pass parameters to a view (you can with functions and stored procedures).

  - **Reusable:** A view can query other views.

  - **Rename columns:** a view can alias columns (`SELECT Amount AS SalesAmount ...`), hide columns or pre-join tables without changing the underlying table; build the report on the view when you need different column names.

  - **Semantic models:** reading a SQL view into a semantic model falls back to DirectQuery. Direct Lake is not possible, because Direct Lake reads Delta tables and a view has no Delta files behind it.

**Exam tip:** a named, reusable query with no parameters → view. A semantic model built on a view cannot use Direct Lake: it uses DirectQuery.

## 5.3 Functions

A user-defined function packages query logic together with **input parameters**. In a Warehouse you create an inline table-valued function: it takes parameters and returns a table (a result set) that you query in the FROM clause. Think of it **as a view that accepts parameters**.

**Syntax and example**

Function that takes a first name as input and returns the matching employees:

```sql
CREATE FUNCTION dbo.fn_EmployeeFirstNameSearch (@FirstName VARCHAR(50))
RETURNS TABLE
AS
RETURN
(
    SELECT EmployeeID, FirstName, LastName, Department
    FROM dbo.DimEmployee
    WHERE FirstName = @FirstName
    -- the parameter filters the rows
);
```

Call it in a SELECT, passing the value:

```sql
SELECT * FROM dbo.fn_EmployeeFirstNameSearch('Anna');
```

**How it works and when to use it**

  - **How it works:** the parameter **@FirstName** is replaced by the value you pass in the call, and the SELECT inside RETURN is executed with that value. The result behaves like a table, so you can filter it, join it or aggregate it.

  - **Why:** a view cannot take parameters, so without a function you would repeat the query with a different WHERE each time. The function keeps the logic in one place.

  - **When:** you need a reusable, parameterized, read-only query that you want to use inside other queries, joins or views. If you need to change data, use a stored procedure.

**Key points**

  - **Packaging:** useful for packaging logic and parameters.

  - **Read-only:** only SELECT. A function cannot change the underlying data (no INSERT, UPDATE or DELETE).

  - **No stored procedures:** a function cannot call a stored procedure.

  - **Not executable on its own:** you do not run it with EXEC, and a pipeline cannot orchestrate a function. Wrap it in a stored procedure if a pipeline must trigger it.

  - **Where used:** it can be called from a SELECT, from a view and from a stored procedure.

**Where the objects are stored**

Views, functions and stored procedures are metadata objects: they hold code, not data. In the warehouse Explorer they appear under their schema (for example dbo) in separate folders: Tables, Views, Functions and Stored Procedures.

## 5.4 Stored procedures

A stored procedure is a **saved block of T-SQL that you run by name**. It can contain several statements, accept input parameters, return output, and change data. It is the right tool when the logic does more than just read.

**Basic example**

```sql
CREATE PROCEDURE dbo.usp_GetEmployees
AS
SELECT EmployeeID, FirstName, LastName, Department
FROM dbo.DimEmployee;
```

Run it with EXEC:

```sql
EXEC dbo.usp_GetEmployees;
```

**Stored procedure with an input parameter**

The parameter is **@Department**. It is declared after the procedure name, used in the WHERE clause, and given a value at execution time.

```sql
CREATE PROCEDURE dbo.usp_GetEmployeesByDepartment
    @Department VARCHAR(50)
AS
SELECT EmployeeID, FirstName, LastName, Department
FROM dbo.DimEmployee
WHERE Department = @Department;
```

Run it passing the value:

```sql
EXEC dbo.usp_GetEmployeesByDepartment @Department = 'Sales';
```

**Stored procedure that changes data**

Unlike a view or a function, a procedure can write. This one reloads one day of a summary table:

```sql
CREATE PROCEDURE dbo.usp_RefreshDailySales
    @LoadDate DATE
AS
BEGIN
    DELETE FROM dbo.DailySales WHERE SalesDate = @LoadDate;
    INSERT INTO dbo.DailySales (SalesDate, ProductKey, TotalSales)
    SELECT OrderDate, ProductKey, SUM(SalesAmount)
    FROM dbo.FactSales
    WHERE OrderDate = @LoadDate
    GROUP BY OrderDate, ProductKey;
END;
```

**Key points**

  - **Parameters:** you can define input and output parameters.

  - **Can change data:** it can UPDATE, INSERT and DELETE rows and create tables, which a view or a function cannot do.

  - **Called with EXEC:** it is not part of a SELECT, so no SELECT (and therefore no view or function) can call a stored procedure.

  - **Can call a function:** a procedure can use functions, views and tables inside its code.

  - **Pipelines:** it can be embedded in a pipeline, with parameters (see 4.10).

**Exam tip:** parameters plus changing data (load, merge, update, create tables) → stored procedure. Parameters but read-only, used inside a SELECT → function.

## 5.5 View, function or stored procedure?

The three objects compared side by side.

| Feature                               | View                 | Function                  | Stored procedure                |
| ------------------------------------- | -------------------- | ------------------------- | ------------------------------- |
| Parameters                            | No                   | Input                     | Input and output                |
| Returns                               | A result set         | A table                   | Result sets, or nothing         |
| Changes data (INSERT, UPDATE, DELETE) | No                   | No                        | Yes                             |
| Creates tables                        | No                   | No                        | Yes                             |
| Invoked with                          | SELECT … FROM view   | SELECT … FROM function(…) | EXEC                            |
| Usable inside a SELECT                | Yes                  | Yes                       | No                              |
| Orchestrated from a pipeline          | No                   | No                        | Yes (Stored procedure activity) |
| Semantic model                        | DirectQuery fallback | Not applicable            | Not applicable                  |

**Who can call whom**

The rule is simple: a SELECT can never run a stored procedure, but a stored procedure can use everything else.

| Object           | Can call or query                                        | Cannot call           |
| ---------------- | -------------------------------------------------------- | --------------------- |
| View             | Tables, other views, functions                           | Stored procedures     |
| Function         | Tables, views, other functions                           | Stored procedures     |
| Stored procedure | Tables, views, functions, other stored procedures (EXEC) | Nothing in particular |

**Exam tip:** you can query a view from a view, and call a function from a view or a stored procedure, but you cannot call a stored procedure from a function.

## 5.6 Monitoring and troubleshooting warehouse queries

**Tools**

| Need | Tool |
| --- | --- |
| Is the **capacity** being throttled? Utilization and overage over time | **Microsoft Fabric Capacity Metrics app** (throttling is a capacity-level behaviour; settings pages and the Monitoring hub do not show it). |
| Overview of activity runs (pipelines, notebooks, refreshes) | **Monitoring hub**. |
| A query that has been running for too long: what is it doing, is it blocked? | **DMVs** `sys.dm_exec_requests` (running requests, wait type, blocking session), `sys.dm_exec_sessions`, `sys.dm_exec_connections`. |
| History of past queries, slow and frequent queries | **Query insights** views (`queryinsights.exec_requests_history`, `frequently_run_queries`, `long_running_queries`). |

```sql
SELECT session_id, status, start_time, wait_type, blocking_session_id, command
FROM sys.dm_exec_requests
WHERE status <> 'background';
```

  - Fabric warehouse uses the SQL Server-style DMVs (`sys.dm_exec_*`). The `sys.dm_pdw_*` views belong to Azure Synapse dedicated SQL pools, not to Fabric.
  - Throttling symptom: all queries slow down at the same times during the day → look at the Capacity Metrics app first.

**Exam tip:** "report query stuck for 45 minutes, what is blocking it?" → `sys.dm_exec_requests`. "Is Fabric throttling my warehouse?" → Capacity Metrics app.

## 5.7 Warehouse statistics

The Fabric warehouse query optimizer uses **statistics** (cardinality, value distribution, average column length) to choose an efficient plan. Out-of-date statistics lead to poor plans and slow queries.

- Fabric creates and updates statistics **automatically** (on the fly when queries need them), but you can manage them manually:
  - `CREATE STATISTICS stats_name ON dbo.Table (Column);`
  - `UPDATE STATISTICS dbo.Table (stats_name);` (or the whole table)
- Prioritize columns the optimizer uses to **filter, join, group and sort**: columns in `WHERE`, `JOIN`, `GROUP BY`, `ORDER BY` and `DISTINCT`.
- The data type, being a primary key or having high cardinality are **not** by themselves the reason to update a statistic.
- To find a slow query, use Query insights / DMVs (see 5.6), then check whether its statistics are stale.

**Exam rule of thumb:** "manually update statistics to speed up a query" = update statistics on the columns used in **GROUP BY / WHERE / JOIN** clauses.

## 5.8 Exam quick reference

  - Connect to a warehouse → SQL connection string, Entra ID authentication, any TDS client (SSMS, VS Code, portal editor).

  - Change data with T-SQL → Warehouse. The Lakehouse SQL analytics endpoint is read-only for tables.

  - Saved query, no parameters → view. Stores no data; result calculated at query time.

  - Semantic model on a SQL view → DirectQuery fallback, no Direct Lake.

  - Parameterized read-only query → function (inline table-valued), used in FROM with SELECT.

  - A function cannot change data and cannot call a stored procedure.

  - Parameters and data changes, run with EXEC → stored procedure; can call functions, views and other procedures.

  - Views, functions and procedures appear in the warehouse Explorer under their schema, in separate folders.

  - Update warehouse statistics manually → columns used in WHERE, JOIN, GROUP BY, ORDER BY, DISTINCT.

  - Rename columns for a report without touching the table → view (alias).
