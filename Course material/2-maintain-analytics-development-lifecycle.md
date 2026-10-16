# 2 – Maintain the analytics development lifecycle

## 2.1 Configure version control for a workspace

**Key concepts**

  - > **Git:** a distributed version control system. A repository holds the project history, a branch is an isolated line of work, a commit is a saved snapshot, push and pull send and fetch changes to and from the remote, a pull request (PR) asks to merge one branch into another after review, and a merge conflict occurs when the same lines were changed in two branches.

  - > **Azure DevOps:** the Microsoft platform that hosts the Git repository (Azure Repos) and adds Boards (work items), Pipelines (CI/CD), and Artifacts. GitHub is the alternative. Fabric's Git integration supports only these two providers.

  - > **Why use it:** history and rollback, collaboration through branches and PRs, backup, audit trail. A .pbix is a binary file, so Git cannot show what changed inside it: that is why Power BI Projects (PBIP) exist.

**Fabric Git integration**

  - > **Scope:** works at the workspace level. It synchronizes item definitions between a workspace and a branch (optionally a folder) of a repository. Data is never saved in Git: for a lakehouse or warehouse only the structure is versioned.

  - > **Supported items:** among others semantic models, reports, paginated reports, notebooks, pipelines, dataflows, lakehouses, and warehouses. Not all item types are supported, so check the unsupported items before relying on Git. If the workspace or Git folder contains unsupported items, the connection still succeeds: those items are ignored (they are not saved, synchronized, or deleted) and appear in the Source control pane without being committable or updatable.

  - > **Prerequisites:** the tenant setting “Users can synchronize workspace items with their Git repositories” (and the GitHub one, if you use GitHub) must be enabled, as must “Users can create Fabric items” for Fabric items; the Azure DevOps account must belong to the same user as the Fabric account; you need access to an existing repository; the workspace must be on a Fabric capacity (or Power BI Premium, which however supports only Power BI items).

  - > **Who connects:** only a workspace admin can connect, disconnect, or change branch. Once connected, anyone with permission can work in the workspace. If an admin enables the workspace setting “Allow users with at least Contributor role to change Git branch”, Members and Contributors with write permission on all items can also switch branches or create new ones.

  - > **Connecting:** Workspace settings → Git integration → choose the provider → organization, project, repository, branch (and folder) → Connect and sync.

  - > **Two directions:** Commit sends workspace changes to the branch; Update brings branch changes into the workspace. Each item shows a status such as Synced, Uncommitted changes, Update required, Conflict, or Unsupported item.

  - > **Conflicts:** when the workspace and the branch have both modified the same item, you choose which version to keep (the Git one or the workspace one).

  - > **Branching:** Branch out creates a new workspace connected to a new branch to work in isolation on a feature; you return to the main branch with a PR in Azure DevOps and then run Update on the main workspace.

  - > **Limits:** commits up to 125 MB; Fabric's authentication must be at least as strong as Git's (for example MFA); semantic models connected to Analysis Services are not supported; sovereign clouds are not supported. Also: workspaces with template apps installed cannot be connected, submodules are not supported, the branch name can be at most 244 characters, Azure DevOps is not supported with IP Conditional Access validation enabled, and some GitHub Enterprise settings (IP allowlist, private networking) are not supported.

**Typical flow**

1.  > Connect the Dev workspace to a branch (or Branch out to a feature workspace).

2.  > Create or modify items in Fabric, or edit a PBIP locally and push it.

3.  > Commit the changes from the Source control pane to the branch.

4.  > Open a pull request in Azure DevOps, review it, and merge it into main.

5.  > Run Update on the workspace connected to main, or let a deployment pipeline promote Dev → Test → Prod.

**Exam tip:** version history, branches, and pull requests on workspace items → Git integration. Only a workspace admin connects a workspace to a repository. Git saves item definitions, never data. Supported providers: Azure DevOps and GitHub.

## 2.2 Create and manage a Power BI Desktop project (.pbip)

A PBIP saves a report as a folder of **plain text-based format files** instead of a single binary .pbix, so **Git can show line-by-line differences and merge** changes. Create one with File → Save as → Power BI Project (.pbip). Desktop creates a .gitignore file if none exists.

**Folder structure**

