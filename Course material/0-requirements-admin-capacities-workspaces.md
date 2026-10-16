# 0 – Requirements, Admin Portal, Capacities, Workspaces and Roles

## 0.1 Planning capacities

**What determines the number of capacities?**

  - **By department:** one capacity per department or business unit, so each team's usage and cost are separate and one team cannot throttle another.

  - **By workload or environment:** separate capacities for dev/test and production (or heavy ETL vs reporting), so heavy jobs do not slow down reports.

  - **By region:** one capacity per region when data must stay in a specific geography. The capacity region decides where the data is stored.

**And the size (SKU)?**

  - **Data and workload intensity:** data volume, number of users and how often the data is refreshed (for example a daily refresh).

  - **Heavy transformations:** Spark jobs and large ETL consume many CUs.

  - **ML training:** needs a lot of compute, usually for short periods.

  - **Urgency:** if everything must be refreshed at the same time (for example all data ready every morning), peak consumption is higher, so a larger SKU is needed. Spreading refresh schedules lowers the peak.

  - **Budget:** the larger the SKU, the higher the cost. Start from the requirements, then check the cost; pay-as-you-go with pause or a reservation can reduce it.

**Features by SKU:** many features open up from F64: free viewers (Power BI Premium features) and, in the course, **Copilot**. Microsoft has since extended Copilot to smaller paid SKUs, so check the current documentation.

**Exam tip:** number of capacities → driven by department, environment (dev/prod) and region. Size → data volume, Spark and ML intensity, refresh timing and budget.

## 0.2 Data ingestion requirements

Choose the ingestion item that matches the source and the need.

| Item               | What it does                                        | Sources and typical use                                                         |
| ------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------- |
| Shortcut           | Points to data where it is. No copy.                | ADLS Gen2, Amazon S3, Google Cloud Storage, Dataverse, other OneLake locations. |
| Database mirroring | Continuously replicates a database into OneLake.    | Azure SQL Database, Azure Cosmos DB, Snowflake.                                 |
| Dataflow Gen2      | Low-code Power Query ETL with 150+ connectors.      | Transform and load data. Combine with a pipeline when you need orchestration.   |
| Data pipeline      | Orchestration plus the Copy activity (ETL/ELT).     | Large copies, control flow, triggering other items.                             |
| Notebook           | Code-based ETL (PySpark, Python, Spark SQL, Scala). | APIs, custom logic, data validation.                                            |
| Eventstream        | Captures and routes real-time events.               | Streaming sources into a KQL database or a lakehouse.                           |

**Exam tip:** no copy → shortcut. Live replica of a database → mirroring. Low-code transformations → dataflow. Orchestration or large copy → pipeline. Custom code → notebook. Streaming events → eventstream. The course slides comparing dataflow, pipeline and notebook are in the Appendix.

## 0.3 Securing data access and moving data

These features come up in exam questions about how data is secured and moved.

**Gateways**

| Gateway                             | Use it for                                                                                                 | Setup                                                                                                                                                                        |
| ----------------------------------- | ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| On-premises data gateway            | Reaching on-premises sources such as SQL Server from Fabric.                                               | Install the gateway on an on-premises server → create an on-premises gateway connection in Fabric → use the connection in a dataflow or pipeline.                            |
| Virtual network (VNet) data gateway | Reaching data sources protected inside an Azure virtual network. Managed by Microsoft, nothing to install. | In Azure: register the Microsoft.PowerPlatform resource provider, set up the virtual network and create a subnet for the gateway → then create the VNet gateway from Fabric. |

**Exam tip:** on-premises SQL → on-premises data gateway (installed by you). Source inside an Azure virtual network → VNet data gateway (no installation).

**Fast Copy and staging**

  - **Fast Copy:** speeds up the ingestion of large data volumes in dataflows and copy activities. Use it for medium-to-large data; it brings no benefit on small loads (it applies above roughly 100 MB of files or 5 million database rows).

  - **Staging:** intermediate storage where dataflows and copy activities land data before it is transformed or loaded into the destination. It helps with large data and heavy transformations, but adds overhead on small loads.

