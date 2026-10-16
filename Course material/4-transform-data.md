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

## 4.11 Exam quick reference

  - Run T-SQL from a pipeline → Stored procedure activity (connect to the warehouse, procedure name, parameters).