| Element                 | Purpose                                                                                                                                                                                                                                   |
| ----------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| \<name\>.pbip           | Entry point. Opens the report and its semantic model in Desktop. It is optional: it only serves as a shortcut.                                                                                                                            |
| \<name\>.Report/        | Report definition. definition.pbir holds the settings and the reference to the semantic model. Pages and visuals are saved in report.json (PBIR-Legacy) or in a definition/ folder of small JSON files (PBIR, better for diff and merge). |
| \<name\>.SemanticModel/ | Model definition. definition.pbism plus a definition/ folder in TMDL (one file per table) or a single model.bim in TMSL.                                                                                                                  |
| .pbi/cache.abf          | Local cache of the model data. Never commit it.                                                                                                                                                                                           |
| .pbi/localSettings.json | User-specific settings. Never commit it.                                                                                                                                                                                                  |
| .gitignore              | Excludes cache.abf and localSettings.json.                                                                                                                                                                                                |

  - > **Why PBIP:** readable, comparable text; the schema goes into Git but the data does not; report and model are in separate folders, so one model can serve several reports and both can be versioned or deployed separately.

  - > **Formats:** the report uses PBIR (one JSON file per page, visual, and bookmark, with a public schema, ideal for merges) or PBIR-Legacy (report.json); the model uses TMDL (readable text, one file per table, role, and culture) or TMSL (model.bim).

  - > **Link with Fabric:** Fabric's Git integration uses the same folder format, so a PBIP repository can be synchronized with a workspace.

## 2.3 Create and configure deployment pipelines

Instead of a single copy of the content, organizations usually use several environments, typically Development, Test, and Production. Changes are developed and verified before users see them. Deployment pipelines manage promotion between these environments.

**How deployment pipelines work**

  - > **Stages:** 2 to 10, 3 by default (Development, Test, Production). The number of stages is decided when the pipeline is created and cannot be changed afterwards.

  - > **Workspaces:** each stage is linked to a workspace, and a workspace can belong to only one pipeline stage. Workspaces must be on a Fabric capacity.

  - > **What moves:** item definitions, not data. After deploying a semantic model you must refresh it in the target stage. Lakehouse and warehouse data is not copied.

  - > **Deployment:** everything or selected items (with Select related to include dependencies), forward or backward between adjacent stages. Backward deployment is possible only to an empty stage. The compare view shows the differences between two stages before deployment.

  - > **Permissions:** a workspace admin creates the pipeline and assigns workspaces. To deploy you must be a pipeline admin and at least Contributor in both the source and target workspaces.

  - > **Automation:** deployments can also be triggered with the deployment pipelines REST APIs, for example from Azure DevOps or GitHub Actions.

**Deployment rules in detail**

  - > **Rule types:** data source rule (changes the source, that is server or database, but not the source type), parameter rule (changes a parameter value; parameters must be of type Text if used to rebind items), and default lakehouse rule (notebooks only: sets the default lakehouse in the target stage).

  - > **Supported items and sources:** rules are defined for semantic models, Gen1 dataflows, and paginated reports (data sources) and for notebooks (default lakehouse). Data source rules work for Azure Analysis Services, Azure Synapse, SQL Server Analysis Services, Azure SQL Server, SQL Server, OData, Oracle, SAP HANA (import only), SharePoint, and Teradata; for other sources use parameters.

  - > **Limitations:** to create a rule you must be the item's owner; rules cannot be created in the Development stage; the same source cannot appear in more than one rule; if the source or parameter is changed or removed in the source stage the rule is no longer valid and deployment fails; if you unassign and reassign a workspace, its rules are lost.

  - > **Direct Lake:** a Direct Lake semantic model does not rebind by itself to the target stage's items after deployment (it stays linked to the source item): use a data source rule to bind it.

**What is copied and what is not**

  - > **Copied:** definitions and metadata (model, report pages and visuals, dashboard tiles), relationships between items, data sources and parameters (with deployment rules).

  - > **Not copied in the semantic model:** role membership assignments (RLS), refresh schedule, data source credentials, and query caching settings. Data is not copied either.

  - > **Gateway:** the gateway associated with the target item is not automatically mapped to the data source: configure it manually in the item's settings.

  - > **Sensitivity labels:** copied only in specific cases (new item, empty stage, label with protection), see Apply sensitivity labels to items.

**Git integration or deployment pipeline?**

The two tools solve different problems and are usually used together.

