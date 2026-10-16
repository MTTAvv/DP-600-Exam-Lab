# 3 – Get data

## 3.1 Ways to bring data into Fabric

There are three families of options:

| Approach            | Items                                                                                                                                                 | Is data copied?                                                                                                |
| ------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| Ingestion (ETL/ELT) | Dataflow Gen2, data pipeline, notebook, eventstream.                                                                                                  | Yes. Data is extracted, optionally transformed, and written into OneLake (Lakehouse, Warehouse, KQL database). |
| Shortcut            | Internal (other OneLake locations) and external (Amazon S3, ADLS Gen2, Google Cloud Storage, Dataverse, S3-compatible storage such as Cloudflare R2). | No. A live link to the data where it is.                                                                       |
| Database mirroring  | Azure SQL Database, Azure Cosmos DB, Snowflake.                                                                                                       | Yes. Continuous replication into OneLake, with no pipeline to build.                                           |

  - **ETL vs ELT:** ETL transforms the data before loading it (dataflow Gen2 does this with Power Query). ELT loads the raw data first and transforms it inside the destination (for example a pipeline Copy activity followed by a notebook or SQL).

  - **Destination:** ingested data lands in OneLake, as Delta tables or files in a Lakehouse, tables in a Warehouse, or tables in a KQL database.

**Exam tip:** first decide whether the data must be copied. No copy → shortcut. Live replica of a database → mirroring. Otherwise choose the ingestion item that fits the skills, the volume and the need for orchestration (see 3.5).

## 3.2 Dataflow Gen2

A dataflow brings data in through the Power Query low-code/no-code interface. You use 150+ connectors to external systems, apply transformations, and then write to a Fabric data store. It is the only ingestion item that covers Extract, Transform and Load with no code.

**Use it when**

  - **Low code:** you want the familiar Power Query experience, with no code to write.

  - **Full ETL:** it does Extract, Transform and Load in one item.

  - **Connectors:** you need one of the 150+ external connectors.

  - **On-premises data:** it reaches on-premises sources through the on-premises data gateway (OPDG).

  - **Several datasets at once:** you need to get more than one dataset and combine them (you may want to space this out in stages, to allow data validation).

  - **Static local files:** it can upload raw local files (for example Excel or CSV).

**Watch out**

  - **Large datasets:** a dataflow can struggle with them. **Fast Copy** has been introduced to speed up the ETL for supported sources (see section 0.3).

  - **Data validation:** difficult to implement.

  - **Parameters:** according to the course, it cannot receive external parameters.

**Key points**

  - **Data destination:** each query can write to a destination such as a Lakehouse, a Warehouse or a KQL database.

  - **Orchestration:** a dataflow can be refreshed on a schedule or run as a step of a data pipeline (Dataflow activity).

**Exam tip:** low-code transformations with Power Query, 150+ connectors, on-premises data through a gateway, or uploading a static local file → dataflow Gen2.

## 3.3 Data pipeline

A data pipeline is primarily an orchestration tool (do this, then do that). It can also bring data into Fabric, using the **Copy data** activity (and other activities).

**Use it when**

  - **Large datasets:** the Copy data activity is built for large volumes. Since dataflows now have Fast Copy, the performance of the two should be comparable.

  - **Cloud data:** you import data that sits in the cloud, for example in Azure.

  - **Control flow logic:** ForEach, If Condition, Switch, Until, Wait, and dependency paths (on success, on failure, on completion, on skip).

  - **Triggering other work:** it can start a wide variety of actions in and outside Fabric, such as dataflows, notebooks, stored procedures, KQL scripts, webhooks, Azure Functions, Azure ML and Azure Databricks.

  - **Scheduling and parameters:** a pipeline can run on a schedule or on a trigger, and accepts parameters.

**Watch out**

  - **No native transformation:** a pipeline cannot transform data on its own, but it can embed a notebook or a dataflow to do it.

  - **No local files:** you cannot upload local files.

  - **Cross-workspace:** according to the course, a pipeline does not work across workspaces (a limitation that was planned to be removed).

**Key points**

  - **Copy job:** a simpler item that copies data (including incremental copy) without building a pipeline.

  - **Gateways:** a pipeline can reach on-premises sources through the on-premises data gateway (see section 0.3).

**Exam tip:** orchestration, control flow (loops, conditions), a large copy, or triggering notebooks and dataflows in sequence → data pipeline.

## 3.4 Notebook

A notebook is a general-purpose coding item (PySpark, Python, Spark SQL, Scala, R). It brings data into Fabric by connecting to APIs or by using client Python libraries.