**Exam tip:** moving large data → Fast Copy. Landing data before loading it → staging.

## 0.4 Data storage requirements

The first deciding factor is the type of data: structured or unstructured. The second is real-time need. The third is the skill set (Spark, T-SQL or KQL).

| Store        | Data                                                             | Language / engine                                                                       | Choose it when                                    |
| ------------ | ---------------------------------------------------------------- | --------------------------------------------------------------------------------------- | ------------------------------------------------- |
| Lakehouse    | Structured, semi-structured and unstructured (files and tables). | Spark (PySpark, Spark SQL, Scala, R). The SQL analytics endpoint gives read-only T-SQL. | Data engineering, ETL, files and tables together. |
| Warehouse    | Structured, relational.                                          | T-SQL (read and write).                                                                 | SQL-skilled teams, relational data warehouse.     |
| KQL database | Real-time and streaming data, time series, logs.                 | KQL.                                                                                    | Streaming and real-time analytics.                |

**Exam tip:** files or unstructured data → lakehouse. Streaming and real time → KQL database only. Relational with T-SQL → warehouse. Spark, Spark SQL and Scala → lakehouse.

## 0.5 Fabric admin portal

  - **Access:** you need a Fabric license and one of these Entra ID roles: Global Administrator, Fabric Administrator or Power Platform Administrator. Nobody else can open it.

  - **Tenant settings:** the main page. Each switch can be turned on for the whole organization or only for specific security groups (with exceptions).

  - **Other areas:** capacity settings, workspaces, usage and audit information.

**Tenant settings to remember**

  - Users can create Fabric items.

  - Create workspaces.

  - Manage guest users (external sharing).

  - Block public internet access.

  - Service principals can use Fabric APIs.

  - Git integration: users can synchronize workspace items with their Git repositories.

  - Copilot: users can use Copilot and other features powered by Azure OpenAI.

**Exam tip:** “only some people may create workspaces or use Copilot” → enable the tenant setting for a specific security group. “Automation with a service principal” → enable service principal access to Fabric APIs.

## 0.6 Administration levels

Fabric administration is split across three levels. Each has its own admin role and its own place to manage it.

| Level     | Administrator   | Role required                                                                                                                                             | Where admin happens                                      |
| --------- | --------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------- |
| Tenant    | Tenant admin    | Entra ID role of Global Administrator, Power Platform Administrator or Fabric Administrator                                                               | Fabric Admin portal → Tenant settings                    |
| Capacity  | Capacity admin  | Assigned in Azure when provisioning the capacity (must be a person or service principal in the Entra ID tenant); can be updated later in the Azure portal | Azure portal and Fabric Admin portal → Capacity settings |
| Workspace | Workspace admin | Person or group with the workspace role Admin                                                                                                             | Workspace settings (inside the workspace)                |

**Exam tip:** tenant settings = Fabric Admin portal; capacity = Azure + Admin portal; workspace = workspace settings. Each level only manages what is inside it.

## 0.7 Capacity administration

A capacity can be managed in two places: the **Azure portal** (it is an Azure resource) and the **Fabric Admin portal → Capacity settings**.

| Task                                                                    | Azure portal | Fabric capacity settings |
| ----------------------------------------------------------------------- | ------------ | ------------------------ |
| Create a new capacity                                                   | Yes          | –                        |
| Delete the capacity                                                     | Yes          | –                        |
| Change the size (scale up/down)                                         | Yes          | –                        |
| Pause / resume                                                          | Yes          | –                        |
| Change capacity admins                                                  | Yes          | Yes                      |
| View capacity usage (Capacity Metrics app)                              | –            | Yes                      |
| Define who can create workspaces in the capacity and who administers it | –            | Yes                      |
| Assign workspaces to the capacity                                       | –            | Yes                      |
| Update Power BI connection / workload settings                          | –            | Yes                      |