|                          | Git integration                                       | Deployment pipeline                                       |
| ------------------------ | ----------------------------------------------------- | --------------------------------------------------------- |
| Purpose                  | Version control, collaboration, history, and rollback | Promote content between environments (release management) |
| Connection               | One workspace ↔ one branch of a repository            | Each stage ↔ one workspace                                |
| What moves               | Item definitions between workspace and Git            | Item definitions between workspaces                       |
| Per-environment settings | None (handled with branches and manual changes)       | Deployment rules (data sources and parameters)            |
| Typical use              | Developers working in parallel on the Dev workspace   | Dev → Test → Prod releases                                |

Combined pattern: Git on the Dev workspace for versioning; a deployment pipeline to promote approved content to Test and Prod.

**Exam tip:** Dev/Test/Prod with a different data source per environment → deployment pipeline with deployment rules. Version history and pull requests → Git integration.

## 2.4 Perform impact analysis of downstream dependencies from lakehouses, warehouses, dataflows, and semantic models

Before changing an item (for example altering the schema of a lakehouse table, renaming a column, or deleting a measure) you need to know which downstream items depend on it. Fabric offers two related tools: lineage view and impact analysis. They are informational tools: they show dependencies but do not block or prevent changes.

| Aspect        | Lineage view                                                                                            | Impact analysis                                                                                                      |
| ------------- | ------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| Scope         | Relationships among all items in a workspace, plus data sources outside the workspace one step upstream | Items and workspaces potentially affected downstream of an item, including in other workspaces                       |
| How to open   | Every workspace has its own lineage view (workspace view selector)                                      | From the button on the item's card in lineage view, or from the item's details page (Lineage)                        |
| What it shows | A graph of cards: items, data sources, and connections, with dependencies highlighted                   | Number of impacted items and workspaces, by type or by workspace, with the Child items and All downstream items tabs |
| Purpose       | Understand the flow of data from source to destination                                                  | Assess the risk of a change and notify the people it affects (Notify contacts)                                       |

**Performing an impact analysis**

1.  > Open the workspace and switch to the lineage view.

2.  > Find the card of the item to be changed (lakehouse, warehouse, dataflow, or semantic model).