**Use it when**

  - **APIs:** you extract data from APIs, for example with the Python **requests** library or similar.

  - **Client libraries:** you need a client library, such as the Azure libraries or the HubSpot client library to access HubSpot data.

  - **Code re-use:** the code can be reused and parameterized (for example run from a pipeline Notebook activity).

  - **Data validation:** you want to validate and quality-test the incoming data.

  - **Performance and cost:** according to the course, it is the fastest ingestion option and the most efficient in CU spend.

**Watch out**

  - **Skills:** not a good fit when the organization has no Python capability.

  - **Warehouse as destination:** according to the course, writing to a Data Warehouse is not possible from a notebook. The natural destination is a Lakehouse (Delta tables or files).

**Exam tip:** API extraction, a Python client library, data quality checks, or the most CU-efficient option → notebook. Destination is a Warehouse → not a notebook.

## 3.5 Choosing between dataflow, pipeline and notebook

The three items overlap, so the exam asks you to pick the best fit for a scenario.

| Criterion            | Dataflow Gen2                  | Data pipeline                               | Notebook                            |
| -------------------- | ------------------------------ | ------------------------------------------- | ----------------------------------- |
| Style                | Low-code (Power Query)         | Low-code (visual canvas)                    | Code                                |
| Main role            | ETL                            | Orchestration and copy                      | Custom ETL in code                  |
| Transformation       | Yes, built in                  | Not natively (embed a notebook or dataflow) | Yes, in code                        |
| Large volumes        | Can struggle (Fast Copy helps) | Good                                        | Good; fastest and most CU-efficient |
| On-premises data     | Yes, through the gateway       | Yes, through the gateway                    | No gateway                          |
| Upload local files   | Yes (static files)             | No                                          | No                                  |
| Control flow         | No                             | Yes                                         | Only in code                        |
| Data validation      | Difficult                      | Limited                                     | Strong                              |
| External parameters  | No (per the course)            | Yes                                         | Yes                                 |
| Write to a Warehouse | Yes                            | Yes (Copy data)                             | Not possible (per the course)       |

**Exam tip:** no code and Power Query → dataflow. Orchestration, control flow or triggering other items → pipeline. APIs, custom logic or data quality tests → notebook. A common pattern is a pipeline that orchestrates dataflows and notebooks.

## 3.6 Shortcuts

A shortcut creates a live link to data stored in another part of Fabric or in external storage, such as Amazon S3, ADLS Gen2, Google Cloud Storage, Dataverse or S3-compatible storage like Cloudflare R2. The data is not copied: it is read where it lives, so there is no duplication and no ETL to maintain.

**When to use shortcuts**

  - Query data from other lakehouses, warehouses, or workspaces without duplication.

  - Access external storage (for example ADLS Gen2 or Amazon S3) directly from a lakehouse.

  - Combine data from several sources in a single lakehouse view without moving it.

  - Reduce storage costs and avoid stale, redundant copies.

**Key facts**

  - **Granularity:** a shortcut can point to an individual file or to a folder.

  - **Internal shortcut:** points to another location in OneLake: Lakehouses, Warehouses, KQL databases, mirrored databases (including Mirrored Azure Databricks Catalogs), SQL databases and semantic models (same or different workspace).

  - **External shortcut:** points to storage outside Fabric: ADLS Gen2, Azure Blob Storage, Amazon S3 and S3-compatible storage, Google Cloud Storage, Dataverse, OneDrive and SharePoint, Iceberg tables, and on-premises or network-restricted locations (through the on-premises data gateway).

  - **Where you create it:** in a Lakehouse (under Tables or under Files) or in a KQL database. A Warehouse cannot host shortcuts. Tables and Files follow different rules (see “Where to place shortcuts in a lakehouse”).

  - **How it behaves:** it looks like a folder, so notebooks, Spark, the SQL analytics endpoint, Direct Lake models and Power BI read it as if the data were local. Changes at the source are visible immediately.

  - **Authorization:** an internal shortcut checks the permissions of the user on the target data. An external shortcut uses the credentials of the connection set up when the shortcut was created. Anyone with access to the lakehouse can therefore read through an external shortcut.

  - **Deleting:** deleting the shortcut removes only the link; the target data stays. Deleting or writing files through a shortcut, however, changes the target data.

  - **Caching:** for external shortcuts (S3, Google Cloud Storage, S3-compatible) caching can be enabled to reduce egress costs. Cached files are kept for a retention period of 1 to 28 days.