**Rule of thumb:** the Azure portal manages the capacity as a resource (lifecycle and size). Fabric capacity settings manage how the capacity is used (monitoring, access, workspace assignment).

## 0.8 Capacities and SKUs

**What a capacity is**

A capacity is a pool of compute, measured in **Capacity Units (CUs)**, shared by every Fabric workload (Power BI, Spark, Warehouse, Pipelines, Real-Time Intelligence). Workspaces are assigned to a capacity and all their items consume from it. The capacity region decides where the data is stored.

**What the SKU expresses**

  - **Size = number of CUs.** F2 = 2 CUs, F4 = 4, F8 = 8 … F64 = 64 … F2048 = 2,048. Each step doubles compute and (roughly) price.

  - **Power BI equivalence:** F64 = P1 = 8 v-cores; F128 = P2; F256 = P3; and so on.

  - **Spark:** 1 CU = 2 Spark vCores, so the SKU also caps Spark concurrency.

**SKU families**

Only the F SKUs are bought in Azure as Fabric capacities.

| Family               | Supports            | Notes                                                                    |
| -------------------- | ------------------- | ------------------------------------------------------------------------ |
| F (Fabric)           | All Fabric items    | Azure resource; pay-as-you-go (pausable) or reserved (about 40% cheaper) |
| P (Power BI Premium) | All Fabric items    | Legacy per-capacity licensing; maps to F SKUs                            |
| A / EM               | Power BI items only | Embedding scenarios; no Fabric items                                     |
| Trial                | All Fabric items    | Free, time-limited, F64-equivalent                                       |

**How to choose and assign a SKU**

  - **F64 is the licensing threshold.** Below F64, every user who views Power BI content needs a Pro or PPU license. On F64 or larger, users with a free license and a Viewer role can consume content. Authors who publish still need Pro.

  - **Data volume:** Direct Lake guardrails and semantic model memory grow with the SKU (F64: 1.5 billion rows per table, 25 GB max memory; the smallest SKUs: 300 million rows).

  - **Usage pattern:** spiky or dev/test → pay-as-you-go and pause when idle; steady 24/7 production → reservation.

  - **Throttling:** capacities can burst above their CUs and smooth the load over time. Sustained overload leads to throttling. Check the Capacity Metrics app, then scale up (in Azure) or move heavy workspaces to another capacity.

  - **Isolation:** keep dev/test and prod on separate capacities so heavy jobs don't slow down reports. Choose the capacity region for data residency.

  - **Assignment:** Workspace settings → License info → choose the capacity (needs permission on that capacity). An admin can also assign workspaces from Capacity settings.

**Exam tip:** “viewers without individual licenses” → F64 or higher. “Capacity is throttled” → scale up or split workloads. “Occasional workload, minimize cost” → pay-as-you-go + pause.

## 0.9 Installing Python packages for a whole workspace

Only a workspace admin can do this. Steps:

1.  Create an **Environment** item in the workspace.

2.  Add the libraries (public PyPI/conda packages or custom .whl files).

3.  **Save and Publish** the environment.

4.  Go to **Workspace settings → Spark settings → Environment** and set it as the **default environment**.

Alternatives: attach an environment to a single notebook, or use inline %pip install (session-only, not persisted).

## 0.10 Exam quick reference

  - Number of capacities → department, workload (dev/prod) and region.

  - Size of a capacity → data volume, Spark and ML intensity, refresh timing, budget.

  - Use ADLS Gen2, S3 or Dataverse data without copying → **shortcut**.

  - Continuously replicate Azure SQL, Cosmos DB or Snowflake → **database mirroring**.

  - Real-time events → **eventstream** into a KQL database.

  - On-premises SQL source → **on-premises data gateway**. Source in an Azure virtual network → **VNet data gateway**.

  - Unstructured files → **lakehouse**. T-SQL warehouse → **warehouse**. Streaming → **KQL database**.

  - Who opens the admin portal → Global, Fabric or Power Platform administrator.

  - Restrict who can create workspaces → tenant setting limited to a security group.