3.  > Select the impact analysis button on the card (or open it from the item's details page).

4.  > Switch from Child items (direct children, one step downstream) to All downstream items and compare the by-type and by-workspace views.

5.  > If the change is made or planned, use Notify contacts to alert the contacts of the affected workspaces.

## 2.5 Deploy and manage semantic models by using the XMLA endpoint

There are two ways to **create and manage a semantic model**: inside the workspace (Power BI Desktop and the service) or with a **third-party tool such as Tabular Editor**, then **deploying it through the XMLA endpoint**. The endpoint exposes the workspace's semantic models as an Analysis Services instance, so any Analysis Services client can connect.

**Requirements**

  - > The workspace must be on a Fabric (F), Power BI Premium (P), Embedded (A/EM), or Premium Per User capacity. A Pro license alone is not enough.

  - > The **XMLA endpoint must be set to Read Write at the capacity level** (Admin portal → Capacity settings → Power BI workloads → XMLA Endpoint). Read Only allows queries only. Older documentation indicates read-only as the default, but newer capacities have read/write enabled by default: if a write fails, check this setting first.

  - > The tenant setting “**Allow XMLA endpoints and Analyze in Excel with on-premises semantic models**” must be enabled.

  - > The user must have write permission on the model in the workspace. Automated or CI/CD deployments use a service principal.

**Connecting and deploying**

1.  > In Workspace settings, copy the workspace connection link (format powerbi://api.powerbi.com/v1.0/myorg/\<workspace name\>).

2.  > Open Tabular Editor, SSMS, or DAX Studio and use the link as the server name; sign in with your Microsoft Entra ID account.

3.  > Open or create the model (for example from a model.bim or a TMDL folder) and edit it.

4.  > Deploy it to the workspace (in Tabular Editor: Model → Deploy, with the workspace link as the destination).

5.  > Refresh the model in the service. Deployment sends metadata, not data.

Connection string for a single model (Initial Catalog = model name):

`Data Source=powerbi://api.powerbi.com/v1.0/myorg/Workspace Name;Initial Catalog=SalesModel;`

TMSL script (SSMS, XMLA query window): full refresh of a single partition.

`{`

`   "refresh": { `

`     "type": "full", `

`     "objects": [ `

`       { "database": "SalesModel", "table": "FactSales", "partition": "FactSales_2026" } `

`     ] `

`   } `

`}`

  - > **Authentication:** Microsoft Entra ID account; for automation a service principal. The service principal must have the same permissions on the workspace or model as a regular user, be enabled in the tenant settings to use the APIs, and, in SSMS or connection strings, is specified in the format app:\<appId\>@\<tenantId\>.

  - > **XMLA or publishing from Desktop:** Desktop publishes the .pbix file (model, report, and data) and overwrites the model in the service; the XMLA endpoint deploys only the model metadata and allows selective deployments and advanced management features.

**Watch out**

  - > **Features that Desktop does not offer (calculation groups, perspectives, partitions, translations, object-level security) can be created through the XMLA endpoint**.

  - > Once a model has been written through XMLA, **it can no longer be downloaded from the service as a .pbix**. Keep the source in a PBIP/Git repository.

  - > Direct Lake models are created and edited in the service or through the XMLA endpoint.

## 2.6 Create and update reusable assets, including Power BI template (.pbit) files, Power BI data source (.pbids) files, and shared semantic models

Power BI uses several file types and reusable assets, each with a different purpose.

| Format                | What it is                                                                                           | When to use it                                                          |
| --------------------- | ---------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| .pbix                 | Report, semantic model, and data in a single binary file.                                            | Standard authoring and publishing. Not suitable for Git.                |
| .pbip                 | A folder of text files for the report and model (see Create and manage a Power BI Desktop project).  | Version control, CI/CD, team development.                               |
| .pbit                 | Template: report pages, model, queries, and measures, but no data.                                   | A reusable starting point that keeps reports consistent and saves time. |
| .pbids                | Power BI data source file: a small JSON file with the connection details of a single data source.    | Give users a ready-made connection to a standard source.                |
| Shared semantic model | Not a file. A semantic model that is published and reused by many reports through a live connection. | One governed model, many reports.                                       |

**.pbit: Power BI template**

  - > **Creation:** save a .pbix as a template with File → Export → Power BI template (you can add a description). On opening, Desktop asks for parameter values (for example server name or date range) and then loads the data. The template contains no data, so it is small and safe to share.

  - > **Updating:** open the .pbit, edit it, re-export it, and redistribute it. Reports already created from the template do not change: the template is a starting point, not a link.

  - > **Not to be confused with template apps:** a template app is a package created in the service to distribute content to external customers (for example through AppSource); a workspace with a template app installed cannot be connected to Git.

**.pbids: Power BI data source**

  - > **Content:** it contains the protocol, the address (server and database or URL), and the connection mode (Import or DirectQuery). It contains no data or credentials and describes a single data source. Opening it launches Power BI Desktop directly at the connection step, so users only need to sign in.

  - > **Creation:** from Data source settings → Export PBIDS, or by writing the JSON by hand.

  - > **Updating:** if the server or database changes, edit the JSON and redistribute the file; reports already created are not touched.

**How updates propagate**

| Asset                 | What is reused                                                           | What happens when it is updated                                                           |
| --------------------- | ------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------- |
| .pbit                 | Report and model structure (queries, measures, parameters), without data | Independent copy: updating the template does not change reports already created           |
| .pbids                | Only the connection to a data source                                     | No link: each user has their own file; if the source changes, a new .pbids is distributed |
| Shared semantic model | Single model and data, with RLS                                          | Live link: every change is visible in all linked reports                                  |

**Exam tip:** reusable layout and model without data, with parameters → .pbit. Preconfigured connection to a source → .pbids. One governed model for many reports → shared semantic model (live connection, Build permission). Source control → .pbip.

## 2.7 Exam quick reference

  - > Version history, branches, and pull requests on workspace items → Git integration (Azure DevOps or GitHub).

  - > Who can connect a workspace to a repository → the workspace admin.

  - > Version report and model as text → PBIP (TMDL + PBIR); add cache.abf to .gitignore.

  - > Promote Dev → Test → Prod with a different source per environment → deployment pipeline + deployment rules.

  - > Deployment pipeline stages → 2 to 10, 3 by default; fixed after creation. Deployment carries definitions, not data: the model needs a refresh.

  - > Which items break if I change a lakehouse, warehouse, dataflow, or model → impact analysis from the lineage view; notify contacts → Notify contacts.

  - > Edit calculation groups or perspectives with an external tool and deploy → XMLA endpoint (read/write).

  - > Cannot download a .pbix after an XMLA write → expected behavior.

  - > Reusable report without data, prompting for parameters → .pbit. Preset connection → .pbids. One model for many reports → shared semantic model.

  - > Automated CI/CD deployment → service principal.