**Where to place shortcuts in a lakehouse**

  - **Tables:** shortcuts can only be created at the top level (no subfolders). If the target holds Delta data, the lakehouse recognizes it as a table, queryable with both Spark and the SQL analytics endpoint.

  - **Files:** shortcuts can be created at any level of the folder hierarchy. The data is not registered as a table, but Spark can read it directly.

  - **Limit of external Delta tables:** an external Delta table created with Spark code is not automatically visible in the SQL analytics endpoint. Create a shortcut in the Tables section to make it available to SQL queries.

To create one, open the lakehouse, go to the Explorer view and select the ellipsis (…) next to Tables or Files. The menu option depends on where you create it:

| Location | Menu option         | What it creates                                                                                        |
| -------- | ------------------- | ------------------------------------------------------------------------------------------------------ |
| Tables   | New table shortcut  | A shortcut to a single Delta table, registered automatically as a table in the lakehouse.              |
| Tables   | New schema shortcut | A shortcut to a folder containing several Delta tables, which appear as a new schema in the lakehouse. |
| Files    | New shortcut        | A shortcut to any folder, in any format. The data is not registered as a table.                        |

**Who can do what**

Workspace roles decide what a user can do with shortcuts and the data behind them.

| Role                       | What it can do with shortcuts                                                                                                                                                                                                |
| -------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Admin, Member, Contributor | Same capabilities for all three: create shortcuts, read files, folders and content (Lakehouse explorer, Spark, OneLake APIs), write or delete through the shortcut, and query with T-SQL through the SQL analytics endpoint. |
| Viewer                     | Read only, and only through the SQL analytics endpoint (TDS) of the Lakehouse, using T-SQL. It cannot browse the data in the Lakehouse explorer, nor read it with Spark or the OneLake APIs.                                 |

To create a shortcut you need write permission where the shortcut is created (Contributor or higher) and read permission on the target. See “Implement workspace-level access controls” (section 1.1) for the full permissions matrix.

**Shortcut or copy?**

| Scenario                                                              | Approach                                                               |
| --------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| Data is already in Fabric (another lakehouse, warehouse or workspace) | Shortcut: avoids duplication and keeps data in sync.                   |
| Data is in external cloud storage and you need near-real-time access  | Shortcut: no ingestion pipeline to maintain.                           |
| Data needs complex transformations before use                         | Copy: use pipelines, dataflows or notebooks to transform and load.     |
| Compliance requires data to reside in a specific region               | Copy: a shortcut does not move data, so it stays in its source region. |
| You need full control over schema evolution and table maintenance     | Copy: Delta table maintenance operations only work on local tables.    |

**Exam tip:** data in S3, ADLS or Google Cloud Storage, without copying → external shortcut. Data in another Lakehouse or Warehouse, without copying → internal shortcut. Viewer and shortcuts → read-only through the SQL analytics endpoint. Deleting a shortcut does not delete the source data. Tables section → top level only, a Delta target is recognized as a table; Files section → any level, no table registration. Complex transformations, data residency or table maintenance needs → copy, not shortcut.

## 3.7 Database mirroring

Mirroring continuously replicates an operational database into OneLake, in near real time, with no ETL to build.

  - **Sources:** Azure SQL Database, Azure Cosmos DB and Snowflake (more sources are added regularly).

  - **Result:** a mirrored database item, with the data stored as Delta tables in OneLake and a SQL analytics endpoint. It is read-only and can be used by Spark, shortcuts, cross-database queries and Direct Lake models.

  - **Cost:** the compute used for replication is free, and storage is free up to a limit tied to the capacity SKU (for example 64 TB with F64).

  - **Mirroring vs shortcut:** a shortcut does not copy the data; mirroring does copy it, and keeps the copy in sync.

**Exam tip:** a live, continuously updated replica of Azure SQL Database, Cosmos DB or Snowflake in Fabric, with no pipeline → database mirroring.

## 3.8 Eventstream

An eventstream captures, transforms and routes real-time events with a no-code editor. It is the ingestion item for streaming data: sources such as Azure Event Hubs, Kafka or custom apps are routed to a KQL database, a Lakehouse or Activator.

## 3.9 Scheduling dataflows, pipelines and notebooks

Items do not run on their own: you either run them on demand or attach a schedule. Each item has its own scheduler, with different options and limits.

| Item          | Where to schedule                                                                         | Frequency and limits                                                                                                             |
| ------------- | ----------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| Dataflow Gen2 | Schedule refresh icon in the workspace list, or the dataflow Settings → Refresh.          | Up to 48 refreshes per day (one every 30 minutes). Hard cap of 300 refreshes per rolling 24 hours (150 for non-CI/CD dataflows). |
| Data pipeline | Schedule button on the Home tab of the pipeline editor, or ⋯ → Schedule in the workspace. | By the minute, hourly, daily, weekly or monthly. Set start and end date and the time zone.                                       |
| Notebook      | Notebook ribbon (Run → Schedule), or ⋯ → Schedule in the workspace.                       | By the minute, hourly, daily, weekly or monthly. Set start and end date and the time zone.                                       |

**Differences to remember**

  - **Dataflow Gen2:** the scheduler is limited to 48 refreshes per day. For anything more frequent or more complex, call the dataflow from a pipeline (Dataflow activity) and schedule the pipeline.

  - **Pipeline:** the most flexible, because one schedule can start a whole chain (dataflow → notebook → stored procedure → semantic model refresh). It also supports event-based triggers, not only time.

  - **Notebook:** a scheduled run uses the identity of the person who set the schedule. When a notebook is part of a larger flow, call it from a pipeline Notebook activity instead of scheduling it alone.

  - **Time zone and overlap:** schedules are set in a chosen time zone. If a semantic model refreshes after a dataflow, leave enough time for the dataflow to finish, or chain them in a pipeline.

  - **Capacity:** scheduled runs consume capacity units, so very frequent schedules can contribute to throttling on small SKUs.

**Exam tip:** scheduler for a dataflow → maximum 48 refreshes per day. Run several items in sequence, or more often than the dataflow scheduler allows → pipeline.

## 3.10 Handling failures and retries

Schedulers only start the item: they do not retry it. Failure handling is configured on the activities inside a pipeline.

**Retry settings on each activity**

Open the activity and go to the **General** tab:

  - **Retry:** the number of times to retry after a failure (default 0).

  - **Retry interval (sec):** the wait between attempts (default 30 seconds).

  - **Timeout:** the maximum run time before the activity is marked as failed (default 12 hours).

**What to do when an activity fails**

  - **Dependency paths:** connect the next activity with On success, On fail, On completion or On skip. An On fail path can run a cleanup, send a notification or call a Fail activity.

  - **Notifications:** use the Office 365 Outlook or Teams activity on the failure path to alert the team.

  - **Idempotent loads:** a retry runs the step again, so write it to be safe to repeat (for example the stored procedure that deletes one day and reinserts it, as in 5.4).

  - **Monitor:** check runs and errors in the Monitoring hub and in each item's run history.

  - **Dataflows and notebooks:** when they are called from a pipeline, the retry and timeout settings of the Dataflow or Notebook activity apply. A dataflow or notebook scheduled on its own has no automatic retry: the next scheduled run is the next attempt.

**Exam tip:** automatically re-run a failed step → Retry and Retry interval on the pipeline activity. Do something different when a step fails → On fail path. Notify on failure → Outlook or Teams activity.

## 3.11 Exam quick reference

  - Low-code transformations, Power Query, 150+ connectors → dataflow Gen2.

  - On-premises data with a low-code tool → dataflow (or pipeline) with the on-premises data gateway.

  - Upload a static local file → dataflow.

  - Dataflow slow on large data → enable Fast Copy, or use a pipeline.

  - Orchestration, control flow, large copy, triggering other items → data pipeline (Copy data activity).

  - API extraction, client libraries, data validation, most CU-efficient → notebook.

  - Destination is a Data Warehouse → not a notebook (per the course).

  - Data in S3, ADLS, Google Cloud Storage or Dataverse without copying → external shortcut.

  - Data in another Lakehouse, Warehouse or KQL database without copying → internal shortcut.

  - A shortcut points to a file or a folder, and is created in a Lakehouse or KQL database.

  - Shortcut in Tables → top level only; a Delta target is recognized as a table (Spark and SQL endpoint). Shortcut in Files → any level, not registered as a table. External Delta table created with Spark, to be queried in SQL → shortcut in Tables.

  - Admin, Member and Contributor can create and read shortcuts and write through them; Viewer reads only through the SQL analytics endpoint (TDS).

  - Deleting a shortcut does not delete the target data.

  - Live replica of Azure SQL Database, Cosmos DB or Snowflake → database mirroring.

  - Streaming events → eventstream.

  - Dataflow Gen2 scheduler → up to 48 refreshes per day.

  - Pipelines and notebooks → scheduled by the minute, hourly, daily, weekly or monthly.

  - Automatic re-run on failure → Retry and Retry interval on the pipeline activity (defaults 0 and 30 seconds, timeout 12 hours).

  - Different action on failure → On fail dependency path; alert with Outlook or Teams activity.
