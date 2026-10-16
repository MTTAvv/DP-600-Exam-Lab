# Exam Topics Questions

@thatonecodes

## Exam DP-600 topic 1 question 1 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 1
Topic #: 1

[All DP-600 Questions]

Case study -This is a case study. Case studies are not timed separately. You can use as much exam time as you would like to complete each case. However, there may be additional case studies and sections on this exam. You must manage your time to ensure that you are able to complete all questions included on this exam in the time provided.To answer the questions included in a case study, you will need to reference information that is provided in the case study. Case studies might contain exhibits and other resources that provide more information about the scenario that is described in the case study. Each question is independent of the other questions in this case study.At the end of this case study, a review screen will appear. This screen allows you to review your answers and to make changes before you move to the next section of the exam. After you begin a new section, you cannot return to this section.To start the case study -To display the first question in this case study, click the Next button. Use the buttons in the left pane to explore the content of the case study before you answer the questions. Clicking these buttons displays information such as business requirements, existing environment, and problem statements. If the case study has an All Information tab, note that the information displayed is identical to the information displayed on the subsequent tabs. When you are ready to answer a question, click the Question button to return to the question.Overview -Contoso, Ltd. is a US-based health supplements company. Contoso has two divisions named Sales and Research. The Sales division contains two departments named Online Sales and Retail Sales. The Research division assigns internally developed product lines to individual teams of researchers and analysts.Existing Environment -Identity Environment -Contoso has a Microsoft Entra tenant named contoso.com. The tenant contains two groups named ResearchReviewersGroup1 and ResearchReviewersGroup2.Data Environment -Contoso has the following data environment:The Sales division uses a Microsoft Power BI Premium capacity.The semantic model of the Online Sales department includes a fact table named Orders that uses Import made. In the system of origin, the OrderID value represents the sequence in which orders are created.The Research department uses an on-premises, third-party data warehousing product.Fabric is enabled for contoso.com.An Azure Data Lake Storage Gen2 storage account named storage1 contains Research division data for a product line named Productline1. The data is in the delta format.A Data Lake Storage Gen2 storage account named storage2 contains Research division data for a product line named Productline2. The data is in the CSV format.Requirements -Planned Changes -Contoso plans to make the following changes:Enable support for Fabric in the Power BI Premium capacity used by the Sales division.Make all the data for the Sales division and the Research division available in Fabric.For the Research division, create two Fabric workspaces named Productline1ws and Productine2ws.In Productline1ws, create a lakehouse named Lakehouse1.In Lakehouse1, create a shortcut to storage1 named ResearchProduct.Data Analytics Requirements -Contoso identifies the following data analytics requirements:All the workspaces for the Sales division and the Research division must support all Fabric experiences.The Research division workspaces must use a dedicated, on-demand capacity that has per-minute billing.The Research division workspaces must be grouped together logically to support OneLake data hub filtering based on the department name.For the Research division workspaces, the members of ResearchReviewersGroup1 must be able to read lakehouse and warehouse data and shortcuts by using SQL endpoints.For the Research division workspaces, the members of ResearchReviewersGroup2 must be able to read lakehouse data by using Lakehouse explorer.All the semantic models and reports for the Research division must use version control that supports branching.Data Preparation Requirements -Contoso identifies the following data preparation requirements:The Research division data for Productline1 must be retrieved from Lakehouse1 by using Fabric notebooks.All the Research division data in the lakehouses must be presented as managed tables in Lakehouse explorer.Semantic Model Requirements -Contoso identifies the following requirements for implementing and managing semantic models:The number of rows added to the Orders table during refreshes must be minimized.The semantic models in the Research division workspaces must use Direct Lake mode.General Requirements -Contoso identifies the following high-level requirements that must be considered for all solutions:Follow the principle of least privilege when applicable.Minimize implementation and maintenance effort when possible.You need to ensure that Contoso can use version control to meet the data analytics requirements and the general requirements.What should you do? 
Suggested Answer: C 🗳️ 

A. Store at the semantic models and reports in Data Lake Gen2 storage.

B. Modify the settings of the Research workspaces to use a GitHub repository.

C. Modify the settings of the Research division workspaces to use an Azure Repos repository.

D. Store all the semantic models and reports in Microsoft OneDrive.

**Answer: C**

**Timestamp: Feb. 8, 2024, 6:36 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/133398-exam-dp-600-topic-1-question-1-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 2 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 2
Topic #: 1

[All DP-600 Questions]

HOTSPOT -Case study -This is a case study. Case studies are not timed separately. You can use as much exam time as you would like to complete each case. However, there may be additional case studies and sections on this exam. You must manage your time to ensure that you are able to complete all questions included on this exam in the time provided.To answer the questions included in a case study, you will need to reference information that is provided in the case study. Case studies might contain exhibits and other resources that provide more information about the scenario that is described in the case study. Each question is independent of the other questions in this case study.At the end of this case study, a review screen will appear. This screen allows you to review your answers and to make changes before you move to the next section of the exam. After you begin a new section, you cannot return to this section.To start the case study -To display the first question in this case study, click the Next button. Use the buttons in the left pane to explore the content of the case study before you answer the questions. Clicking these buttons displays information such as business requirements, existing environment, and problem statements. If the case study has an All Information tab, note that the information displayed is identical to the information displayed on the subsequent tabs. When you are ready to answer a question, click the Question button to return to the question.Overview -Contoso, Ltd. is a US-based health supplements company. Contoso has two divisions named Sales and Research. The Sales division contains two departments named Online Sales and Retail Sales. The Research division assigns internally developed product lines to individual teams of researchers and analysts.Existing Environment -Identity Environment -Contoso has a Microsoft Entra tenant named contoso.com. The tenant contains two groups named ResearchReviewersGroup1 and ResearchReviewersGroup2.Data Environment -Contoso has the following data environment:The Sales division uses a Microsoft Power BI Premium capacity.The semantic model of the Online Sales department includes a fact table named Orders that uses Import made. In the system of origin, the OrderID value represents the sequence in which orders are created.The Research department uses an on-premises, third-party data warehousing product.Fabric is enabled for contoso.com.An Azure Data Lake Storage Gen2 storage account named storage1 contains Research division data for a product line named Productline1. The data is in the delta format.A Data Lake Storage Gen2 storage account named storage2 contains Research division data for a product line named Productline2. The data is in the CSV format.Requirements -Planned Changes -Contoso plans to make the following changes:Enable support for Fabric in the Power BI Premium capacity used by the Sales division.Make all the data for the Sales division and the Research division available in Fabric.For the Research division, create two Fabric workspaces named Productline1ws and Productine2ws.In Productline1ws, create a lakehouse named Lakehouse1.In Lakehouse1, create a shortcut to storage1 named ResearchProduct.Data Analytics Requirements -Contoso identifies the following data analytics requirements:All the workspaces for the Sales division and the Research division must support all Fabric experiences.The Research division workspaces must use a dedicated, on-demand capacity that has per-minute billing.The Research division workspaces must be grouped together logically to support OneLake data hub filtering based on the department name.For the Research division workspaces, the members of ResearchReviewersGroup1 must be able to read lakehouse and warehouse data and shortcuts by using SQL endpoints.For the Research division workspaces, the members of ResearchReviewersGroup2 must be able to read lakehouse data by using Lakehouse explorer.All the semantic models and reports for the Research division must use version control that supports branching.Data Preparation Requirements -Contoso identifies the following data preparation requirements:The Research division data for Productline1 must be retrieved from Lakehouse1 by using Fabric notebooks.All the Research division data in the lakehouses must be presented as managed tables in Lakehouse explorer.Semantic Model Requirements -Contoso identifies the following requirements for implementing and managing semantic models:The number of rows added to the Orders table during refreshes must be minimized.The semantic models in the Research division workspaces must use Direct Lake mode.General Requirements -Contoso identifies the following high-level requirements that must be considered for all solutions:Follow the principle of least privilege when applicable.Minimize implementation and maintenance effort when possible.You need to recommend a solution to group the Research division workspaces.What should you include in the recommendation? To answer, select the appropriate options in the answer area.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: Feb. 9, 2024, 1:41 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/133443-exam-dp-600-topic-1-question-2-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 3 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 3
Topic #: 1

[All DP-600 Questions]

Case study -This is a case study. Case studies are not timed separately. You can use as much exam time as you would like to complete each case. However, there may be additional case studies and sections on this exam. You must manage your time to ensure that you are able to complete all questions included on this exam in the time provided.To answer the questions included in a case study, you will need to reference information that is provided in the case study. Case studies might contain exhibits and other resources that provide more information about the scenario that is described in the case study. Each question is independent of the other questions in this case study.At the end of this case study, a review screen will appear. This screen allows you to review your answers and to make changes before you move to the next section of the exam. After you begin a new section, you cannot return to this section.To start the case study -To display the first question in this case study, click the Next button. Use the buttons in the left pane to explore the content of the case study before you answer the questions. Clicking these buttons displays information such as business requirements, existing environment, and problem statements. If the case study has an All Information tab, note that the information displayed is identical to the information displayed on the subsequent tabs. When you are ready to answer a question, click the Question button to return to the question.Overview -Contoso, Ltd. is a US-based health supplements company. Contoso has two divisions named Sales and Research. The Sales division contains two departments named Online Sales and Retail Sales. The Research division assigns internally developed product lines to individual teams of researchers and analysts.Existing Environment -Identity Environment -Contoso has a Microsoft Entra tenant named contoso.com. The tenant contains two groups named ResearchReviewersGroup1 and ResearchReviewersGroup2.Data Environment -Contoso has the following data environment:The Sales division uses a Microsoft Power BI Premium capacity.The semantic model of the Online Sales department includes a fact table named Orders that uses Import made. In the system of origin, the OrderID value represents the sequence in which orders are created.The Research department uses an on-premises, third-party data warehousing product.Fabric is enabled for contoso.com.An Azure Data Lake Storage Gen2 storage account named storage1 contains Research division data for a product line named Productline1. The data is in the delta format.A Data Lake Storage Gen2 storage account named storage2 contains Research division data for a product line named Productline2. The data is in the CSV format.Requirements -Planned Changes -Contoso plans to make the following changes:Enable support for Fabric in the Power BI Premium capacity used by the Sales division.Make all the data for the Sales division and the Research division available in Fabric.For the Research division, create two Fabric workspaces named Productline1ws and Productine2ws.In Productline1ws, create a lakehouse named Lakehouse1.In Lakehouse1, create a shortcut to storage1 named ResearchProduct.Data Analytics Requirements -Contoso identifies the following data analytics requirements:All the workspaces for the Sales division and the Research division must support all Fabric experiences.The Research division workspaces must use a dedicated, on-demand capacity that has per-minute billing.The Research division workspaces must be grouped together logically to support OneLake data hub filtering based on the department name.For the Research division workspaces, the members of ResearchReviewersGroup1 must be able to read lakehouse and warehouse data and shortcuts by using SQL endpoints.For the Research division workspaces, the members of ResearchReviewersGroup2 must be able to read lakehouse data by using Lakehouse explorer.All the semantic models and reports for the Research division must use version control that supports branching.Data Preparation Requirements -Contoso identifies the following data preparation requirements:The Research division data for Productline1 must be retrieved from Lakehouse1 by using Fabric notebooks.All the Research division data in the lakehouses must be presented as managed tables in Lakehouse explorer.Semantic Model Requirements -Contoso identifies the following requirements for implementing and managing semantic models:The number of rows added to the Orders table during refreshes must be minimized.The semantic models in the Research division workspaces must use Direct Lake mode.General Requirements -Contoso identifies the following high-level requirements that must be considered for all solutions:Follow the principle of least privilege when applicable.Minimize implementation and maintenance effort when possible.You need to refresh the Orders table of the Online Sales department. The solution must meet the semantic model requirements.What should you include in the solution? 
Suggested Answer: D 🗳️ 

A. an Azure Data Factory pipeline that executes a Stored procedure activity to retrieve the maximum value of the OrderID column in the destination lakehouse

B. an Azure Data Factory pipeline that executes a Stored procedure activity to retrieve the minimum value of the OrderID column in the destination lakehouse

C. an Azure Data Factory pipeline that executes a dataflow to retrieve the minimum value of the OrderID column in the destination lakehouse

D. an Azure Data Factory pipeline that executes a dataflow to retrieve the maximum value of the OrderID column in the destination lakehouse

**Answer: D**

**Timestamp: Feb. 9, 2024, 1:46 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/133444-exam-dp-600-topic-1-question-3-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 4 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 4
Topic #: 1

[All DP-600 Questions]

Case study -This is a case study. Case studies are not timed separately. You can use as much exam time as you would like to complete each case. However, there may be additional case studies and sections on this exam. You must manage your time to ensure that you are able to complete all questions included on this exam in the time provided.To answer the questions included in a case study, you will need to reference information that is provided in the case study. Case studies might contain exhibits and other resources that provide more information about the scenario that is described in the case study. Each question is independent of the other questions in this case study.At the end of this case study, a review screen will appear. This screen allows you to review your answers and to make changes before you move to the next section of the exam. After you begin a new section, you cannot return to this section.To start the case study -To display the first question in this case study, click the Next button. Use the buttons in the left pane to explore the content of the case study before you answer the questions. Clicking these buttons displays information such as business requirements, existing environment, and problem statements. If the case study has an All Information tab, note that the information displayed is identical to the information displayed on the subsequent tabs. When you are ready to answer a question, click the Question button to return to the question.Overview -Contoso, Ltd. is a US-based health supplements company. Contoso has two divisions named Sales and Research. The Sales division contains two departments named Online Sales and Retail Sales. The Research division assigns internally developed product lines to individual teams of researchers and analysts.Existing Environment -Identity Environment -Contoso has a Microsoft Entra tenant named contoso.com. The tenant contains two groups named ResearchReviewersGroup1 and ResearchReviewersGroup2.Data Environment -Contoso has the following data environment:The Sales division uses a Microsoft Power BI Premium capacity.The semantic model of the Online Sales department includes a fact table named Orders that uses Import made. In the system of origin, the OrderID value represents the sequence in which orders are created.The Research department uses an on-premises, third-party data warehousing product.Fabric is enabled for contoso.com.An Azure Data Lake Storage Gen2 storage account named storage1 contains Research division data for a product line named Productline1. The data is in the delta format.A Data Lake Storage Gen2 storage account named storage2 contains Research division data for a product line named Productline2. The data is in the CSV format.Requirements -Planned Changes -Contoso plans to make the following changes:Enable support for Fabric in the Power BI Premium capacity used by the Sales division.Make all the data for the Sales division and the Research division available in Fabric.For the Research division, create two Fabric workspaces named Productline1ws and Productine2ws.In Productline1ws, create a lakehouse named Lakehouse1.In Lakehouse1, create a shortcut to storage1 named ResearchProduct.Data Analytics Requirements -Contoso identifies the following data analytics requirements:All the workspaces for the Sales division and the Research division must support all Fabric experiences.The Research division workspaces must use a dedicated, on-demand capacity that has per-minute billing.The Research division workspaces must be grouped together logically to support OneLake data hub filtering based on the department name.For the Research division workspaces, the members of ResearchReviewersGroup1 must be able to read lakehouse and warehouse data and shortcuts by using SQL endpoints.For the Research division workspaces, the members of ResearchReviewersGroup2 must be able to read lakehouse data by using Lakehouse explorer.All the semantic models and reports for the Research division must use version control that supports branching.Data Preparation Requirements -Contoso identifies the following data preparation requirements:The Research division data for Productline1 must be retrieved from Lakehouse1 by using Fabric notebooks.All the Research division data in the lakehouses must be presented as managed tables in Lakehouse explorer.Semantic Model Requirements -Contoso identifies the following requirements for implementing and managing semantic models:The number of rows added to the Orders table during refreshes must be minimized.The semantic models in the Research division workspaces must use Direct Lake mode.General Requirements -Contoso identifies the following high-level requirements that must be considered for all solutions:Follow the principle of least privilege when applicable.Minimize implementation and maintenance effort when possible.Which syntax should you use in a notebook to access the Research division data for Productline1? 
Suggested Answer: B 🗳️ 

A. spark.read.format(“delta”).load(“Tables/productline1/ResearchProduct”)

B. spark.sql(“SELECT * FROM Lakehouse1.ResearchProduct ”)

C. external_table(‘Tables/ResearchProduct)

D. external_table(ResearchProduct)

**Answer: B**

**Timestamp: Feb. 17, 2024, 10:44 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/134088-exam-dp-600-topic-1-question-4-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 5 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 5
Topic #: 1

[All DP-600 Questions]

HOTSPOT -Case study -This is a case study. Case studies are not timed separately. You can use as much exam time as you would like to complete each case. However, there may be additional case studies and sections on this exam. You must manage your time to ensure that you are able to complete all questions included on this exam in the time provided.To answer the questions included in a case study, you will need to reference information that is provided in the case study. Case studies might contain exhibits and other resources that provide more information about the scenario that is described in the case study. Each question is independent of the other questions in this case study.At the end of this case study, a review screen will appear. This screen allows you to review your answers and to make changes before you move to the next section of the exam. After you begin a new section, you cannot return to this section.To start the case study -To display the first question in this case study, click the Next button. Use the buttons in the left pane to explore the content of the case study before you answer the questions. Clicking these buttons displays information such as business requirements, existing environment, and problem statements. If the case study has an All Information tab, note that the information displayed is identical to the information displayed on the subsequent tabs. When you are ready to answer a question, click the Question button to return to the question.Overview -Litware, Inc. is a manufacturing company that has offices throughout North America. The analytics team at Litware contains data engineers, analytics engineers, data analysts, and data scientists.Existing Environment -Fabric Environment -Litware has been using a Microsoft Power BI tenant for three years. Litware has NOT enabled any Fabric capacities and features.Available Data -Litware has data that must be analyzed as shown in the following table.The Product data contains a single table and the following columns.The customer satisfaction data contains the following tables:Survey -Question -Response -For each survey submitted, the following occurs:One row is added to the Survey table.One row is added to the Response table for each question in the survey.The Question table contains the text of each survey question. The third question in each survey response is an overall satisfaction score. Customers can submit a survey after each purchase.User Problems -The analytics team has large volumes of data, some of which is semi-structured. The team wants to use Fabric to create a new data store.Product data is often classified into three pricing groups: high, medium, and low. This logic is implemented in several databases and semantic models, but the logic does NOT always match across implementations.Requirements -Planned Changes -Litware plans to enable Fabric features in the existing tenant. The analytics team will create a new data store as a proof of concept (PoC). The remaining Liware users will only get access to the Fabric features once the PoC is complete. The PoC will be completed by using a Fabric trial capacityThe following three workspaces will be created:AnalyticsPOC: Will contain the data store, semantic models, reports pipelines, dataflow, and notebooks used to populate the data storeDataEngPOC: Will contain all the pipelines, dataflows, and notebooks used to populate OneLakeDataSciPOC: Will contain all the notebooks and reports created by the data scientistsThe following will be created in the AnalyticsPOC workspace:A data store (type to be decided)A custom semantic model -A default semantic model -Interactive reports -The data engineers will create data pipelines to load data to OneLake either hourly or daily depending on the data source. The analytics engineers will create processes to ingest, transform, and load the data to the data store in the AnalyticsPOC workspace daily. Whenever possible, the data engineers will use low-code tools for data ingestion. The choice of which data cleansing and transformation tools to use will be at the data engineers’ discretion.All the semantic models and reports in the Analytics POC workspace will use the data store as the sole data source.Technical Requirements -The data store must support the following:Read access by using T-SQL or PythonSemi-structured and unstructured dataRow-level security (RLS) for users executing T-SQL queriesFiles loaded by the data engineers to OneLake will be stored in the Parquet format and will meet Delta Lake specifications.Data will be loaded without transformation in one area of the AnalyticsPOC data store. The data will then be cleansed, merged, and transformed into a dimensional modelThe data load process must ensure that the raw and cleansed data is updated completely before populating the dimensional modelThe dimensional model must contain a date dimension. There is no existing data source for the date dimension. The Litware fiscal year matches the calendar year. The date dimension must always contain dates from 2010 through the end of the current year.The product pricing group logic must be maintained by the analytics engineers in a single location. The pricing group data must be made available in the data store for T-SOL. queries and in the default semantic model. The following logic must be used:List prices that are less than or equal to 50 are in the low pricing group.List prices that are greater than 50 and less than or equal to 1,000 are in the medium pricing group.List prices that are greater than 1,000 are in the high pricing group.Security Requirements -Only Fabric administrators and the analytics team must be able to see the Fabric items created as part of the PoC.Litware identifies the following security requirements for the Fabric items in the AnalyticsPOC workspace:Fabric administrators will be the workspace administrators.The data engineers must be able to read from and write to the data store. No access must be granted to datasets or reports.The analytics engineers must be able to read from, write to, and create schemas in the data store. They also must be able to create and share semantic models with the data analysts and view and modify all reports in the workspace.The data scientists must be able to read from the data store, but not write to it. They will access the data by using a Spark notebookThe data analysts must have read access to only the dimensional model objects in the data store. They also must have access to create Power BI reports by using the semantic models created by the analytics engineers.The date dimension must be available to all users of the data store.The principle of least privilege must be followed.Both the default and custom semantic models must include only tables or views from the dimensional model in the data store. Litware already has the following Microsoft Entra security groups:FabricAdmins: Fabric administratorsAnalyticsTeam: All the members of the analytics teamDataAnalysts: The data analysts on the analytics teamDataScientists: The data scientists on the analytics teamDataEngineers: The data engineers on the analytics teamAnalyticsEngineers: The analytics engineers on the analytics teamReport Requirements -The data analysts must create a customer satisfaction report that meets the following requirements:Enables a user to select a product to filter customer survey responses to only those who have purchased that product.Displays the average overall satisfaction score of all the surveys submitted during the last 12 months up to a selected dat.Shows data as soon as the data is updated in the data store.Ensures that the report and the semantic model only contain data from the current and previous year.Ensures that the report respects any table-level security specified in the source data store.Minimizes the execution time of report queries.You need to assign permissions for the data store in the AnalyticsPOC workspace. The solution must meet the security requirements.Which additional permissions should you assign when you share the data store? To answer, select the appropriate options in the answer area.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: Feb. 12, 2024, 4:19 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/133620-exam-dp-600-topic-1-question-5-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 6 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 6
Topic #: 1

[All DP-600 Questions]

HOTSPOT -Case study -This is a case study. Case studies are not timed separately. You can use as much exam time as you would like to complete each case. However, there may be additional case studies and sections on this exam. You must manage your time to ensure that you are able to complete all questions included on this exam in the time provided.To answer the questions included in a case study, you will need to reference information that is provided in the case study. Case studies might contain exhibits and other resources that provide more information about the scenario that is described in the case study. Each question is independent of the other questions in this case study.At the end of this case study, a review screen will appear. This screen allows you to review your answers and to make changes before you move to the next section of the exam. After you begin a new section, you cannot return to this section.To start the case study -To display the first question in this case study, click the Next button. Use the buttons in the left pane to explore the content of the case study before you answer the questions. Clicking these buttons displays information such as business requirements, existing environment, and problem statements. If the case study has an All Information tab, note that the information displayed is identical to the information displayed on the subsequent tabs. When you are ready to answer a question, click the Question button to return to the question.Overview -Litware, Inc. is a manufacturing company that has offices throughout North America. The analytics team at Litware contains data engineers, analytics engineers, data analysts, and data scientists.Existing Environment -Fabric Environment -Litware has been using a Microsoft Power BI tenant for three years. Litware has NOT enabled any Fabric capacities and features.Available Data -Litware has data that must be analyzed as shown in the following table.The Product data contains a single table and the following columns.The customer satisfaction data contains the following tables:Survey -Question -Response -For each survey submitted, the following occurs:One row is added to the Survey table.One row is added to the Response table for each question in the survey.The Question table contains the text of each survey question. The third question in each survey response is an overall satisfaction score. Customers can submit a survey after each purchase.User Problems -The analytics team has large volumes of data, some of which is semi-structured. The team wants to use Fabric to create a new data store.Product data is often classified into three pricing groups: high, medium, and low. This logic is implemented in several databases and semantic models, but the logic does NOT always match across implementations.Requirements -Planned Changes -Litware plans to enable Fabric features in the existing tenant. The analytics team will create a new data store as a proof of concept (PoC). The remaining Liware users will only get access to the Fabric features once the PoC is complete. The PoC will be completed by using a Fabric trial capacityThe following three workspaces will be created:AnalyticsPOC: Will contain the data store, semantic models, reports pipelines, dataflow, and notebooks used to populate the data storeDataEngPOC: Will contain all the pipelines, dataflows, and notebooks used to populate OneLakeDataSciPOC: Will contain all the notebooks and reports created by the data scientistsThe following will be created in the AnalyticsPOC workspace:A data store (type to be decided)A custom semantic model -A default semantic model -Interactive reports -The data engineers will create data pipelines to load data to OneLake either hourly or daily depending on the data source. The analytics engineers will create processes to ingest, transform, and load the data to the data store in the AnalyticsPOC workspace daily. Whenever possible, the data engineers will use low-code tools for data ingestion. The choice of which data cleansing and transformation tools to use will be at the data engineers’ discretion.All the semantic models and reports in the Analytics POC workspace will use the data store as the sole data source.Technical Requirements -The data store must support the following:Read access by using T-SQL or PythonSemi-structured and unstructured dataRow-level security (RLS) for users executing T-SQL queriesFiles loaded by the data engineers to OneLake will be stored in the Parquet format and will meet Delta Lake specifications.Data will be loaded without transformation in one area of the AnalyticsPOC data store. The data will then be cleansed, merged, and transformed into a dimensional modelThe data load process must ensure that the raw and cleansed data is updated completely before populating the dimensional modelThe dimensional model must contain a date dimension. There is no existing data source for the date dimension. The Litware fiscal year matches the calendar year. The date dimension must always contain dates from 2010 through the end of the current year.The product pricing group logic must be maintained by the analytics engineers in a single location. The pricing group data must be made available in the data store for T-SOL. queries and in the default semantic model. The following logic must be used:List prices that are less than or equal to 50 are in the low pricing group.List prices that are greater than 50 and less than or equal to 1,000 are in the medium pricing group.List prices that are greater than 1,000 are in the high pricing group.Security Requirements -Only Fabric administrators and the analytics team must be able to see the Fabric items created as part of the PoC.Litware identifies the following security requirements for the Fabric items in the AnalyticsPOC workspace:Fabric administrators will be the workspace administrators.The data engineers must be able to read from and write to the data store. No access must be granted to datasets or reports.The analytics engineers must be able to read from, write to, and create schemas in the data store. They also must be able to create and share semantic models with the data analysts and view and modify all reports in the workspace.The data scientists must be able to read from the data store, but not write to it. They will access the data by using a Spark notebookThe data analysts must have read access to only the dimensional model objects in the data store. They also must have access to create Power BI reports by using the semantic models created by the analytics engineers.The date dimension must be available to all users of the data store.The principle of least privilege must be followed.Both the default and custom semantic models must include only tables or views from the dimensional model in the data store. Litware already has the following Microsoft Entra security groups:FabricAdmins: Fabric administratorsAnalyticsTeam: All the members of the analytics teamDataAnalysts: The data analysts on the analytics teamDataScientists: The data scientists on the analytics teamDataEngineers: The data engineers on the analytics teamAnalyticsEngineers: The analytics engineers on the analytics teamReport Requirements -The data analysts must create a customer satisfaction report that meets the following requirements:Enables a user to select a product to filter customer survey responses to only those who have purchased that product.Displays the average overall satisfaction score of all the surveys submitted during the last 12 months up to a selected dat.Shows data as soon as the data is updated in the data store.Ensures that the report and the semantic model only contain data from the current and previous year.Ensures that the report respects any table-level security specified in the source data store.Minimizes the execution time of report queries.You need to create a DAX measure to calculate the average overall satisfaction score.How should you complete the DAX code? To answer, select the appropriate options in the answer area.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: Feb. 9, 2024, 1:56 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/133445-exam-dp-600-topic-1-question-6-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 7 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 7
Topic #: 1

[All DP-600 Questions]

HOTSPOT -Case study -This is a case study. Case studies are not timed separately. You can use as much exam time as you would like to complete each case. However, there may be additional case studies and sections on this exam. You must manage your time to ensure that you are able to complete all questions included on this exam in the time provided.To answer the questions included in a case study, you will need to reference information that is provided in the case study. Case studies might contain exhibits and other resources that provide more information about the scenario that is described in the case study. Each question is independent of the other questions in this case study.At the end of this case study, a review screen will appear. This screen allows you to review your answers and to make changes before you move to the next section of the exam. After you begin a new section, you cannot return to this section.To start the case study -To display the first question in this case study, click the Next button. Use the buttons in the left pane to explore the content of the case study before you answer the questions. Clicking these buttons displays information such as business requirements, existing environment, and problem statements. If the case study has an All Information tab, note that the information displayed is identical to the information displayed on the subsequent tabs. When you are ready to answer a question, click the Question button to return to the question.Overview -Litware, Inc. is a manufacturing company that has offices throughout North America. The analytics team at Litware contains data engineers, analytics engineers, data analysts, and data scientists.Existing Environment -Fabric Environment -Litware has been using a Microsoft Power BI tenant for three years. Litware has NOT enabled any Fabric capacities and features.Available Data -Litware has data that must be analyzed as shown in the following table.The Product data contains a single table and the following columns.The customer satisfaction data contains the following tables:Survey -Question -Response -For each survey submitted, the following occurs:One row is added to the Survey table.One row is added to the Response table for each question in the survey.The Question table contains the text of each survey question. The third question in each survey response is an overall satisfaction score. Customers can submit a survey after each purchase.User Problems -The analytics team has large volumes of data, some of which is semi-structured. The team wants to use Fabric to create a new data store.Product data is often classified into three pricing groups: high, medium, and low. This logic is implemented in several databases and semantic models, but the logic does NOT always match across implementations.Requirements -Planned Changes -Litware plans to enable Fabric features in the existing tenant. The analytics team will create a new data store as a proof of concept (PoC). The remaining Liware users will only get access to the Fabric features once the PoC is complete. The PoC will be completed by using a Fabric trial capacityThe following three workspaces will be created:AnalyticsPOC: Will contain the data store, semantic models, reports pipelines, dataflow, and notebooks used to populate the data storeDataEngPOC: Will contain all the pipelines, dataflows, and notebooks used to populate OneLakeDataSciPOC: Will contain all the notebooks and reports created by the data scientistsThe following will be created in the AnalyticsPOC workspace:A data store (type to be decided)A custom semantic model -A default semantic model -Interactive reports -The data engineers will create data pipelines to load data to OneLake either hourly or daily depending on the data source. The analytics engineers will create processes to ingest, transform, and load the data to the data store in the AnalyticsPOC workspace daily. Whenever possible, the data engineers will use low-code tools for data ingestion. The choice of which data cleansing and transformation tools to use will be at the data engineers’ discretion.All the semantic models and reports in the Analytics POC workspace will use the data store as the sole data source.Technical Requirements -The data store must support the following:Read access by using T-SQL or PythonSemi-structured and unstructured dataRow-level security (RLS) for users executing T-SQL queriesFiles loaded by the data engineers to OneLake will be stored in the Parquet format and will meet Delta Lake specifications.Data will be loaded without transformation in one area of the AnalyticsPOC data store. The data will then be cleansed, merged, and transformed into a dimensional modelThe data load process must ensure that the raw and cleansed data is updated completely before populating the dimensional modelThe dimensional model must contain a date dimension. There is no existing data source for the date dimension. The Litware fiscal year matches the calendar year. The date dimension must always contain dates from 2010 through the end of the current year.The product pricing group logic must be maintained by the analytics engineers in a single location. The pricing group data must be made available in the data store for T-SOL. queries and in the default semantic model. The following logic must be used:List prices that are less than or equal to 50 are in the low pricing group.List prices that are greater than 50 and less than or equal to 1,000 are in the medium pricing group.List prices that are greater than 1,000 are in the high pricing group.Security Requirements -Only Fabric administrators and the analytics team must be able to see the Fabric items created as part of the PoC.Litware identifies the following security requirements for the Fabric items in the AnalyticsPOC workspace:Fabric administrators will be the workspace administrators.The data engineers must be able to read from and write to the data store. No access must be granted to datasets or reports.The analytics engineers must be able to read from, write to, and create schemas in the data store. They also must be able to create and share semantic models with the data analysts and view and modify all reports in the workspace.The data scientists must be able to read from the data store, but not write to it. They will access the data by using a Spark notebookThe data analysts must have read access to only the dimensional model objects in the data store. They also must have access to create Power BI reports by using the semantic models created by the analytics engineers.The date dimension must be available to all users of the data store.The principle of least privilege must be followed.Both the default and custom semantic models must include only tables or views from the dimensional model in the data store. Litware already has the following Microsoft Entra security groups:FabricAdmins: Fabric administratorsAnalyticsTeam: All the members of the analytics teamDataAnalysts: The data analysts on the analytics teamDataScientists: The data scientists on the analytics teamDataEngineers: The data engineers on the analytics teamAnalyticsEngineers: The analytics engineers on the analytics teamReport Requirements -The data analysts must create a customer satisfaction report that meets the following requirements:Enables a user to select a product to filter customer survey responses to only those who have purchased that product.Displays the average overall satisfaction score of all the surveys submitted during the last 12 months up to a selected dat.Shows data as soon as the data is updated in the data store.Ensures that the report and the semantic model only contain data from the current and previous year.Ensures that the report respects any table-level security specified in the source data store.Minimizes the execution time of report queries.You need to resolve the issue with the pricing group classification.How should you complete the T-SQL statement? To answer, select the appropriate options in the answer area.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: Feb. 9, 2024, 2:03 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/133446-exam-dp-600-topic-1-question-7-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 8 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 8
Topic #: 1

[All DP-600 Questions]

Case study -This is a case study. Case studies are not timed separately. You can use as much exam time as you would like to complete each case. However, there may be additional case studies and sections on this exam. You must manage your time to ensure that you are able to complete all questions included on this exam in the time provided.To answer the questions included in a case study, you will need to reference information that is provided in the case study. Case studies might contain exhibits and other resources that provide more information about the scenario that is described in the case study. Each question is independent of the other questions in this case study.At the end of this case study, a review screen will appear. This screen allows you to review your answers and to make changes before you move to the next section of the exam. After you begin a new section, you cannot return to this section.To start the case study -To display the first question in this case study, click the Next button. Use the buttons in the left pane to explore the content of the case study before you answer the questions. Clicking these buttons displays information such as business requirements, existing environment, and problem statements. If the case study has an All Information tab, note that the information displayed is identical to the information displayed on the subsequent tabs. When you are ready to answer a question, click the Question button to return to the question.Overview -Litware, Inc. is a manufacturing company that has offices throughout North America. The analytics team at Litware contains data engineers, analytics engineers, data analysts, and data scientists.Existing Environment -Fabric Environment -Litware has been using a Microsoft Power BI tenant for three years. Litware has NOT enabled any Fabric capacities and features.Available Data -Litware has data that must be analyzed as shown in the following table.The Product data contains a single table and the following columns.The customer satisfaction data contains the following tables:Survey -Question -Response -For each survey submitted, the following occurs:One row is added to the Survey table.One row is added to the Response table for each question in the survey.The Question table contains the text of each survey question. The third question in each survey response is an overall satisfaction score. Customers can submit a survey after each purchase.User Problems -The analytics team has large volumes of data, some of which is semi-structured. The team wants to use Fabric to create a new data store.Product data is often classified into three pricing groups: high, medium, and low. This logic is implemented in several databases and semantic models, but the logic does NOT always match across implementations.Requirements -Planned Changes -Litware plans to enable Fabric features in the existing tenant. The analytics team will create a new data store as a proof of concept (PoC). The remaining Liware users will only get access to the Fabric features once the PoC is complete. The PoC will be completed by using a Fabric trial capacityThe following three workspaces will be created:AnalyticsPOC: Will contain the data store, semantic models, reports pipelines, dataflow, and notebooks used to populate the data storeDataEngPOC: Will contain all the pipelines, dataflows, and notebooks used to populate OneLakeDataSciPOC: Will contain all the notebooks and reports created by the data scientistsThe following will be created in the AnalyticsPOC workspace:A data store (type to be decided)A custom semantic model -A default semantic model -Interactive reports -The data engineers will create data pipelines to load data to OneLake either hourly or daily depending on the data source. The analytics engineers will create processes to ingest, transform, and load the data to the data store in the AnalyticsPOC workspace daily. Whenever possible, the data engineers will use low-code tools for data ingestion. The choice of which data cleansing and transformation tools to use will be at the data engineers’ discretion.All the semantic models and reports in the Analytics POC workspace will use the data store as the sole data source.Technical Requirements -The data store must support the following:Read access by using T-SQL or PythonSemi-structured and unstructured dataRow-level security (RLS) for users executing T-SQL queriesFiles loaded by the data engineers to OneLake will be stored in the Parquet format and will meet Delta Lake specifications.Data will be loaded without transformation in one area of the AnalyticsPOC data store. The data will then be cleansed, merged, and transformed into a dimensional modelThe data load process must ensure that the raw and cleansed data is updated completely before populating the dimensional modelThe dimensional model must contain a date dimension. There is no existing data source for the date dimension. The Litware fiscal year matches the calendar year. The date dimension must always contain dates from 2010 through the end of the current year.The product pricing group logic must be maintained by the analytics engineers in a single location. The pricing group data must be made available in the data store for T-SOL. queries and in the default semantic model. The following logic must be used:List prices that are less than or equal to 50 are in the low pricing group.List prices that are greater than 50 and less than or equal to 1,000 are in the medium pricing group.List prices that are greater than 1,000 are in the high pricing group.Security Requirements -Only Fabric administrators and the analytics team must be able to see the Fabric items created as part of the PoC.Litware identifies the following security requirements for the Fabric items in the AnalyticsPOC workspace:Fabric administrators will be the workspace administrators.The data engineers must be able to read from and write to the data store. No access must be granted to datasets or reports.The analytics engineers must be able to read from, write to, and create schemas in the data store. They also must be able to create and share semantic models with the data analysts and view and modify all reports in the workspace.The data scientists must be able to read from the data store, but not write to it. They will access the data by using a Spark notebookThe data analysts must have read access to only the dimensional model objects in the data store. They also must have access to create Power BI reports by using the semantic models created by the analytics engineers.The date dimension must be available to all users of the data store.The principle of least privilege must be followed.Both the default and custom semantic models must include only tables or views from the dimensional model in the data store. Litware already has the following Microsoft Entra security groups:FabricAdmins: Fabric administratorsAnalyticsTeam: All the members of the analytics teamDataAnalysts: The data analysts on the analytics teamDataScientists: The data scientists on the analytics teamDataEngineers: The data engineers on the analytics teamAnalyticsEngineers: The analytics engineers on the analytics teamReport Requirements -The data analysts must create a customer satisfaction report that meets the following requirements:Enables a user to select a product to filter customer survey responses to only those who have purchased that product.Displays the average overall satisfaction score of all the surveys submitted during the last 12 months up to a selected dat.Shows data as soon as the data is updated in the data store.Ensures that the report and the semantic model only contain data from the current and previous year.Ensures that the report respects any table-level security specified in the source data store.Minimizes the execution time of report queries.What should you recommend using to ingest the customer data into the data store in the AnalyticsPOC workspace? 
Suggested Answer: D 🗳️ 

A. a stored procedure

B. a pipeline that contains a KQL activity

C. a Spark notebook

D. a dataflow

**Answer: D**

**Timestamp: Feb. 9, 2024, 2:08 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/133447-exam-dp-600-topic-1-question-8-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 9 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 9
Topic #: 1

[All DP-600 Questions]

Case study -This is a case study. Case studies are not timed separately. You can use as much exam time as you would like to complete each case. However, there may be additional case studies and sections on this exam. You must manage your time to ensure that you are able to complete all questions included on this exam in the time provided.To answer the questions included in a case study, you will need to reference information that is provided in the case study. Case studies might contain exhibits and other resources that provide more information about the scenario that is described in the case study. Each question is independent of the other questions in this case study.At the end of this case study, a review screen will appear. This screen allows you to review your answers and to make changes before you move to the next section of the exam. After you begin a new section, you cannot return to this section.To start the case study -To display the first question in this case study, click the Next button. Use the buttons in the left pane to explore the content of the case study before you answer the questions. Clicking these buttons displays information such as business requirements, existing environment, and problem statements. If the case study has an All Information tab, note that the information displayed is identical to the information displayed on the subsequent tabs. When you are ready to answer a question, click the Question button to return to the question.Overview -Litware, Inc. is a manufacturing company that has offices throughout North America. The analytics team at Litware contains data engineers, analytics engineers, data analysts, and data scientists.Existing Environment -Fabric Environment -Litware has been using a Microsoft Power BI tenant for three years. Litware has NOT enabled any Fabric capacities and features.Available Data -Litware has data that must be analyzed as shown in the following table.The Product data contains a single table and the following columns.The customer satisfaction data contains the following tables:Survey -Question -Response -For each survey submitted, the following occurs:One row is added to the Survey table.One row is added to the Response table for each question in the survey.The Question table contains the text of each survey question. The third question in each survey response is an overall satisfaction score. Customers can submit a survey after each purchase.User Problems -The analytics team has large volumes of data, some of which is semi-structured. The team wants to use Fabric to create a new data store.Product data is often classified into three pricing groups: high, medium, and low. This logic is implemented in several databases and semantic models, but the logic does NOT always match across implementations.Requirements -Planned Changes -Litware plans to enable Fabric features in the existing tenant. The analytics team will create a new data store as a proof of concept (PoC). The remaining Liware users will only get access to the Fabric features once the PoC is complete. The PoC will be completed by using a Fabric trial capacityThe following three workspaces will be created:AnalyticsPOC: Will contain the data store, semantic models, reports pipelines, dataflow, and notebooks used to populate the data storeDataEngPOC: Will contain all the pipelines, dataflows, and notebooks used to populate OneLakeDataSciPOC: Will contain all the notebooks and reports created by the data scientistsThe following will be created in the AnalyticsPOC workspace:A data store (type to be decided)A custom semantic model -A default semantic model -Interactive reports -The data engineers will create data pipelines to load data to OneLake either hourly or daily depending on the data source. The analytics engineers will create processes to ingest, transform, and load the data to the data store in the AnalyticsPOC workspace daily. Whenever possible, the data engineers will use low-code tools for data ingestion. The choice of which data cleansing and transformation tools to use will be at the data engineers’ discretion.All the semantic models and reports in the Analytics POC workspace will use the data store as the sole data source.Technical Requirements -The data store must support the following:Read access by using T-SQL or PythonSemi-structured and unstructured dataRow-level security (RLS) for users executing T-SQL queriesFiles loaded by the data engineers to OneLake will be stored in the Parquet format and will meet Delta Lake specifications.Data will be loaded without transformation in one area of the AnalyticsPOC data store. The data will then be cleansed, merged, and transformed into a dimensional modelThe data load process must ensure that the raw and cleansed data is updated completely before populating the dimensional modelThe dimensional model must contain a date dimension. There is no existing data source for the date dimension. The Litware fiscal year matches the calendar year. The date dimension must always contain dates from 2010 through the end of the current year.The product pricing group logic must be maintained by the analytics engineers in a single location. The pricing group data must be made available in the data store for T-SOL. queries and in the default semantic model. The following logic must be used:List prices that are less than or equal to 50 are in the low pricing group.List prices that are greater than 50 and less than or equal to 1,000 are in the medium pricing group.List prices that are greater than 1,000 are in the high pricing group.Security Requirements -Only Fabric administrators and the analytics team must be able to see the Fabric items created as part of the PoC.Litware identifies the following security requirements for the Fabric items in the AnalyticsPOC workspace:Fabric administrators will be the workspace administrators.The data engineers must be able to read from and write to the data store. No access must be granted to datasets or reports.The analytics engineers must be able to read from, write to, and create schemas in the data store. They also must be able to create and share semantic models with the data analysts and view and modify all reports in the workspace.The data scientists must be able to read from the data store, but not write to it. They will access the data by using a Spark notebookThe data analysts must have read access to only the dimensional model objects in the data store. They also must have access to create Power BI reports by using the semantic models created by the analytics engineers.The date dimension must be available to all users of the data store.The principle of least privilege must be followed.Both the default and custom semantic models must include only tables or views from the dimensional model in the data store. Litware already has the following Microsoft Entra security groups:FabricAdmins: Fabric administratorsAnalyticsTeam: All the members of the analytics teamDataAnalysts: The data analysts on the analytics teamDataScientists: The data scientists on the analytics teamDataEngineers: The data engineers on the analytics teamAnalyticsEngineers: The analytics engineers on the analytics teamReport Requirements -The data analysts must create a customer satisfaction report that meets the following requirements:Enables a user to select a product to filter customer survey responses to only those who have purchased that product.Displays the average overall satisfaction score of all the surveys submitted during the last 12 months up to a selected dat.Shows data as soon as the data is updated in the data store.Ensures that the report and the semantic model only contain data from the current and previous year.Ensures that the report respects any table-level security specified in the source data store.Minimizes the execution time of report queries.Which type of data store should you recommend in the AnalyticsPOC workspace? 
Suggested Answer: C 🗳️ 

A. a data lake

B. a warehouse

C. a lakehouse

D. an external Hive metastore

**Answer: C**

**Timestamp: Feb. 9, 2024, 2:09 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/133448-exam-dp-600-topic-1-question-9-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 10 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 10
Topic #: 1

[All DP-600 Questions]

You have a Fabric warehouse that contains a table named Staging.Sales. Staging.Sales contains the following columns.You need to write a T-SQL query that will return data for the year 2023 that displays ProductID and ProductName and has a summarized Amount that is higher than 10,000.Which query should you use? 
Suggested Answer: A 🗳️ 

A.

B.

C.

D.

**Answer: A**

**Timestamp: Feb. 9, 2024, 2:13 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/133449-exam-dp-600-topic-1-question-10-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 11 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 11
Topic #: 1

[All DP-600 Questions]

HOTSPOT -You have a data warehouse that contains a table named Stage.Customers. Stage.Customers contains all the customer record updates from a customer relationship management (CRM) system. There can be multiple updates per customer.You need to write a T-SQL query that will return the customer ID, name. postal code, and the last updated time of the most recent row for each customer ID.How should you complete the code? To answer, select the appropriate options in the answer area.NOTE: Each correct selection is worth one point. 
Suggested Answer: Box 1: ROW_NUMBER()Box 2: WHERE X = 1 

**Answer: B**

**Timestamp: Feb. 12, 2024, 3:04 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/133613-exam-dp-600-topic-1-question-11-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 12 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 12
Topic #: 1

[All DP-600 Questions]

HOTSPOT -You have a Fabric tenant.You plan to create a Fabric notebook that will use Spark DataFrames to generate Microsoft Power BI visuals.You run the following code.For each of the following statements, select Yes if the statement is true. Otherwise, select No.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: Feb. 17, 2024, 3:40 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/134062-exam-dp-600-topic-1-question-12-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 13 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 13
Topic #: 1

[All DP-600 Questions]

You are the administrator of a Fabric workspace that contains a lakehouse named Lakehouse1. Lakehouse1 contains the following tables:Table1: A Delta table created by using a shortcutTable2: An external table created by using SparkTable3: A managed table -You plan to connect to Lakehouse1 by using its SQL endpoint.What will you be able to do after connecting to Lakehouse1? 
Suggested Answer: A 🗳️ 

A. Read Table3.

B. Update the data Table3.

C. Read Table2.

D. Update the data in Table1.

**Answer: A**

**Timestamp: Feb. 9, 2024, 12:09 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/133434-exam-dp-600-topic-1-question-13-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 14 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 14
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant that contains a warehouse.You use a dataflow to load a new dataset from OneLake to the warehouse.You need to add a PowerQuery step to identify the maximum values for the numeric columns.Which function should you include in the step? 
Suggested Answer: D 🗳️ 

A. Table.MaxN

B. Table.Max

C. Table.Range

D. Table.Profile

**Answer: D**

**Timestamp: Feb. 12, 2024, 8:49 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/133594-exam-dp-600-topic-1-question-14-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 15 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 15
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant that contains a machine learning model registered in a Fabric workspace.You need to use the model to generate predictions by using the PREDICT function in a Fabric notebook.Which two languages can you use to perform model scoring? Each correct answer presents a complete solution.NOTE: Each correct answer is worth one point. 
Suggested Answer: CD 🗳️ 

A. T-SQL

B. DAX

C. Spark SQL

D. PySpark

**Answer: C**

**Timestamp: Feb. 13, 2024, 11:46 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/133734-exam-dp-600-topic-1-question-15-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 16 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 16
Topic #: 1

[All DP-600 Questions]

You are analyzing the data in a Fabric notebook.You have a Spark DataFrame assigned to a variable named df.You need to use the Chart view in the notebook to explore the data manually.Which function should you run to make the data available in the Chart view? 
Suggested Answer: D 🗳️ 

A. displayHTML

B. show

C. write

D. display

**Answer: D**

**Timestamp: Feb. 17, 2024, 4:04 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/134063-exam-dp-600-topic-1-question-16-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 17 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 17
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant that contains a Microsoft Power BI report named Report1. Report1 includes a Python visual.Data displayed by the visual is grouped automatically and duplicate rows are NOT displayed.You need all rows to appear in the visual.What should you do? 
Suggested Answer: C 🗳️ 

A. Reference the columns in the Python code by index.

B. Modify the Sort Column By property for all columns.

C. Add a unique field to each row.

D. Modify the Summarize By property for all columns.

**Answer: C**

**Timestamp: Feb. 9, 2024, 1:17 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/133441-exam-dp-600-topic-1-question-17-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 18 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 18
Topic #: 1

[All DP-600 Questions]

DRAG DROP -You have a Fabric tenant that contains a semantic model. The model contains data about retail stores.You need to write a DAX query that will be executed by using the XMLA endpoint. The query must return a table of stores that have opened since December 1, 2023.How should you complete the DAX expression? To answer, drag the appropriate values to the correct targets. Each value may be used once, more than once, or not at all. You may need to drag the split bar between panes or scroll to view content.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: Feb. 17, 2024, 4:17 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/134064-exam-dp-600-topic-1-question-18-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 19 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 19
Topic #: 1

[All DP-600 Questions]

You have a Fabric workspace named Workspace1 that contains a dataflow named Dataflow1. Dataflow1 has a query that returns 2,000 rows.You view the query in Power Query as shown in the following exhibit.What can you identify about the pickupLongitude column? 
Suggested Answer: A 🗳️ 

A. The column has duplicate values.

B. All the table rows are profiled.

C. The column has missing values.

D. There are 935 values that occur only once.

**Answer: A**

**Timestamp: Feb. 11, 2024, 2:15 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/133523-exam-dp-600-topic-1-question-19-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 20 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 20
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant named Tenant1 that contains a workspace named WS1. WS1 uses a capacity named C1 and contains a dataset named DS1.You need to ensure read-write access to DS1 is available by using XMLA endpoint.What should be modified first? 
Suggested Answer: C 🗳️ 

A. the DS1 settings

B. the WS1 settings

C. the C1 settings

D. the Tenant1 settings

**Answer: C**

**Timestamp: Feb. 14, 2024, 7:55 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/133878-exam-dp-600-topic-1-question-20-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 21 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 21
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant that contains a workspace named Workspace1. Workspace1 is assigned to a Fabric capacity.You need to recommend a solution to provide users with the ability to create and publish custom Direct Lake semantic models by using external tools. The solution must follow the principle of least privilege.Which three actions in the Fabric Admin portal should you include in the recommendation? Each correct answer presents part of the solution.NOTE: Each correct answer is worth one point. 
Suggested Answer: ADE 🗳️ 

A. From the Tenant settings, set Allow XMLA Endpoints and Analyze in Excel with on-premises datasets to Enabled.

B. From the Tenant settings, set Allow Azure Active Directory guest users to access Microsoft Fabric to Enabled.

C. From the Tenant settings, select Users can edit data model in the Power BI service.

D. From the Capacity settings, set XMLA Endpoint to Read Write.

E. From the Tenant settings, set Users can create Fabric items to Enabled.

F. From the Tenant settings, enable Publish to Web.

**Answer: A**

**Timestamp: Feb. 17, 2024, 11:31 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/134090-exam-dp-600-topic-1-question-21-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 22 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 22
Topic #: 1

[All DP-600 Questions]

You are creating a semantic model in Microsoft Power BI Desktop.You plan to make bulk changes to the model by using the Tabular Model Definition Language (TMDL) extension for Microsoft Visual Studio Code.You need to save the semantic model to a file.Which file format should you use? 
Suggested Answer: A 🗳️ 

A. PBIP

B. PBIX

C. PBIT

D. PBIDS

**Answer: A**

**Timestamp: Feb. 9, 2024, 7:17 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/133461-exam-dp-600-topic-1-question-22-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 23 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 23
Topic #: 1

[All DP-600 Questions]

HOTSPOT -You have a Fabric tenant that contains a warehouse named Warehouse1. Warehouse1 contains three schemas named schemaA, schemaB, and schemaC.You need to ensure that a user named User1 can truncate tables in schemaA only.How should you complete the T-SQL statement? To answer, select the appropriate options in the answer area.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: Feb. 17, 2024, 11:36 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/134091-exam-dp-600-topic-1-question-23-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 24 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 24
Topic #: 1

[All DP-600 Questions]

You plan to deploy Microsoft Power BI items by using Fabric deployment pipelines. You have a deployment pipeline that contains three stages named Development, Test, and Production. A workspace is assigned to each stage.You need to provide Power BI developers with access to the pipeline. The solution must meet the following requirements:Ensure that the developers can deploy items to the workspaces for Development and Test.Prevent the developers from deploying items to the workspace for Production.Follow the principle of least privilege.Which three levels of access should you assign to the developers? Each correct answer presents part of the solution.NOTE: Each correct answer is worth one point. 
Suggested Answer: BDE 🗳️ 

A. Build permission to the production semantic models

B. Admin access to the deployment pipeline

C. Viewer access to the Development and Test workspaces

D. Viewer access to the Production workspace

E. Contributor access to the Development and Test workspaces

F. Contributor access to the Production workspace

**Answer: B**

**Timestamp: Feb. 17, 2024, 11:49 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/134093-exam-dp-600-topic-1-question-24-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 25 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 25
Topic #: 1

[All DP-600 Questions]

You have a Fabric workspace that contains a DirectQuery semantic model. The model queries a data source that has 500 million rows.You have a Microsoft Power Bi report named Report1 that uses the model. Report1 contains visuals on multiple pages.You need to reduce the query execution time for the visuals on all the pages.What are two features that you can use? Each correct answer presents a complete solution,NOTE: Each correct answer is worth one point. 
Suggested Answer: AB 🗳️ 

A. user-defined aggregations

B. automatic aggregation

C. query caching

D. OneLake integration

**Answer: A**

**Timestamp: Feb. 12, 2024, 6:26 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/133635-exam-dp-600-topic-1-question-25-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 26 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 26
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant that contains 30 CSV files in OneLake. The files are updated daily.You create a Microsoft Power BI semantic model named Model1 that uses the CSV files as a data source. You configure incremental refresh for Model1 and publish the model to a Premium capacity in the Fabric tenant.When you initiate a refresh of Model1, the refresh fails after running out of resources.What is a possible cause of the failure? 
Suggested Answer: D 🗳️ 

A. Query folding is occurring.

B. Only refresh complete days is selected.

C. XMLA Endpoint is set to Read Only.

D. Query folding is NOT occurring.

E. The delta type of the column used to partition the data has changed.

**Answer: D**

**Timestamp: Feb. 13, 2024, 9:23 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/133726-exam-dp-600-topic-1-question-26-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 27 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 27
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant that uses a Microsoft Power BI Premium capacity.You need to enable scale-out for a semantic model.What should you do first? 
Suggested Answer: C 🗳️ 

A. At the semantic model level, set Large dataset storage format to Off.

B. At the tenant level, set Create and use Metrics to Enabled.

C. At the semantic model level, set Large dataset storage format to On.

D. At the tenant level, set Data Activator to Enabled.

**Answer: C**

**Timestamp: Feb. 12, 2024, 7:32 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/133645-exam-dp-600-topic-1-question-27-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 28 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 28
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant that contains a warehouse. The warehouse uses row-level security (RLS).You create a Direct Lake semantic model that uses the Delta tables and RLS of the warehouse.When users interact with a report built from the model, which mode will be used by the DAX queries? 
Suggested Answer: A 🗳️ 

A. DirectQuery

B. Dual

C. Direct Lake

D. Import

**Answer: A**

**Timestamp: Feb. 9, 2024, 8:06 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/133464-exam-dp-600-topic-1-question-28-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 29 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 29
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant that contains a complex semantic model. The model is based on a star schema and contains many tables, including a fact table named Sales.You need to create a diagram of the model. The diagram must contain only the Sales table and related tables.What should you use from Microsoft Power BI Desktop? 
Suggested Answer: C 🗳️ 

A. data categories

B. Data view

C. Model view

D. DAX query view

**Answer: C**

**Timestamp: Feb. 18, 2024, 12:04 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/134094-exam-dp-600-topic-1-question-29-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 30 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 30
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant that contains a semantic model. The model uses Direct Lake mode.You suspect that some DAX queries load unnecessary columns into memory.You need to identify the frequently used columns that are loaded into memory.What are two ways to achieve the goal? Each correct answer presents a complete solution.NOTE: Each correct answer is worth one point. 
Suggested Answer: BC 🗳️ 

A. Use the Analyze in Excel feature.

B. Use the Vertipaq Analyzer tool.

C. Query the $System.DISCOVER_STORAGE_TABLE_COLUMN_SEGMENTS dynamic management view (DMV).

D. Query the DISCOVER_MEMORYGRANT dynamic management view (DMV).

**Answer: B**

**Timestamp: Feb. 17, 2024, 2:26 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/134040-exam-dp-600-topic-1-question-30-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 31 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 31
Topic #: 1

[All DP-600 Questions]

HOTSPOT -You have the source data model shown in the following exhibit.The primary keys of the tables are indicated by a key symbol beside the columns involved in each key.You need to create a dimensional data model that will enable the analysis of order items by date, product, and customer.What should you include in the solution? To answer, select the appropriate options in the answer area.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: Feb. 13, 2024, 9:38 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/133728-exam-dp-600-topic-1-question-31-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 32 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 32
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant that contains a semantic model named Model1. Model1 uses Import mode. Model1 contains a table named Orders. Orders has 100 million rows and the following fields.You need to reduce the memory used by Model1 and the time it takes to refresh the model.Which two actions should you perform? Each correct answer presents part of the solution.NOTE: Each correct answer is worth one point. 
Suggested Answer: AD 🗳️ 

A. Split OrderDateTime into separate date and time columns.

B. Replace TotalQuantity with a calculated column.

C. Convert Quantity into the Text data type.

D. Replace TotalSalesAmount with a measure.

**Answer: A**

**Timestamp: Feb. 13, 2024, 9:48 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/133729-exam-dp-600-topic-1-question-32-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 33 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 33
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant that contains a semantic model.You need to prevent report creators from populating visuals by using implicit measures.What are two tools that you can use to achieve the goal? Each correct answer presents a complete solution.NOTE: Each correct answer is worth one point. 
Suggested Answer: AB 🗳️ 

A. Microsoft Power BI Desktop

B. Tabular Editor

C. Microsoft SQL Server Management Studio (SSMS)

D. DAX Studio

**Answer: A**

**Timestamp: Feb. 9, 2024, 8:29 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/133465-exam-dp-600-topic-1-question-33-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 34 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 34
Topic #: 1

[All DP-600 Questions]

HOTSPOT -You have a Fabric tenant that contains two lakehouses.You are building a dataflow that will combine data from the lakehouses. The applied steps from one of the queries in the dataflow is shown in the following exhibit.Use the drop-down menus to select the answer choice that completes each statement based on the information presented in the graphic.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: Feb. 17, 2024, 3:03 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/134042-exam-dp-600-topic-1-question-34-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 35 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 35
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant that contains a lakehouse named Lakehouse’. Lakehouse1 contains a table named Tablet.You are creating a new data pipeline.You plan to copy external data to Table’. The schema of the external data changes regularly.You need the copy operation to meet the following requirements:Replace Table1 with the schema of the external data.Replace all the data in Table1 with the rows in the external data.You add a Copy data activity to the pipeline.What should you do for the Copy data activity? 
Suggested Answer: B 🗳️ 

A. From the Source tab, add additional columns.

B. From the Destination tab, set Table action to Overwrite.

C. From the Settings tab, select Enable staging.

D. From the Source tab, select Enable partition discovery.

E. From the Source tab, select Recursively.

**Answer: B**

**Timestamp: Feb. 9, 2024, 8:36 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/133466-exam-dp-600-topic-1-question-35-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 36 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 36
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant that contains a lakehouse.You plan to query sales data files by using the SQL endpoint. The files will be in an Amazon Simple Storage Service (Amazon S3) storage bucket.You need to recommend which file format to use and where to create a shortcut.Which two actions should you include in the recommendation? Each correct answer presents part of the solution.NOTE: Each correct answer is worth one point. 
Suggested Answer: DE 🗳️ 

A. Create a shortcut in the Files section.

B. Use the Parquet format

C. Use the CSV format.

D. Create a shortcut in the Tables section.

E. Use the delta format.

**Answer: D**

**Timestamp: Feb. 9, 2024, 8:50 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/133467-exam-dp-600-topic-1-question-36-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 37 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 37
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant that contains a lakehouse named Lakehouse1. Lakehouse1 contains a subfolder named Subfolder1 that contains CSV files.You need to convert the CSV files into the delta format that has V-Order optimization enabled.What should you do from Lakehouse explorer? 
Suggested Answer: A 🗳️ 

A. Use the Load to Tables feature.

B. Create a new shortcut in the Files section.

C. Create a new shortcut in the Tables section.

D. Use the Optimize feature.

**Answer: A**

**Timestamp: Feb. 9, 2024, 9:07 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/133468-exam-dp-600-topic-1-question-37-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 38 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 38
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant that contains a lakehouse named Lakehouse1. Lakehouse1 contains an unpartitioned table named Table1.You plan to copy data to Table1 and partition the table based on a date column in the source data.You create a Copy activity to copy the data to Table1.You need to specify the partition column in the Destination settings of the Copy activity.What should you do first? 
Suggested Answer: D 🗳️ 

A. From the Destination tab, set Mode to Append.

B. From the Destination tab, select the partition column.

C. From the Source tab, select Enable partition discovery.

D. From the Destination tabs, set Mode to Overwrite.

**Answer: D**

**Timestamp: Feb. 17, 2024, 6:19 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/134050-exam-dp-600-topic-1-question-38-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 40 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 40
Topic #: 1

[All DP-600 Questions]

You have source data in a folder on a local computer.You need to create a solution that will use Fabric to populate a data store. The solution must meet the following requirements:Support the use of dataflows to load and append data to the data store.Ensure that Delta tables are V-Order optimized and compacted automatically.Which type of data store should you use? 
Suggested Answer: A 🗳️ 

A. a lakehouse

B. an Azure SQL database

C. a warehouse

D. a KQL database

**Answer: A**

**Timestamp: Feb. 9, 2024, 9:22 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/133469-exam-dp-600-topic-1-question-40-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 41 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 41
Topic #: 1

[All DP-600 Questions]

HOTSPOT -You have a Fabric tenant that contains a lakehouse.You are using a Fabric notebook to save a large DataFrame by using the following code. df.write.partitionBy(“year”, “month”, “day”).mode(“overwrite”).parquet(“Files/SalesOrder”)For each of the following statements, select Yes if the statement is true. Otherwise, select No.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: Feb. 18, 2024, 12:54 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/134096-exam-dp-600-topic-1-question-41-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 42 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 42
Topic #: 1

[All DP-600 Questions]

You have a Fabric workspace named Workspace1 that contains a data flow named Dataflow1 contains a query that returns the data shown in the following exhibit.You need to transform the data columns into attribute-value pairs, where columns become rows.You select the VendorID column.Which transformation should you select from the context menu of the VendorID column? 
Suggested Answer: C 🗳️ 

A. Group by

B. Unpivot columns

C. Unpivot other columns

D. Split column

E. Remove other columns

**Answer: C**

**Timestamp: Feb. 18, 2024, 12:57 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/134097-exam-dp-600-topic-1-question-42-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 43 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 43
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant that contains a data pipeline.You need to ensure that the pipeline runs every four hours on Mondays and Fridays.To what should you set Repeat for the schedule? 
Suggested Answer: C 🗳️ 

A. Daily

B. By the minute

C. Weekly

D. Hourly

**Answer: C**

**Timestamp: Feb. 9, 2024, 9:31 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/133470-exam-dp-600-topic-1-question-43-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 44 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 44
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant that contains a warehouse.Several times a day, the performance of all warehouse queries degrades. You suspect that Fabric is throttling the compute used by the warehouse.What should you use to identify whether throttling is occurring? 
Suggested Answer: D 🗳️ 

A. the Capacity settings

B. the Monitoring hub

C. dynamic management views (DMVs)

D. the Microsoft Fabric Capacity Metrics app

**Answer: D**

**Timestamp: Feb. 18, 2024, 12:59 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/134098-exam-dp-600-topic-1-question-44-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 45 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 45
Topic #: 1

[All DP-600 Questions]

HOTSPOT -You have a Fabric workspace that uses the default Spark starter pool and runtime version 1.2.You plan to read a CSV file named Sales_raw.csv in a lakehouse, select columns, and save the data as a Delta table to the managed area of the lakehouse. Sales_raw.csv contains 12 columns.You have the following code.For each of the following statements, select Yes if the statement is true. Otherwise, select No.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: Feb. 18, 2024, 1:30 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/134102-exam-dp-600-topic-1-question-45-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 46 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 46
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant that contains a warehouse.A user discovers that a report that usually takes two minutes to render has been running for 45 minutes and has still not rendered.You need to identify what is preventing the report query from completing.Which dynamic management view (DMV) should you use? 
Suggested Answer: A 🗳️ 

A. sys.dm_exec_requests

B. sys.dm_exec_sessions

C. sys.dm_exec_connections

D. sys.dm_pdw_exec_requests

**Answer: A**

**Timestamp: Feb. 18, 2024, 1:32 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/134103-exam-dp-600-topic-1-question-46-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 47 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 47
Topic #: 1

[All DP-600 Questions]

DRAG DROP -You are creating a data flow in Fabric to ingest data from an Azure SQL database by using a T-SQL statement.You need to ensure that any foldable Power Query transformation steps are processed by the Microsoft SQL Server engine.How should you complete the code? To answer, drag the appropriate values to the correct targets. Each value may be used once, more than once, or not at all. You may need to drag the split bar between panes or scroll to view content.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: Feb. 17, 2024, 7:27 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/134070-exam-dp-600-topic-1-question-47-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 48 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 48
Topic #: 1

[All DP-600 Questions]

DRAG DROP -You have a Fabric tenant that contains a lakehouse named Lakehouse1.Readings from 100 IoT devices are appended to a Delta table in Lakehouse1. Each set of readings is approximately 25 KB. Approximately 10 GB of data is received daily.All the table and SparkSession settings are set to the default.You discover that queries are slow to execute. In addition, the lakehouse storage contains data and log files that are no longer used.You need to remove the files that are no longer used and combine small files into larger files with a target size of 1 GB per file.What should you do? To answer, drag the appropriate actions to the correct requirements. Each action may be used once, more than once, or not at all. You may need to drag the split bar between panes or scroll to view content.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: Feb. 17, 2024, 7:41 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/134071-exam-dp-600-topic-1-question-48-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 49 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 49
Topic #: 1

[All DP-600 Questions]

You need to create a data loading pattern for a Type 1 slowly changing dimension (SCD).Which two actions should you include in the process? Each correct answer presents part of the solution.NOTE: Each correct answer is worth one point. 
Suggested Answer: AD 🗳️ 

A. Update rows when the non-key attributes have changed.

B. Insert new rows when the natural key exists in the dimension table, and the non-key attribute values have changed.

C. Update the effective end date of rows when the non-key attribute values have changed.

D. Insert new records when the natural key is a new value in the table.

**Answer: A**

**Timestamp: Feb. 13, 2024, 12:28 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/133737-exam-dp-600-topic-1-question-49-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 50 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 50
Topic #: 1

[All DP-600 Questions]

HOTSPOT -You have a Fabric workspace named Workspace1 and an Azure Data Lake Storage Gen2 account named storage1. Workspace1 contains a lakehouse named Lakehouse1.You need to create a shortcut to storage1 in Lakehouse1.Which connection and endpoint should you specify? To answer, select the appropriate options in the answer area.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: Feb. 9, 2024, 11:04 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/133471-exam-dp-600-topic-1-question-50-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 51 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 51
Topic #: 1

[All DP-600 Questions]

You are analyzing customer purchases in a Fabric notebook by using PySpark.You have the following DataFrames:transactions: Contains five columns named transaction_id, customer_id, product_id, amount, and date and has 10 million rows, with each row representing a transaction. customers: Contains customer details in 1,000 rows and three columns named customer_id, name, and country.You need to join the DataFrames on the customer_id column. The solution must minimize data shuffling.You write the following code.from pyspark.sql import functions as Fresults =Which code should you run to populate the results DataFrame? 
Suggested Answer: A 🗳️ 

A. transactions.join(F.broadcast(customers), transactions.customer_id == customers.customer_id)

B. transactions.join(customers, transactions.customer_id == customers.customer_id).distinct()

C. transactions.join(customers, transactions.customer_id == customers.customer_id)

D. transactions.crossJoin(customers).where(transactions.customer_id == customers.customer_id)

**Answer: A**

**Timestamp: Feb. 17, 2024, 8:25 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/134072-exam-dp-600-topic-1-question-51-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 52 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 52
Topic #: 1

[All DP-600 Questions]

HOTSPOT -You have a Microsoft Power BI report and a semantic model that uses Direct Lake mode.From Power BI Desktop, you open Performance analyzer as shown in the following exhibit.Use the drop-down menus to select the answer choice that completes each statement based on the information presented in the graphic.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: Feb. 17, 2024, 8:40 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/134073-exam-dp-600-topic-1-question-52-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 53 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 53
Topic #: 1

[All DP-600 Questions]

HOTSPOT -You have a Fabric tenant that contains a lakehouse named Lakehouse1. Lakehouse1 contains a table named Nyctaxi_raw. Nyctaxi_row contains the following table:You create a Fabric notebook and attach it to Lakehouse1.You need to use PySpark code to transform the data. The solution must meet the following requirements:Add a column named pickupDate that will contain only the date portion of pickupDateTime.Filter the DataFrame to include only rows where fareAmount is a positive number that is less than 100.How should you complete the code? To answer, select the appropriate options in the answer area.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: Feb. 13, 2024, 12:52 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/133739-exam-dp-600-topic-1-question-53-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 54 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 54
Topic #: 1

[All DP-600 Questions]

Note: This question is part of a series of questions that present the same scenario. Each question in the series contains a unique solution that might meet the stated goals. Some question sets might have more than one correct solution, while others might not have a correct solution.After you answer a question in this section, you will NOT be able to return to it. As a result, these questions will not appear in the review screen.You have a Fabric tenant that contains a new semantic model in OneLake.You use a Fabric notebook to read the data into a Spark DataFrame.You need to evaluate the data to calculate the min, max, mean, and standard deviation values for all the string and numeric columns.Solution: You use the following PySpark expression:df.explain()Does this meet the goal? 
Suggested Answer: B 🗳️ 

A. Yes

B. No

**Answer: B**

**Timestamp: Feb. 17, 2024, 9:43 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/134075-exam-dp-600-topic-1-question-54-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 55 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 55
Topic #: 1

[All DP-600 Questions]

Note: This question is part of a series of questions that present the same scenario. Each question in the series contains a unique solution that might meet the stated goals. Some question sets might have more than one correct solution, while others might not have a correct solution.After you answer a question in this section, you will NOT be able to return to it. As a result, these questions will not appear in the review screen.You have a Fabric tenant that contains a new semantic model in OneLake.You use a Fabric notebook to read the data into a Spark DataFrame.You need to evaluate the data to calculate the min, max, mean, and standard deviation values for all the string and numeric columns.Solution: You use the following PySpark expression:df.show()Does this meet the goal? 
Suggested Answer: B 🗳️ 

A. Yes

B. No

**Answer: B**

**Timestamp: Feb. 17, 2024, 9:44 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/134076-exam-dp-600-topic-1-question-55-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 56 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 56
Topic #: 1

[All DP-600 Questions]

Note: This question is part of a series of questions that present the same scenario. Each question in the series contains a unique solution that might meet the stated goals. Some question sets might have more than one correct solution, while others might not have a correct solution.After you answer a question in this section, you will NOT be able to return to it. As a result, these questions will not appear in the review screen.You have a Fabric tenant that contains a new semantic model in OneLake.You use a Fabric notebook to read the data into a Spark DataFrame.You need to evaluate the data to calculate the min, max, mean, and standard deviation values for all the string and numeric columns.Solution: You use the following PySpark expression:df.summary()Does this meet the goal? 
Suggested Answer: A 🗳️ 

A. Yes

B. No

**Answer: A**

**Timestamp: Feb. 17, 2024, 9:44 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/134077-exam-dp-600-topic-1-question-56-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 57 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 57
Topic #: 1

[All DP-600 Questions]

Note: This question is part of a series of questions that present the same scenario. Each question in the series contains a unique solution that might meet the stated goals. Some question sets might have more than one correct solution, while others might not have a correct solution.After you answer a question in this section, you will NOT be able to return to it. As a result, these questions will not appear in the review screen.You have a Fabric tenant that contains a lakehouse named Lakehouse1. Lakehouse1 contains a Delta table named Customer.When you query Customer, you discover that the query is slow to execute. You suspect that maintenance was NOT performed on the table.You need to identify whether maintenance tasks were performed on Customer.Solution: You run the following Spark SQL statement:DESCRIBE HISTORY customer -Does this meet the goal? 
Suggested Answer: A 🗳️ 

A. Yes

B. No

**Answer: A**

**Timestamp: Feb. 17, 2024, 10:07 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/134079-exam-dp-600-topic-1-question-57-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 58 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 58
Topic #: 1

[All DP-600 Questions]

Note: This question is part of a series of questions that present the same scenario. Each question in the series contains a unique solution that might meet the stated goals. Some question sets might have more than one correct solution, while others might not have a correct solution.After you answer a question in this section, you will NOT be able to return to it. As a result, these questions will not appear in the review screen.You have a Fabric tenant that contains a lakehouse named Lakehouse1. Lakehouse1 contains a Delta table named Customer.When you query Customer, you discover that the query is slow to execute. You suspect that maintenance was NOT performed on the table.You need to identify whether maintenance tasks were performed on Customer.Solution: You run the following Spark SQL statement:REFRESH TABLE customer -Does this meet the goal? 
Suggested Answer: B 🗳️ 

A. Yes

B. No

**Answer: B**

**Timestamp: Feb. 17, 2024, 10:10 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/134080-exam-dp-600-topic-1-question-58-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 59 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 59
Topic #: 1

[All DP-600 Questions]

Note: This question is part of a series of questions that present the same scenario. Each question in the series contains a unique solution that might meet the stated goals. Some question sets might have more than one correct solution, while others might not have a correct solution.After you answer a question in this section, you will NOT be able to return to it. As a result, these questions will not appear in the review screen.You have a Fabric tenant that contains a lakehouse named Lakehouse1. Lakehouse1 contains a Delta table named Customer.When you query Customer, you discover that the query is slow to execute. You suspect that maintenance was NOT performed on the table.You need to identify whether maintenance tasks were performed on Customer.Solution: You run the following Spark SQL statement:EXPLAIN TABLE customer -Does this meet the goal? 
Suggested Answer: B 🗳️ 

A. Yes

B. No

**Answer: B**

**Timestamp: Feb. 17, 2024, 10:16 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/134083-exam-dp-600-topic-1-question-59-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 60 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 60
Topic #: 1

[All DP-600 Questions]

Case study -This is a case study. Case studies are not timed separately. You can use as much exam time as you would like to complete each case. However, there may be additional case studies and sections on this exam. You must manage your time to ensure that you are able to complete all questions included on this exam in the time provided.To answer the questions included in a case study, you will need to reference information that is provided in the case study. Case studies might contain exhibits and other resources that provide more information about the scenario that is described in the case study. Each question is independent of the other questions in this case study.At the end of this case study, a review screen will appear. This screen allows you to review your answers and to make changes before you move to the next section of the exam. After you begin a new section, you cannot return to this section.To start the case study -To display the first question in this case study, click the Next button. Use the buttons in the left pane to explore the content of the case study before you answer the questions. Clicking these buttons displays information such as business requirements, existing environment, and problem statements. If the case study has an All Information tab, note that the information displayed is identical to the information displayed on the subsequent tabs. When you are ready to answer a question, click the Question button to return to the question.Overview -Litware, Inc. is a manufacturing company that has offices throughout North America. The analytics team at Litware contains data engineers, analytics engineers, data analysts, and data scientists.Existing Environment -Fabric Environment -Litware has been using a Microsoft Power BI tenant for three years. Litware has NOT enabled any Fabric capacities and features.Available Data -Litware has data that must be analyzed as shown in the following table.The Product data contains a single table and the following columns.The customer satisfaction data contains the following tables:• Survey• Question• ResponseFor each survey submitted, the following occurs:• One row is added to the Survey table.• One row is added to the Response table for each question in the survey.The Question table contains the text of each survey question. The third question in each survey response is an overall satisfaction score. Customers can submit a survey after each purchase.User Problems -The analytics team has large volumes of data, some of which is semi-structured. The team wants to use Fabric to create a new data store.Product data is often classified into three pricing groups: high, medium, and low. This logic is implemented in several databases and semantic models, but the logic does NOT always match across implementations.Requirements -Planned Changes -Litware plans to enable Fabric features in the existing tenant. The analytics team will create a new data store as a proof of concept (PoC). The remaining Liware users will only get access to the Fabric features once the PoC is complete. The PoC will be completed by using a Fabric trial capacityThe following three workspaces will be created:• AnalyticsPOC: Will contain the data store, semantic models, reports pipelines, dataflow, and notebooks used to populate the data store• DataEngPOC: Will contain all the pipelines, dataflows, and notebooks used to populate OneLake• DataSciPOC: Will contain all the notebooks and reports created by the data scientistsThe following will be created in the AnalyticsPOC workspace:• A data store (type to be decided)• A custom semantic model• A default semantic model• Interactive reportsThe data engineers will create data pipelines to load data to OneLake either hourly or daily depending on the data source. The analytics engineers will create processes to ingest, transform, and load the data to the data store in the AnalyticsPOC workspace daily. Whenever possible, the data engineers will use low-code tools for data ingestion. The choice of which data cleansing and transformation tools to use will be at the data engineers’ discretion.All the semantic models and reports in the Analytics POC workspace will use the data store as the sole data source.Technical Requirements -The data store must support the following:• Read access by using T-SQL or Python• Semi-structured and unstructured data• Row-level security (RLS) for users executing T-SQL queriesFiles loaded by the data engineers to OneLake will be stored in the Parquet format and will meet Delta Lake specifications.Data will be loaded without transformation in one area of the AnalyticsPOC data store. The data will then be cleansed, merged, and transformed into a dimensional modelThe data load process must ensure that the raw and cleansed data is updated completely before populating the dimensional modelThe dimensional model must contain a date dimension. There is no existing data source for the date dimension. The Litware fiscal year matches the calendar year. The date dimension must always contain dates from 2010 through the end of the current year.The product pricing group logic must be maintained by the analytics engineers in a single location. The pricing group data must be made available in the data store for T-SOL. queries and in the default semantic model. The following logic must be used:• List prices that are less than or equal to 50 are in the low pricing group.• List prices that are greater than 50 and less than or equal to 1,000 are in the medium pricing group.• List prices that are greater than 1,000 are in the high pricing group.Security Requirements -Only Fabric administrators and the analytics team must be able to see the Fabric items created as part of the PoC.Litware identifies the following security requirements for the Fabric items in the AnalyticsPOC workspace:• Fabric administrators will be the workspace administrators.• The data engineers must be able to read from and write to the data store. No access must be granted to datasets or reports.• The analytics engineers must be able to read from, write to, and create schemas in the data store. They also must be able to create and share semantic models with the data analysts and view and modify all reports in the workspace.• The data scientists must be able to read from the data store, but not write to it. They will access the data by using a Spark notebook• The data analysts must have read access to only the dimensional model objects in the data store. They also must have access to create Power BI reports by using the semantic models created by the analytics engineers.• The date dimension must be available to all users of the data store.• The principle of least privilege must be followed.Both the default and custom semantic models must include only tables or views from the dimensional model in the data store. Litware already has the following Microsoft Entra security groups:• FabricAdmins: Fabric administrators• AnalyticsTeam: All the members of the analytics team• DataAnalysts: The data analysts on the analytics team• DataScientists: The data scientists on the analytics team• DataEngineers: The data engineers on the analytics team• AnalyticsEngineers: The analytics engineers on the analytics teamReport Requirements -The data analysts must create a customer satisfaction report that meets the following requirements:• Enables a user to select a product to filter customer survey responses to only those who have purchased that product.• Displays the average overall satisfaction score of all the surveys submitted during the last 12 months up to a selected dat.• Shows data as soon as the data is updated in the data store.• Ensures that the report and the semantic model only contain data from the current and previous year.• Ensures that the report respects any table-level security specified in the source data store.• Minimizes the execution time of report queries.You need to recommend a solution to prepare the tenant for the PoC.Which two actions should you recommend performing from the Fabric Admin portal? Each correct answer presents part of the solution.NOTE: Each correct answer is worth one point. 
Suggested Answer: BE 🗳️ 

A. Enable the Users can try Microsoft Fabric paid features option for the entire organization.

B. Enable the Users can try Microsoft Fabric paid features option for specific security groups.

C. Enable the Allow Azure Active Directory guest users to access Microsoft Fabric option for specific security groups.

D. Enable the Users can create Fabric items option and exclude specific security groups.

E. Enable the Users can create Fabric items option for specific security groups.

**Answer: B**

**Timestamp: April 21, 2024, 10:07 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/139283-exam-dp-600-topic-1-question-60-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 61 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 61
Topic #: 1

[All DP-600 Questions]

HOTSPOT -Case study -This is a case study. Case studies are not timed separately. You can use as much exam time as you would like to complete each case. However, there may be additional case studies and sections on this exam. You must manage your time to ensure that you are able to complete all questions included on this exam in the time provided.To answer the questions included in a case study, you will need to reference information that is provided in the case study. Case studies might contain exhibits and other resources that provide more information about the scenario that is described in the case study. Each question is independent of the other questions in this case study.At the end of this case study, a review screen will appear. This screen allows you to review your answers and to make changes before you move to the next section of the exam. After you begin a new section, you cannot return to this section.To start the case study -To display the first question in this case study, click the Next button. Use the buttons in the left pane to explore the content of the case study before you answer the questions. Clicking these buttons displays information such as business requirements, existing environment, and problem statements. If the case study has an All Information tab, note that the information displayed is identical to the information displayed on the subsequent tabs. When you are ready to answer a question, click the Question button to return to the question.Overview -Litware, Inc. is a manufacturing company that has offices throughout North America. The analytics team at Litware contains data engineers, analytics engineers, data analysts, and data scientists.Existing Environment -Fabric Environment -Litware has been using a Microsoft Power BI tenant for three years. Litware has NOT enabled any Fabric capacities and features.Available Data -Litware has data that must be analyzed as shown in the following table.The Product data contains a single table and the following columns.The customer satisfaction data contains the following tables:• Survey• Question• ResponseFor each survey submitted, the following occurs:• One row is added to the Survey table.• One row is added to the Response table for each question in the survey.The Question table contains the text of each survey question. The third question in each survey response is an overall satisfaction score. Customers can submit a survey after each purchase.User Problems -The analytics team has large volumes of data, some of which is semi-structured. The team wants to use Fabric to create a new data store.Product data is often classified into three pricing groups: high, medium, and low. This logic is implemented in several databases and semantic models, but the logic does NOT always match across implementations.Requirements -Planned Changes -Litware plans to enable Fabric features in the existing tenant. The analytics team will create a new data store as a proof of concept (PoC). The remaining Liware users will only get access to the Fabric features once the PoC is complete. The PoC will be completed by using a Fabric trial capacityThe following three workspaces will be created:• AnalyticsPOC: Will contain the data store, semantic models, reports pipelines, dataflow, and notebooks used to populate the data store• DataEngPOC: Will contain all the pipelines, dataflows, and notebooks used to populate OneLake• DataSciPOC: Will contain all the notebooks and reports created by the data scientistsThe following will be created in the AnalyticsPOC workspace:• A data store (type to be decided)• A custom semantic model• A default semantic model• Interactive reportsThe data engineers will create data pipelines to load data to OneLake either hourly or daily depending on the data source. The analytics engineers will create processes to ingest, transform, and load the data to the data store in the AnalyticsPOC workspace daily. Whenever possible, the data engineers will use low-code tools for data ingestion. The choice of which data cleansing and transformation tools to use will be at the data engineers’ discretion.All the semantic models and reports in the Analytics POC workspace will use the data store as the sole data source.Technical Requirements -The data store must support the following:• Read access by using T-SQL or Python• Semi-structured and unstructured data• Row-level security (RLS) for users executing T-SQL queriesFiles loaded by the data engineers to OneLake will be stored in the Parquet format and will meet Delta Lake specifications.Data will be loaded without transformation in one area of the AnalyticsPOC data store. The data will then be cleansed, merged, and transformed into a dimensional modelThe data load process must ensure that the raw and cleansed data is updated completely before populating the dimensional modelThe dimensional model must contain a date dimension. There is no existing data source for the date dimension. The Litware fiscal year matches the calendar year. The date dimension must always contain dates from 2010 through the end of the current year.The product pricing group logic must be maintained by the analytics engineers in a single location. The pricing group data must be made available in the data store for T-SOL. queries and in the default semantic model. The following logic must be used:• List prices that are less than or equal to 50 are in the low pricing group.• List prices that are greater than 50 and less than or equal to 1,000 are in the medium pricing group.• List prices that are greater than 1,000 are in the high pricing group.Security Requirements -Only Fabric administrators and the analytics team must be able to see the Fabric items created as part of the PoC.Litware identifies the following security requirements for the Fabric items in the AnalyticsPOC workspace:• Fabric administrators will be the workspace administrators.• The data engineers must be able to read from and write to the data store. No access must be granted to datasets or reports.• The analytics engineers must be able to read from, write to, and create schemas in the data store. They also must be able to create and share semantic models with the data analysts and view and modify all reports in the workspace.• The data scientists must be able to read from the data store, but not write to it. They will access the data by using a Spark notebook• The data analysts must have read access to only the dimensional model objects in the data store. They also must have access to create Power BI reports by using the semantic models created by the analytics engineers.• The date dimension must be available to all users of the data store.• The principle of least privilege must be followed.Both the default and custom semantic models must include only tables or views from the dimensional model in the data store. Litware already has the following Microsoft Entra security groups:• FabricAdmins: Fabric administrators• AnalyticsTeam: All the members of the analytics team• DataAnalysts: The data analysts on the analytics team• DataScientists: The data scientists on the analytics team• DataEngineers: The data engineers on the analytics team• AnalyticsEngineers: The analytics engineers on the analytics teamReport Requirements -The data analysts must create a customer satisfaction report that meets the following requirements:• Enables a user to select a product to filter customer survey responses to only those who have purchased that product.• Displays the average overall satisfaction score of all the surveys submitted during the last 12 months up to a selected dat.• Shows data as soon as the data is updated in the data store.• Ensures that the report and the semantic model only contain data from the current and previous year.• Ensures that the report respects any table-level security specified in the source data store.• Minimizes the execution time of report queries.You need to design a semantic model for the customer satisfaction report.Which data source authentication method and mode should you use? To answer, select the appropriate options in the answer area.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: April 7, 2024, 7:25 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/138090-exam-dp-600-topic-1-question-61-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 62 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 62
Topic #: 1

[All DP-600 Questions]

Case study -This is a case study. Case studies are not timed separately. You can use as much exam time as you would like to complete each case. However, there may be additional case studies and sections on this exam. You must manage your time to ensure that you are able to complete all questions included on this exam in the time provided.To answer the questions included in a case study, you will need to reference information that is provided in the case study. Case studies might contain exhibits and other resources that provide more information about the scenario that is described in the case study. Each question is independent of the other questions in this case study.At the end of this case study, a review screen will appear. This screen allows you to review your answers and to make changes before you move to the next section of the exam. After you begin a new section, you cannot return to this section.To start the case study -To display the first question in this case study, click the Next button. Use the buttons in the left pane to explore the content of the case study before you answer the questions. Clicking these buttons displays information such as business requirements, existing environment, and problem statements. If the case study has an All Information tab, note that the information displayed is identical to the information displayed on the subsequent tabs. When you are ready to answer a question, click the Question button to return to the question.Overview -Litware, Inc. is a manufacturing company that has offices throughout North America. The analytics team at Litware contains data engineers, analytics engineers, data analysts, and data scientists.Existing Environment -Fabric Environment -Litware has been using a Microsoft Power BI tenant for three years. Litware has NOT enabled any Fabric capacities and features.Available Data -Litware has data that must be analyzed as shown in the following table.The Product data contains a single table and the following columns.The customer satisfaction data contains the following tables:• Survey• Question• ResponseFor each survey submitted, the following occurs:• One row is added to the Survey table.• One row is added to the Response table for each question in the survey.The Question table contains the text of each survey question. The third question in each survey response is an overall satisfaction score. Customers can submit a survey after each purchase.User Problems -The analytics team has large volumes of data, some of which is semi-structured. The team wants to use Fabric to create a new data store.Product data is often classified into three pricing groups: high, medium, and low. This logic is implemented in several databases and semantic models, but the logic does NOT always match across implementations.Requirements -Planned Changes -Litware plans to enable Fabric features in the existing tenant. The analytics team will create a new data store as a proof of concept (PoC). The remaining Liware users will only get access to the Fabric features once the PoC is complete. The PoC will be completed by using a Fabric trial capacityThe following three workspaces will be created:• AnalyticsPOC: Will contain the data store, semantic models, reports pipelines, dataflow, and notebooks used to populate the data store• DataEngPOC: Will contain all the pipelines, dataflows, and notebooks used to populate OneLake• DataSciPOC: Will contain all the notebooks and reports created by the data scientistsThe following will be created in the AnalyticsPOC workspace:• A data store (type to be decided)• A custom semantic model• A default semantic model• Interactive reportsThe data engineers will create data pipelines to load data to OneLake either hourly or daily depending on the data source. The analytics engineers will create processes to ingest, transform, and load the data to the data store in the AnalyticsPOC workspace daily. Whenever possible, the data engineers will use low-code tools for data ingestion. The choice of which data cleansing and transformation tools to use will be at the data engineers’ discretion.All the semantic models and reports in the Analytics POC workspace will use the data store as the sole data source.Technical Requirements -The data store must support the following:• Read access by using T-SQL or Python• Semi-structured and unstructured data• Row-level security (RLS) for users executing T-SQL queriesFiles loaded by the data engineers to OneLake will be stored in the Parquet format and will meet Delta Lake specifications.Data will be loaded without transformation in one area of the AnalyticsPOC data store. The data will then be cleansed, merged, and transformed into a dimensional modelThe data load process must ensure that the raw and cleansed data is updated completely before populating the dimensional modelThe dimensional model must contain a date dimension. There is no existing data source for the date dimension. The Litware fiscal year matches the calendar year. The date dimension must always contain dates from 2010 through the end of the current year.The product pricing group logic must be maintained by the analytics engineers in a single location. The pricing group data must be made available in the data store for T-SOL. queries and in the default semantic model. The following logic must be used:• List prices that are less than or equal to 50 are in the low pricing group.• List prices that are greater than 50 and less than or equal to 1,000 are in the medium pricing group.• List prices that are greater than 1,000 are in the high pricing group.Security Requirements -Only Fabric administrators and the analytics team must be able to see the Fabric items created as part of the PoC.Litware identifies the following security requirements for the Fabric items in the AnalyticsPOC workspace:• Fabric administrators will be the workspace administrators.• The data engineers must be able to read from and write to the data store. No access must be granted to datasets or reports.• The analytics engineers must be able to read from, write to, and create schemas in the data store. They also must be able to create and share semantic models with the data analysts and view and modify all reports in the workspace.• The data scientists must be able to read from the data store, but not write to it. They will access the data by using a Spark notebook• The data analysts must have read access to only the dimensional model objects in the data store. They also must have access to create Power BI reports by using the semantic models created by the analytics engineers.• The date dimension must be available to all users of the data store.• The principle of least privilege must be followed.Both the default and custom semantic models must include only tables or views from the dimensional model in the data store. Litware already has the following Microsoft Entra security groups:• FabricAdmins: Fabric administrators• AnalyticsTeam: All the members of the analytics team• DataAnalysts: The data analysts on the analytics team• DataScientists: The data scientists on the analytics team• DataEngineers: The data engineers on the analytics team• AnalyticsEngineers: The analytics engineers on the analytics teamReport Requirements -The data analysts must create a customer satisfaction report that meets the following requirements:• Enables a user to select a product to filter customer survey responses to only those who have purchased that product.• Displays the average overall satisfaction score of all the surveys submitted during the last 12 months up to a selected dat.• Shows data as soon as the data is updated in the data store.• Ensures that the report and the semantic model only contain data from the current and previous year.• Ensures that the report respects any table-level security specified in the source data store.• Minimizes the execution time of report queries.You need to implement the date dimension in the data store. The solution must meet the technical requirements.What are two ways to achieve the goal? Each correct answer presents a complete solution.NOTE: Each correct selection is worth one point. 
Suggested Answer: AD 🗳️ 

A. Populate the date dimension table by using a dataflow.

B. Populate the date dimension table by using a Copy activity in a pipeline.

C. Populate the date dimension view by using T-SQL.

D. Populate the date dimension table by using a Stored procedure activity in a pipeline.

**Answer: A**

**Timestamp: April 4, 2024, 9:02 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/137913-exam-dp-600-topic-1-question-62-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 63 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 63
Topic #: 1

[All DP-600 Questions]

Case study -This is a case study. Case studies are not timed separately. You can use as much exam time as you would like to complete each case. However, there may be additional case studies and sections on this exam. You must manage your time to ensure that you are able to complete all questions included on this exam in the time provided.To answer the questions included in a case study, you will need to reference information that is provided in the case study. Case studies might contain exhibits and other resources that provide more information about the scenario that is described in the case study. Each question is independent of the other questions in this case study.At the end of this case study, a review screen will appear. This screen allows you to review your answers and to make changes before you move to the next section of the exam. After you begin a new section, you cannot return to this section.To start the case study -To display the first question in this case study, click the Next button. Use the buttons in the left pane to explore the content of the case study before you answer the questions. Clicking these buttons displays information such as business requirements, existing environment, and problem statements. If the case study has an All Information tab, note that the information displayed is identical to the information displayed on the subsequent tabs. When you are ready to answer a question, click the Question button to return to the question.Overview -Litware, Inc. is a manufacturing company that has offices throughout North America. The analytics team at Litware contains data engineers, analytics engineers, data analysts, and data scientists.Existing Environment -Fabric Environment -Litware has been using a Microsoft Power BI tenant for three years. Litware has NOT enabled any Fabric capacities and features.Available Data -Litware has data that must be analyzed as shown in the following table.The Product data contains a single table and the following columns.The customer satisfaction data contains the following tables:• Survey• Question• ResponseFor each survey submitted, the following occurs:• One row is added to the Survey table.• One row is added to the Response table for each question in the survey.The Question table contains the text of each survey question. The third question in each survey response is an overall satisfaction score. Customers can submit a survey after each purchase.User Problems -The analytics team has large volumes of data, some of which is semi-structured. The team wants to use Fabric to create a new data store.Product data is often classified into three pricing groups: high, medium, and low. This logic is implemented in several databases and semantic models, but the logic does NOT always match across implementations.Requirements -Planned Changes -Litware plans to enable Fabric features in the existing tenant. The analytics team will create a new data store as a proof of concept (PoC). The remaining Liware users will only get access to the Fabric features once the PoC is complete. The PoC will be completed by using a Fabric trial capacityThe following three workspaces will be created:• AnalyticsPOC: Will contain the data store, semantic models, reports pipelines, dataflow, and notebooks used to populate the data store• DataEngPOC: Will contain all the pipelines, dataflows, and notebooks used to populate OneLake• DataSciPOC: Will contain all the notebooks and reports created by the data scientistsThe following will be created in the AnalyticsPOC workspace:• A data store (type to be decided)• A custom semantic model• A default semantic model• Interactive reportsThe data engineers will create data pipelines to load data to OneLake either hourly or daily depending on the data source. The analytics engineers will create processes to ingest, transform, and load the data to the data store in the AnalyticsPOC workspace daily. Whenever possible, the data engineers will use low-code tools for data ingestion. The choice of which data cleansing and transformation tools to use will be at the data engineers’ discretion.All the semantic models and reports in the Analytics POC workspace will use the data store as the sole data source.Technical Requirements -The data store must support the following:• Read access by using T-SQL or Python• Semi-structured and unstructured data• Row-level security (RLS) for users executing T-SQL queriesFiles loaded by the data engineers to OneLake will be stored in the Parquet format and will meet Delta Lake specifications.Data will be loaded without transformation in one area of the AnalyticsPOC data store. The data will then be cleansed, merged, and transformed into a dimensional modelThe data load process must ensure that the raw and cleansed data is updated completely before populating the dimensional modelThe dimensional model must contain a date dimension. There is no existing data source for the date dimension. The Litware fiscal year matches the calendar year. The date dimension must always contain dates from 2010 through the end of the current year.The product pricing group logic must be maintained by the analytics engineers in a single location. The pricing group data must be made available in the data store for T-SOL. queries and in the default semantic model. The following logic must be used:• List prices that are less than or equal to 50 are in the low pricing group.• List prices that are greater than 50 and less than or equal to 1,000 are in the medium pricing group.• List prices that are greater than 1,000 are in the high pricing group.Security Requirements -Only Fabric administrators and the analytics team must be able to see the Fabric items created as part of the PoC.Litware identifies the following security requirements for the Fabric items in the AnalyticsPOC workspace:• Fabric administrators will be the workspace administrators.• The data engineers must be able to read from and write to the data store. No access must be granted to datasets or reports.• The analytics engineers must be able to read from, write to, and create schemas in the data store. They also must be able to create and share semantic models with the data analysts and view and modify all reports in the workspace.• The data scientists must be able to read from the data store, but not write to it. They will access the data by using a Spark notebook• The data analysts must have read access to only the dimensional model objects in the data store. They also must have access to create Power BI reports by using the semantic models created by the analytics engineers.• The date dimension must be available to all users of the data store.• The principle of least privilege must be followed.Both the default and custom semantic models must include only tables or views from the dimensional model in the data store. Litware already has the following Microsoft Entra security groups:• FabricAdmins: Fabric administrators• AnalyticsTeam: All the members of the analytics team• DataAnalysts: The data analysts on the analytics team• DataScientists: The data scientists on the analytics team• DataEngineers: The data engineers on the analytics team• AnalyticsEngineers: The analytics engineers on the analytics teamReport Requirements -The data analysts must create a customer satisfaction report that meets the following requirements:• Enables a user to select a product to filter customer survey responses to only those who have purchased that product.• Displays the average overall satisfaction score of all the surveys submitted during the last 12 months up to a selected dat.• Shows data as soon as the data is updated in the data store.• Ensures that the report and the semantic model only contain data from the current and previous year.• Ensures that the report respects any table-level security specified in the source data store.• Minimizes the execution time of report queries.You need to ensure the data loading activities in the AnalyticsPOC workspace are executed in the appropriate sequence. The solution must meet the technical requirements.What should you do? 
Suggested Answer: D 🗳️ 

A. Create a dataflow that has multiple steps and schedule the dataflow.

B. Create and schedule a Spark notebook.

C. Create and schedule a Spark job definition.

D. Create a pipeline that has dependencies between activities and schedule the pipeline.

**Answer: D**

**Timestamp: April 21, 2024, 10:43 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/139284-exam-dp-600-topic-1-question-63-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 64 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 64
Topic #: 1

[All DP-600 Questions]

Case study -This is a case study. Case studies are not timed separately. You can use as much exam time as you would like to complete each case. However, there may be additional case studies and sections on this exam. You must manage your time to ensure that you are able to complete all questions included on this exam in the time provided.To answer the questions included in a case study, you will need to reference information that is provided in the case study. Case studies might contain exhibits and other resources that provide more information about the scenario that is described in the case study. Each question is independent of the other questions in this case study.At the end of this case study, a review screen will appear. This screen allows you to review your answers and to make changes before you move to the next section of the exam. After you begin a new section, you cannot return to this section.To start the case study -To display the first question in this case study, click the Next button. Use the buttons in the left pane to explore the content of the case study before you answer the questions. Clicking these buttons displays information such as business requirements, existing environment, and problem statements. If the case study has an All Information tab, note that the information displayed is identical to the information displayed on the subsequent tabs. When you are ready to answer a question, click the Question button to return to the question.Overview -Contoso, Ltd. is a US-based health supplements company. Contoso has two divisions named Sales and Research. The Sales division contains two departments named Online Sales and Retail Sales. The Research division assigns internally developed product lines to individual teams of researchers and analysts.Existing Environment -Identity Environment -Contoso has a Microsoft Entra tenant named contoso.com. The tenant contains two groups named ResearchReviewersGroup1 and ResearchReviewersGroup2.Data Environment -Contoso has the following data environment:• The Sales division uses a Microsoft Power BI Premium capacity.• The semantic model of the Online Sales department includes a fact table named Orders that uses Import made. In the system of origin, the OrderID value represents the sequence in which orders are created.• The Research department uses an on-premises, third-party data warehousing product.• Fabric is enabled for contoso.com.• An Azure Data Lake Storage Gen2 storage account named storage1 contains Research division data for a product line named Productline1. The data is in the delta format.• A Data Lake Storage Gen2 storage account named storage2 contains Research division data for a product line named Productline2. The data is in the CSV format.Requirements -Planned Changes -Contoso plans to make the following changes:• Enable support for Fabric in the Power BI Premium capacity used by the Sales division.• Make all the data for the Sales division and the Research division available in Fabric.• For the Research division, create two Fabric workspaces named Productline1ws and Productine2ws.• In Productline1ws, create a lakehouse named Lakehouse1.• In Lakehouse1, create a shortcut to storage1 named ResearchProduct.Data Analytics Requirements -Contoso identifies the following data analytics requirements:• All the workspaces for the Sales division and the Research division must support all Fabric experiences.• The Research division workspaces must use a dedicated, on-demand capacity that has per-minute billing.• The Research division workspaces must be grouped together logically to support OneLake data hub filtering based on the department name.• For the Research division workspaces, the members of ResearchReviewersGroup1 must be able to read lakehouse and warehouse data and shortcuts by using SQL endpoints.• For the Research division workspaces, the members of ResearchReviewersGroup2 must be able to read lakehouse data by using Lakehouse explorer.• All the semantic models and reports for the Research division must use version control that supports branching.Data Preparation Requirements -Contoso identifies the following data preparation requirements:• The Research division data for Productline1 must be retrieved from Lakehouse1 by using Fabric notebooks.• All the Research division data in the lakehouses must be presented as managed tables in Lakehouse explorer.Semantic Model Requirements -Contoso identifies the following requirements for implementing and managing semantic models:• The number of rows added to the Orders table during refreshes must be minimized.• The semantic models in the Research division workspaces must use Direct Lake mode.General Requirements -Contoso identifies the following high-level requirements that must be considered for all solutions:• Follow the principle of least privilege when applicable.• Minimize implementation and maintenance effort when possible.You need to recommend which type of Fabric capacity SKU meets the data analytics requirements for the Research division.What should you recommend? 
Suggested Answer: D 🗳️ 

A. A

B. EM

C. P

D. F

**Answer: D**

**Timestamp: April 4, 2024, 11:09 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/137927-exam-dp-600-topic-1-question-64-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 65 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 65
Topic #: 1

[All DP-600 Questions]

HOTSPOT -Case study -This is a case study. Case studies are not timed separately. You can use as much exam time as you would like to complete each case. However, there may be additional case studies and sections on this exam. You must manage your time to ensure that you are able to complete all questions included on this exam in the time provided.To answer the questions included in a case study, you will need to reference information that is provided in the case study. Case studies might contain exhibits and other resources that provide more information about the scenario that is described in the case study. Each question is independent of the other questions in this case study.At the end of this case study, a review screen will appear. This screen allows you to review your answers and to make changes before you move to the next section of the exam. After you begin a new section, you cannot return to this section.To start the case study -To display the first question in this case study, click the Next button. Use the buttons in the left pane to explore the content of the case study before you answer the questions. Clicking these buttons displays information such as business requirements, existing environment, and problem statements. If the case study has an All Information tab, note that the information displayed is identical to the information displayed on the subsequent tabs. When you are ready to answer a question, click the Question button to return to the question.Overview -Contoso, Ltd. is a US-based health supplements company. Contoso has two divisions named Sales and Research. The Sales division contains two departments named Online Sales and Retail Sales. The Research division assigns internally developed product lines to individual teams of researchers and analysts.Existing Environment -Identity Environment -Contoso has a Microsoft Entra tenant named contoso.com. The tenant contains two groups named ResearchReviewersGroup1 and ResearchReviewersGroup2.Data Environment -Contoso has the following data environment:• The Sales division uses a Microsoft Power BI Premium capacity.• The semantic model of the Online Sales department includes a fact table named Orders that uses Import made. In the system of origin, the OrderID value represents the sequence in which orders are created.• The Research department uses an on-premises, third-party data warehousing product.• Fabric is enabled for contoso.com.• An Azure Data Lake Storage Gen2 storage account named storage1 contains Research division data for a product line named Productline1. The data is in the delta format.• A Data Lake Storage Gen2 storage account named storage2 contains Research division data for a product line named Productline2. The data is in the CSV format.Requirements -Planned Changes -Contoso plans to make the following changes:• Enable support for Fabric in the Power BI Premium capacity used by the Sales division.• Make all the data for the Sales division and the Research division available in Fabric.• For the Research division, create two Fabric workspaces named Productline1ws and Productine2ws.• In Productline1ws, create a lakehouse named Lakehouse1.• In Lakehouse1, create a shortcut to storage1 named ResearchProduct.Data Analytics Requirements -Contoso identifies the following data analytics requirements:• All the workspaces for the Sales division and the Research division must support all Fabric experiences.• The Research division workspaces must use a dedicated, on-demand capacity that has per-minute billing.• The Research division workspaces must be grouped together logically to support OneLake data hub filtering based on the department name.• For the Research division workspaces, the members of ResearchReviewersGroup1 must be able to read lakehouse and warehouse data and shortcuts by using SQL endpoints.• For the Research division workspaces, the members of ResearchReviewersGroup2 must be able to read lakehouse data by using Lakehouse explorer.• All the semantic models and reports for the Research division must use version control that supports branching.Data Preparation Requirements -Contoso identifies the following data preparation requirements:• The Research division data for Productline1 must be retrieved from Lakehouse1 by using Fabric notebooks.• All the Research division data in the lakehouses must be presented as managed tables in Lakehouse explorer.Semantic Model Requirements -Contoso identifies the following requirements for implementing and managing semantic models:• The number of rows added to the Orders table during refreshes must be minimized.• The semantic models in the Research division workspaces must use Direct Lake mode.General Requirements -Contoso identifies the following high-level requirements that must be considered for all solutions:• Follow the principle of least privilege when applicable.• Minimize implementation and maintenance effort when possible.You need to migrate the Research division data for Productline1. The solution must meet the data preparation requirements.How should you complete the code? To answer, select the appropriate options in the answer area.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: April 15, 2024, 9:11 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/138717-exam-dp-600-topic-1-question-65-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 66 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 66
Topic #: 1

[All DP-600 Questions]

Case study -This is a case study. Case studies are not timed separately. You can use as much exam time as you would like to complete each case. However, there may be additional case studies and sections on this exam. You must manage your time to ensure that you are able to complete all questions included on this exam in the time provided.To answer the questions included in a case study, you will need to reference information that is provided in the case study. Case studies might contain exhibits and other resources that provide more information about the scenario that is described in the case study. Each question is independent of the other questions in this case study.At the end of this case study, a review screen will appear. This screen allows you to review your answers and to make changes before you move to the next section of the exam. After you begin a new section, you cannot return to this section.To start the case study -To display the first question in this case study, click the Next button. Use the buttons in the left pane to explore the content of the case study before you answer the questions. Clicking these buttons displays information such as business requirements, existing environment, and problem statements. If the case study has an All Information tab, note that the information displayed is identical to the information displayed on the subsequent tabs. When you are ready to answer a question, click the Question button to return to the question.Overview -Contoso, Ltd. is a US-based health supplements company. Contoso has two divisions named Sales and Research. The Sales division contains two departments named Online Sales and Retail Sales. The Research division assigns internally developed product lines to individual teams of researchers and analysts.Existing Environment -Identity Environment -Contoso has a Microsoft Entra tenant named contoso.com. The tenant contains two groups named ResearchReviewersGroup1 and ResearchReviewersGroup2.Data Environment -Contoso has the following data environment:• The Sales division uses a Microsoft Power BI Premium capacity.• The semantic model of the Online Sales department includes a fact table named Orders that uses Import made. In the system of origin, the OrderID value represents the sequence in which orders are created.• The Research department uses an on-premises, third-party data warehousing product.• Fabric is enabled for contoso.com.• An Azure Data Lake Storage Gen2 storage account named storage1 contains Research division data for a product line named Productline1. The data is in the delta format.• A Data Lake Storage Gen2 storage account named storage2 contains Research division data for a product line named Productline2. The data is in the CSV format.Requirements -Planned Changes -Contoso plans to make the following changes:• Enable support for Fabric in the Power BI Premium capacity used by the Sales division.• Make all the data for the Sales division and the Research division available in Fabric.• For the Research division, create two Fabric workspaces named Productline1ws and Productine2ws.• In Productline1ws, create a lakehouse named Lakehouse1.• In Lakehouse1, create a shortcut to storage1 named ResearchProduct.Data Analytics Requirements -Contoso identifies the following data analytics requirements:• All the workspaces for the Sales division and the Research division must support all Fabric experiences.• The Research division workspaces must use a dedicated, on-demand capacity that has per-minute billing.• The Research division workspaces must be grouped together logically to support OneLake data hub filtering based on the department name.• For the Research division workspaces, the members of ResearchReviewersGroup1 must be able to read lakehouse and warehouse data and shortcuts by using SQL endpoints.• For the Research division workspaces, the members of ResearchReviewersGroup2 must be able to read lakehouse data by using Lakehouse explorer.• All the semantic models and reports for the Research division must use version control that supports branching.Data Preparation Requirements -Contoso identifies the following data preparation requirements:• The Research division data for Productline1 must be retrieved from Lakehouse1 by using Fabric notebooks.• All the Research division data in the lakehouses must be presented as managed tables in Lakehouse explorer.Semantic Model Requirements -Contoso identifies the following requirements for implementing and managing semantic models:• The number of rows added to the Orders table during refreshes must be minimized.• The semantic models in the Research division workspaces must use Direct Lake mode.General Requirements -Contoso identifies the following high-level requirements that must be considered for all solutions:• Follow the principle of least privilege when applicable.• Minimize implementation and maintenance effort when possible.What should you use to implement calculation groups for the Research division semantic models? 
Suggested Answer: D 🗳️ 

A. Microsoft Power BI Desktop

B. the Power BI service

C. DAX Studio

D. Tabular Editor

**Answer: D**

**Timestamp: April 4, 2024, 10:29 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/137923-exam-dp-600-topic-1-question-66-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 67 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 67
Topic #: 1

[All DP-600 Questions]

HOTSPOT -Case study -This is a case study. Case studies are not timed separately. You can use as much exam time as you would like to complete each case. However, there may be additional case studies and sections on this exam. You must manage your time to ensure that you are able to complete all questions included on this exam in the time provided.To answer the questions included in a case study, you will need to reference information that is provided in the case study. Case studies might contain exhibits and other resources that provide more information about the scenario that is described in the case study. Each question is independent of the other questions in this case study.At the end of this case study, a review screen will appear. This screen allows you to review your answers and to make changes before you move to the next section of the exam. After you begin a new section, you cannot return to this section.To start the case study -To display the first question in this case study, click the Next button. Use the buttons in the left pane to explore the content of the case study before you answer the questions. Clicking these buttons displays information such as business requirements, existing environment, and problem statements. If the case study has an All Information tab, note that the information displayed is identical to the information displayed on the subsequent tabs. When you are ready to answer a question, click the Question button to return to the question.Overview -Contoso, Ltd. is a US-based health supplements company. Contoso has two divisions named Sales and Research. The Sales division contains two departments named Online Sales and Retail Sales. The Research division assigns internally developed product lines to individual teams of researchers and analysts.Existing Environment -Identity Environment -Contoso has a Microsoft Entra tenant named contoso.com. The tenant contains two groups named ResearchReviewersGroup1 and ResearchReviewersGroup2.Data Environment -Contoso has the following data environment:• The Sales division uses a Microsoft Power BI Premium capacity.• The semantic model of the Online Sales department includes a fact table named Orders that uses Import made. In the system of origin, the OrderID value represents the sequence in which orders are created.• The Research department uses an on-premises, third-party data warehousing product.• Fabric is enabled for contoso.com.• An Azure Data Lake Storage Gen2 storage account named storage1 contains Research division data for a product line named Productline1. The data is in the delta format.• A Data Lake Storage Gen2 storage account named storage2 contains Research division data for a product line named Productline2. The data is in the CSV format.Requirements -Planned Changes -Contoso plans to make the following changes:• Enable support for Fabric in the Power BI Premium capacity used by the Sales division.• Make all the data for the Sales division and the Research division available in Fabric.• For the Research division, create two Fabric workspaces named Productline1ws and Productine2ws.• In Productline1ws, create a lakehouse named Lakehouse1.• In Lakehouse1, create a shortcut to storage1 named ResearchProduct.Data Analytics Requirements -Contoso identifies the following data analytics requirements:• All the workspaces for the Sales division and the Research division must support all Fabric experiences.• The Research division workspaces must use a dedicated, on-demand capacity that has per-minute billing.• The Research division workspaces must be grouped together logically to support OneLake data hub filtering based on the department name.• For the Research division workspaces, the members of ResearchReviewersGroup1 must be able to read lakehouse and warehouse data and shortcuts by using SQL endpoints.• For the Research division workspaces, the members of ResearchReviewersGroup2 must be able to read lakehouse data by using Lakehouse explorer.• All the semantic models and reports for the Research division must use version control that supports branching.Data Preparation Requirements -Contoso identifies the following data preparation requirements:• The Research division data for Productline1 must be retrieved from Lakehouse1 by using Fabric notebooks.• All the Research division data in the lakehouses must be presented as managed tables in Lakehouse explorer.Semantic Model Requirements -Contoso identifies the following requirements for implementing and managing semantic models:The number of rows added to the Orders table during refreshes must be minimized.• The semantic models in the Research division workspaces must use Direct Lake mode.General Requirements -Contoso identifies the following high-level requirements that must be considered for all solutions:• Follow the principle of least privilege when applicable.• Minimize implementation and maintenance effort when possible.Which workspace role assignments should you recommend for ResearchReviewersGroup1 and ResearchReviewersGroup2? To answer, select the appropriate options in the answer area.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: April 6, 2024, 10:49 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/138020-exam-dp-600-topic-1-question-67-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 68 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 68
Topic #: 1

[All DP-600 Questions]

HOTSPOT -You have a Fabric tenant.You need to configure OneLake security for users shown in the following table.The solution must follow the principle of least privilege.Which permission should you assign to each user? To answer, select the appropriate options in the answer area.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: April 4, 2024, 10:40 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/137925-exam-dp-600-topic-1-question-68-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 69 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 69
Topic #: 1

[All DP-600 Questions]

You have an Azure Repos repository named Repo1 and a Fabric-enabled Microsoft Power BI Premium capacity. The capacity contains two workspaces named Workspace1 and Workspace2. Git integration is enabled at the workspace level.You plan to use Microsoft Power BI Desktop and Workspace1 to make version-controlled changes to a semantic model stored in Repo1. The changes will be built and deployed to Workspace2 by using Azure Pipelines.You need to ensure that report and semantic model definitions are saved as individual text files in a folder hierarchy. The solution must minimize development and maintenance effort.In which file format should you save the changes? 
Suggested Answer: A 🗳️ 

A. PBIP

B. PBIDS

C. PBIT

D. PBIX

**Answer: A**

**Timestamp: April 5, 2024, 6:58 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/137945-exam-dp-600-topic-1-question-69-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 70 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 70
Topic #: 1

[All DP-600 Questions]

DRAG DROP -You are implementing a medallion architecture in a single Fabric workspace.You have a lakehouse that contains the Bronze and Silver layers and a warehouse that contains the Gold layer.You create the items required to populate the layers as shown in the following table.You need to ensure that the layers are populated daily in sequential order such that Silver is populated only after Bronze is complete, and Gold is populated only after Silver is complete. The solution must minimize development effort and complexity.What should you use to execute each set of items? To answer, drag the appropriate options to the correct items. Each option may be used once, more than once, or not at all. You may need to drag the split bar between panes or scroll to view content.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: April 19, 2024, 10:03 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/139155-exam-dp-600-topic-1-question-70-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 71 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 71
Topic #: 1

[All DP-600 Questions]

DRAG DROP -You are building a solution by using a Fabric notebook.You have a Spark DataFrame assigned to a variable named df. The DataFrame returns four columns.You need to change the data type of a string column named Age to integer. The solution must return a DataFrame that includes all the columns.How should you complete the code? To answer, drag the appropriate values to the correct targets. Each value may be used once, more than once, or not at all. You may need to drag the split bar between panes or scroll to view content.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: April 7, 2024, 8:52 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/138094-exam-dp-600-topic-1-question-71-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 72 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 72
Topic #: 1

[All DP-600 Questions]

HOTSPOT -You have an Azure Data Lake Storage Gen2 account named storage1 that contains a Parquet file named sales.parquet.You have a Fabric tenant that contains a workspace named Workspace1.Using a notebook in Workspace1, you need to load the content of the file to the default lakehouse. The solution must ensure that the content will display automatically as a table named Sales in Lakehouse explorer.How should you complete the code? To answer, select the appropriate options in the answer area.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: April 5, 2024, 4:38 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/137977-exam-dp-600-topic-1-question-72-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 73 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 73
Topic #: 1

[All DP-600 Questions]

You have a Fabric workspace named Workspace1 that contains a lakehouse named Lakehouse1.In Workspace1, you create a data pipeline named Pipeline1.You have CSV files stored in an Azure Storage account.You need to add an activity to Pipeline1 that will copy data from the CSV files to Lakehouse1. The activity must support Power Query M formula language expressions.Which type of activity should you add? 
Suggested Answer: A 🗳️ 

A. Dataflow

B. Notebook

C. Script

D. Copy data

**Answer: A**

**Timestamp: April 16, 2024, 9:02 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/138811-exam-dp-600-topic-1-question-73-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 74 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 74
Topic #: 1

[All DP-600 Questions]

HOTSPOT -You have a Fabric tenant that contains lakehouse named Lakehouse1. Lakehouse1 contains a Delta table with eight columns.You receive new data that contains the same eight columns and two additional columns.You create a Spark DataFrame and assign the DataFrame to a variable named df. The DataFrame contains the new data.You need to add the new data to the Delta table to meet the following requirements:• Keep all the existing rows.• Ensure that all the new data is added to the table.How should you complete the code? To answer, select the appropriate options in the answer area.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: April 5, 2024, 9:22 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/137950-exam-dp-600-topic-1-question-74-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 75 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 75
Topic #: 1

[All DP-600 Questions]

HOTSPOT -You have a Fabric warehouse that contains a table named Sales.Orders. Sales.Orders contains the following columns.You need to write a T-SQL query that will return the following columns.How should you complete the code? To answer, select the appropriate options in the answer area.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: April 19, 2024, 8:05 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/139147-exam-dp-600-topic-1-question-75-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 76 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 76
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant that contains a lakehouse.You plan to use a visual query to merge two tables.You need to ensure that the query returns all the rows in both tables.Which type of join should you use? 
Suggested Answer: B 🗳️ 

A. inner

B. full outer

C. left outer

D. right anti

E. right outer

F. left anti

**Answer: B**

**Timestamp: April 19, 2024, 10:07 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/139156-exam-dp-600-topic-1-question-76-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 77 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 77
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant that contains a lakehouse named Lakehouse1. Lakehouse1 contains a Delta table that has one million Parquet files.You need to remove files that were NOT referenced by the table during the past 30 days. The solution must ensure that the transaction log remains consistent, and the ACID properties of the table are maintained.What should you do? 
Suggested Answer: D 🗳️ 

A. From OneLake file explorer, delete the files.

B. Run the OPTIMIZE command and specify the Z-order parameter.

C. Run the OPTIMIZE command and specify the V-order parameter.

D. Run the VACUUM command.

**Answer: D**

**Timestamp: April 5, 2024, 7:28 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/137987-exam-dp-600-topic-1-question-77-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 78 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 78
Topic #: 1

[All DP-600 Questions]

DRAG DROP -You are implementing two dimension tables named Customers and Products in a Fabric warehouse.You need to use slowly changing dimension (SCD) to manage the versioning of data. The solution must meet the requirements shown in the following table.Which type of SCD should you use for each table? To answer, drag the appropriate SCD types to the correct tables. Each SCD type may be used once, more than once, or not at all. You may need to drag the split bar between panes or scroll to view content.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: April 5, 2024, 7:33 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/137988-exam-dp-600-topic-1-question-78-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 79 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 79
Topic #: 1

[All DP-600 Questions]

You have a Fabric workspace named Workspace1 and an Azure SQL database.You plan to create a dataflow that will read data from the database, and then transform the data by performing an inner join.You need to ignore spaces in the values when performing the inner join. The solution must minimize development effort.What should you do? 
Suggested Answer: B 🗳️ 

A. Append the queries by using fuzzy matching.

B. Merge the queries by using fuzzy matching.

C. Append the queries by using a lookup table.

D. Merge the queries by using a lookup table.

**Answer: B**

**Timestamp: April 15, 2024, 9:58 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/138724-exam-dp-600-topic-1-question-79-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 80 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 80
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant that contains a warehouse named Warehouse1. Warehouse1 contains two schemas name schema1 and schema2 and a table named schema1.city.You need to make a copy of schema1.city in schema2. The solution must minimize the copying of data.Which T-SQL statement should you run? 
Suggested Answer: C 🗳️ 

A. INSERT INTO schema2.city SELECT * FROM schema1.city;

B. SELECT * INTO schema2.city FROM schema1.city;

C. CREATE TABLE schema2.city AS CLONE OF schema1.city;

D. CREATE TABLE schema2.city AS SELECT * FROM schema1.city;

**Answer: C**

**Timestamp: April 6, 2024, 3:10 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/138029-exam-dp-600-topic-1-question-80-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 81 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 81
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant that contains a lakehouse named Lakehouse1.You need to prevent new tables added to Lakehouse1 from being added automatically to the default semantic model of the lakehouse.What should you configure? 
Suggested Answer: A 🗳️ 

A. the SQL analytics endpoint settings

B. the semantic model settings

C. the workspace settings

D. the Lakehouse1 settings

**Answer: A**

**Timestamp: April 5, 2024, 3:07 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/137972-exam-dp-600-topic-1-question-81-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 82 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 82
Topic #: 1

[All DP-600 Questions]

HOTSPOT -You have a Fabric tenant that contains a workspace named Workspace1. Workspace1 contains a lakehouse named Lakehouse1 and a warehouse named Warehouse1.You need to create a new table in Warehouse1 named POSCustomers by querying the customer table in Lakehouse1.How should you complete the T-SQL statement? To answer, select the appropriate options in the answer area.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: April 7, 2024, 3:36 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/138078-exam-dp-600-topic-1-question-82-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 83 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 83
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant.You are creating an Azure Data Factory pipeline.You have a stored procedure that returns the number of active customers and their average sales for the current month.You need to add an activity that will execute the stored procedure in a warehouse. The returned values must be available to the downstream activities of the pipeline.Which type of activity should you add? 
Suggested Answer: D 🗳️ 

A. Switch

B. Copy data

C. Append variable

D. Lookup

**Answer: D**

**Timestamp: April 5, 2024, 8:50 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/137992-exam-dp-600-topic-1-question-83-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 84 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 84
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant that contains two workspaces named Workspace1 and Workspace2. Workspace1 contains a lakehouse named Lakehouse1. Workspace2 contains a lakehouse named Lakehouse2. Lakehouse1 contains a table named dbo.Sales. Lakehouse2 contains a table named dbo.Customers.You need to ensure that you can write queries that reference both dbo.Sales and dbo.Customers in the same SQL query without making additional copies of the tables.What should you use? 
Suggested Answer: A 🗳️ 

A. a shortcut

B. a dataflow

C. a view

D. a managed table

**Answer: A**

**Timestamp: April 5, 2024, 8:49 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/137991-exam-dp-600-topic-1-question-84-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 85 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 85
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant that contains a warehouse.You are designing a star schema model that will contain a customer dimension. The customer dimension table will be a Type 2 slowly changing dimension (SCD).You need to recommend which columns to add to the table. The columns must NOT already exist in the source.Which three types of columns should you recommend? Each correct answer presents part of the solution.NOTE: Each correct answer is worth one point. 
Suggested Answer: CDE 🗳️ 

A. a foreign key

B. a natural key

C. an effective end date and time

D. a surrogate key

E. an effective start date and time

**Answer: C**

**Timestamp: April 24, 2024, 11:32 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/139495-exam-dp-600-topic-1-question-85-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 86 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 86
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant.You plan to create a data pipeline named Pipeline1. Pipeline1 will include two activities that will execute in sequence.You need to ensure that a failure of the first activity will NOT block the second activity.Which conditional path should you configure between the first activity and the second activity? 
Suggested Answer: B 🗳️ 

A. Upon Failure

B. Upon Completion

C. Upon Skip

D. Upon Skip

**Answer: B**

**Timestamp: April 6, 2024, 7:26 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/138011-exam-dp-600-topic-1-question-86-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 87 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 87
Topic #: 1

[All DP-600 Questions]

You have a Microsoft Power BI semantic model.You need to identify any surrogate key columns in the model that have the Summarize By property set to a value other than to None. The solution must minimize effort.What should you use? 
Suggested Answer: D 🗳️ 

A. DAX Formatter in DAX Studio

B. Model explorer in Microsoft Power BI Desktop

C. Model view in Microsoft Power BI Desktop

D. Best Practice Analyzer in Tabular Editor

**Answer: D**

**Timestamp: April 7, 2024, 11:05 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/138102-exam-dp-600-topic-1-question-87-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 88 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 88
Topic #: 1

[All DP-600 Questions]

DRAG DROP -You have a Fabric tenant that contains a Microsoft Power BI report named Report1.Report1 is slow to render. You suspect that an inefficient DAX query is being executed.You need to identify the slowest DAX query, and then review how long the query spends in the formula engine as compared to the storage engine.Which five actions should you perform in sequence? To answer, move the appropriate actions from the list of actions to the answer area and arrange them in the correct order. 
Suggested Answer: 

**Answer: **

**Timestamp: April 6, 2024, 1:16 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/138005-exam-dp-600-topic-1-question-88-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 89 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 89
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant that contains a semantic model. The model contains 15 tables.You need to programmatically change each column that ends in the word Key to meet the following requirements:• Hide the column.• Set Nullable to False• Set Summarize By to None.• Set Available in MDX to False.• Mark the column as a key column.What should you use? 
Suggested Answer: C 🗳️ 

A. Microsoft Power BI Desktop

B. ALM Toolkit

C. Tabular Editor

D. DAX Studio

**Answer: C**

**Timestamp: April 18, 2024, 7:59 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/139059-exam-dp-600-topic-1-question-89-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 90 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 90
Topic #: 1

[All DP-600 Questions]

HOTSPOT -You have a Microsoft Power BI semantic model.You plan to implement calculation groups.You need to create a calculation item that will change the context from the selected date to month-to-date (MTD).How should you complete the DAX expression? To answer, select the appropriate options in the answer area.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: April 6, 2024, 1:30 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/138007-exam-dp-600-topic-1-question-90-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 91 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 91
Topic #: 1

[All DP-600 Questions]

You have a Microsoft Power BI report named Report1 that uses a Fabric semantic model.Users discover that Report1 renders slowly.You open Performance analyzer and identify that a visual named Orders By Date is the slowest to render. The duration breakdown for Orders By Date is shown in the following table.What will provide the greatest reduction in the rendering duration of Report1? 
Suggested Answer: D 🗳️ 

A. Enable automatic page refresh.

B. Optimize the DAX query of Orders By Date by using DAX Studio.

C. Change the visual type of Orders By Date.

D. Reduce the number of visuals in Report1.

**Answer: D**

**Timestamp: April 7, 2024, 11:20 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/138103-exam-dp-600-topic-1-question-91-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 92 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 92
Topic #: 1

[All DP-600 Questions]

You have a custom Direct Lake semantic model named Model1 that has one billion rows of data.You use Tabular Editor to connect to Model1 by using the XMLA endpoint.You need to ensure that when users interact with reports based on Model1, their queries always use Direct Lake mode.What should you do? 
Suggested Answer: D 🗳️ 

A. From Model, configure the Default Mode option.

B. From Partitions, configure the Mode option.

C. From Model, configure the Storage Location option.

D. From Model, configure the Direct Lake Behavior option.

**Answer: D**

**Timestamp: April 6, 2024, 1:28 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/138006-exam-dp-600-topic-1-question-92-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 93 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 93
Topic #: 1

[All DP-600 Questions]

DRAG DROP -You create a semantic model by using Microsoft Power BI Desktop. The model contains one security role named SalesRegionManager and the following tables:• Sales• SalesRegion• SalesAddressYou need to modify the model to ensure that users assigned the SalesRegionManager role cannot see a column named Address in SalesAddress.Which three actions should you perform in sequence? To answer, move the appropriate actions from the list of actions to the answer area and arrange them in the correct order. 
Suggested Answer: 

**Answer: **

**Timestamp: April 6, 2024, 1:42 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/138008-exam-dp-600-topic-1-question-93-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 94 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 94
Topic #: 1

[All DP-600 Questions]

You have a Microsoft Power BI semantic model that contains measures. The measures use multiple CALCULATE functions and a FILTER function.You are evaluating the performance of the measures.In which use case will replacing the FILTER function with the KEEPFILTERS function reduce execution time? 
Suggested Answer: D 🗳️ 

A. when the FILTER function uses a nested calculate function

B. when the FILTER function references a measure

C. when the FILTER function references columns from multiple tables

D. when the FILTER function references a column from a single table that uses Import mode

**Answer: D**

**Timestamp: April 8, 2024, 3:45 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/138114-exam-dp-600-topic-1-question-94-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 95 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 95
Topic #: 1

[All DP-600 Questions]

You have a semantic model named Model1. Model1 contains five tables that all use Import mode. Model1 contains a dynamic row-level security (RLS) role named HR. The HR role filters employee data so that HR managers only see the data of the department to which they are assigned.You publish Model1 to a Fabric tenant and configure RLS role membership. You share the model and related reports to users.An HR manager reports that the data they see in a report is incomplete.What should you do to validate the data seen by the HR Manager? 
Suggested Answer: C 🗳️ 

A. Select Test as role to view the data as the HR role.

B. Filter the data in the report to match the intended logic of the filter for the HR department.

C. Select Test as role to view the report as the HR manager.

D. Ask the HR manager to open the report in Microsoft Power BI Desktop.

**Answer: C**

**Timestamp: April 6, 2024, 1:45 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/138009-exam-dp-600-topic-1-question-95-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 96 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 96
Topic #: 1

[All DP-600 Questions]

You have a Microsoft Fabric tenant that contains a dataflow.You are exploring a new semantic model.From Power Query, you need to view column information as shown in the following exhibit.Which three Data view options should you select? Each correct answer presents part of the solution. 
Suggested Answer: ACD 🗳️ 

A. Show column value distribution

B. Enable details pane

C. Enable column profile

D. Show column quality details

E. Show column profile in details pane

**Answer: A**

**Timestamp: April 5, 2024, 9:54 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/137953-exam-dp-600-topic-1-question-96-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 97 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 97
Topic #: 1

[All DP-600 Questions]

HOTSPOT -You have a Fabric warehouse that contains a table named Sales.Products. Sales.Products contains the following columns.You need to write a T-SQL query that will return the following columns.How should you complete the code? To answer, select the appropriate options in the answer area.NOTE: Each correct answer is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: April 5, 2024, 5:13 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/137979-exam-dp-600-topic-1-question-97-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 98 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 98
Topic #: 1

[All DP-600 Questions]

You have a Fabric notebook that has the Python code and output shown in the following exhibit.Which type of analytics are you performing? 
Suggested Answer: A 🗳️ 

A. descriptive

B. diagnostic

C. prescriptive

D. predictive

**Answer: A**

**Timestamp: April 7, 2024, 3:56 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/138079-exam-dp-600-topic-1-question-98-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 99 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 99
Topic #: 1

[All DP-600 Questions]

HOTSPOT -You have a Fabric warehouse that contains a table named Sales.Orders. Sales.Orders contains the following columns.You need to write a T-SQL query that will return the following columns.How should you complete the code? To answer, select the appropriate options in the answer area.NOTE: Each correct answer is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: April 7, 2024, 3:59 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/138080-exam-dp-600-topic-1-question-99-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 100 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 100
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant that contains JSON files in OneLake. The files have one billion items.You plan to perform time series analysis of the items.You need to transform the data, visualize the data to find insights, perform anomaly detection, and share the insights with other business users. The solution must meet the following requirements:• Use parallel processing.• Minimize the duplication of data.• Minimize how long it takes to load the data.What should you use to transform and visualize the data? 
Suggested Answer: A 🗳️ 

A. the PySpark library in a Fabric notebook

B. the pandas library in a Fabric notebook

C. a Microsoft Power BI report that uses core visuals

**Answer: A**

**Timestamp: April 7, 2024, 3:59 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/138081-exam-dp-600-topic-1-question-100-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 101 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 101
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant that contains customer churn data stored as Parquet files in OneLake. The data contains details about customer demographics and product usage.You create a Fabric notebook to read the data into a Spark DataFrame. You then create column charts in the notebook that show the distribution of retained customers as compared to lost customers based on geography, the number of products purchased, age, and customer tenure.Which type of analytics are you performing? 
Suggested Answer: B 🗳️ 

A. diagnostic

B. descriptive

C. prescriptive

D. predictive

**Answer: B**

**Timestamp: April 22, 2024, 1:21 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/139329-exam-dp-600-topic-1-question-101-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 102 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 102
Topic #: 1

[All DP-600 Questions]

HOTSPOT -You have a Fabric tenant that contains a semantic model. The model contains data about retail stores.You need to write a DAX query that will be executed by using the XMLA endpoint. The query must return the total amount of sales from the same period last year.How should you complete the DAX expression? To answer, select the appropriate options in the answer area.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: April 5, 2024, 8:07 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/137946-exam-dp-600-topic-1-question-102-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 103 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 103
Topic #: 1

[All DP-600 Questions]

You have a Fabric workspace named Workspace1 that contains a dataflow named Dataflow1. Dataflow1 returns 500 rows of data.You need to identify the min and max values for each column in the query results.Which three Data view options should you select? Each correct answer presents part of the solution.NOTE: Each correct answer is worth one point. 
Suggested Answer: BCE 🗳️ 

A. Show column value distribution

B. Enable column profile

C. Show column profile in details pane

D. Show column quality details

E. Enable details pane

**Answer: B**

**Timestamp: April 5, 2024, 5:33 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/137981-exam-dp-600-topic-1-question-103-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 104 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 104
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant that contains a Microsoft Power BI report.You are exploring a new semantic model.You need to display the following column statistics:• Count• Average• Null count• Distinct count• Standard deviationWhich Power Query function should you run? 
Suggested Answer: D 🗳️ 

A. Table.schema

B. Table.view

C. Table.FuzzyGroup

D. Table.Profile

**Answer: D**

**Timestamp: April 5, 2024, 9:36 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/137993-exam-dp-600-topic-1-question-104-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 105 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 105
Topic #: 1

[All DP-600 Questions]

Note: This question is part of a series of questions that present the same scenario. Each question in the series contains a unique solution that might meet the stated goals. Some question sets might have more than one correct solution, while others might not have a correct solution.After you answer a question in this section, you will NOT be able to return to it. As a result, these questions will not appear in the review screen.You have a Fabric tenant that contains a lakehouse named Lakehouse1. Lakehouse1 contains a Delta table named Customer.When you query Customer, you discover that the query is slow to execute. You suspect that maintenance was NOT performed on the table.You need to identify whether maintenance tasks were performed on Customer.Solution: You run the following Spark SQL statement:DESCRIBE DETAIL customer -Does this meet the goal? 
Suggested Answer: B 🗳️ 

A. Yes

B. No

**Answer: B**

**Timestamp: April 22, 2024, 9:11 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/139347-exam-dp-600-topic-1-question-105-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 106 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 106
Topic #: 1

[All DP-600 Questions]

Note: This question is part of a series of questions that present the same scenario. Each question in the series contains a unique solution that might meet the stated goals. Some question sets might have more than one correct solution, while others might not have a correct solution.After you answer a question in this section, you will NOT be able to return to it. As a result, these questions will not appear in the review screen.You have a Fabric tenant that contains a new semantic model in OneLake.You use a Fabric notebook to read the data into a Spark DataFrame.You need to evaluate the data to calculate the min, max, mean, and standard deviation values for all the string and numeric columns.Solution: You use the following PySpark expression:df.explain().show()Does this meet the goal? 
Suggested Answer: B 🗳️ 

A. Yes

B. No

**Answer: B**

**Timestamp: April 23, 2024, 9:45 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/139460-exam-dp-600-topic-1-question-106-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 107 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 107
Topic #: 1

[All DP-600 Questions]

Note: This question is part of a series of questions that present the same scenario. Each question in the series contains a unique solution that might meet the stated goals. Some question sets might have more than one correct solution, while others might not have a correct solution.After you answer a question in this section, you will NOT be able to return to it. As a result, these questions will not appear in the review screen.You have a Fabric tenant that contains a semantic model named Model1.You discover that the following query performs slowly against Model1.You need to reduce the execution time of the query.Solution: You replace line 4 by using the following code:ISEMPTY ( RELATEDTABLE ( 'Order Item' ) )Does this meet the goal? 
Suggested Answer: B 🗳️ 

A. Yes

B. No

**Answer: B**

**Timestamp: April 24, 2024, 7:20 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/139527-exam-dp-600-topic-1-question-107-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 108 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 108
Topic #: 1

[All DP-600 Questions]

Note: This question is part of a series of questions that present the same scenario. Each question in the series contains a unique solution that might meet the stated goals. Some question sets might have more than one correct solution, while others might not have a correct solution.After you answer a question in this section, you will NOT be able to return to it. As a result, these questions will not appear in the review screen.You have a Fabric tenant that contains a semantic model named Model1.You discover that the following query performs slowly against Model1.You need to reduce the execution time of the query.Solution: You replace line 4 by using the following code:NOT ISEMPTY ( CALCULATETABLE ( 'Order Item ' ) )Does this meet the goal? 
Suggested Answer: A 🗳️ 

A. Yes

B. No

**Answer: A**

**Timestamp: April 8, 2024, 1:08 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/138108-exam-dp-600-topic-1-question-108-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 109 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 109
Topic #: 1

[All DP-600 Questions]

Note: This question is part of a series of questions that present the same scenario. Each question in the series contains a unique solution that might meet the stated goals. Some question sets might have more than one correct solution, while others might not have a correct solution.After you answer a question in this section, you will NOT be able to return to it. As a result, these questions will not appear in the review screen.You have a Fabric tenant that contains a semantic model named Model1.You discover that the following query performs slowly against Model1.You need to reduce the execution time of the query.Solution: You replace line 4 by using the following code:CALCULATE ( COUNTROWS ( 'Order Item' ) ) >= 0Does this meet the goal? 
Suggested Answer: B 🗳️ 

A. Yes

B. No

**Answer: B**

**Timestamp: April 24, 2024, 7:16 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/139526-exam-dp-600-topic-1-question-109-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 110 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 110
Topic #: 1

[All DP-600 Questions]

HOTSPOT -Case study -This is a case study. Case studies are not timed separately. You can use as much exam time as you would like to complete each case. However, there may be additional case studies and sections on this exam. You must manage your time to ensure that you are able to complete all questions included on this exam in the time provided.To answer the questions included in a case study, you will need to reference information that is provided in the case study. Case studies might contain exhibits and other resources that provide more information about the scenario that is described in the case study. Each question is independent of the other questions in this case study.At the end of this case study, a review screen will appear. This screen allows you to review your answers and to make changes before you move to the next section of the exam. After you begin a new section, you cannot return to this section.To start the case study -To display the first question in this case study, click the Next button. Use the buttons in the left pane to explore the content of the case study before you answer the questions. Clicking these buttons displays information such as business requirements, existing environment, and problem statements. If the case study has an All Information tab, note that the information displayed is identical to the information displayed on the subsequent tabs. When you are ready to answer a question, click the Question button to return to the question.Overview -Contoso, Ltd. is a US-based health supplements company. Contoso has two divisions named Sales and Research. The Sales division contains two departments named Online Sales and Retail Sales. The Research division assigns internally developed product lines to individual teams of researchers and analysts.Existing Environment -Identity Environment -Contoso has a Microsoft Entra tenant named contoso.com. The tenant contains two groups named ResearchReviewersGroup1 and ResearchReviewersGroup2.Data Environment -Contoso has the following data environment:• The Sales division uses a Microsoft Power BI Premium capacity.• The semantic model of the Online Sales department includes a fact table named Orders that uses Import made. In the system of origin, the OrderID value represents the sequence in which orders are created.• The Research department uses an on-premises, third-party data warehousing product.• Fabric is enabled for contoso.com.• An Azure Data Lake Storage Gen2 storage account named storage1 contains Research division data for a product line named Productline1. The data is in the delta format.• A Data Lake Storage Gen2 storage account named storage2 contains Research division data for a product line named Productline2. The data is in the CSV format.Requirements -Planned Changes -Contoso plans to make the following changes:• Enable support for Fabric in the Power BI Premium capacity used by the Sales division.• Make all the data for the Sales division and the Research division available in Fabric.• For the Research division, create two Fabric workspaces named Productline1ws and Productline2ws.• In Productline1ws, create a lakehouse named Lakehouse1.• In Lakehouse1, create a shortcut to storage1 named ResearchProduct.Data Analytics Requirements -Contoso identifies the following data analytics requirements:• All the workspaces for the Sales division and the Research division must support all Fabric experiences.• The Research division workspaces must use a dedicated, on-demand capacity that has per-minute billing.• The Research division workspaces must be grouped together logically to support OneLake data hub filtering based on the department name.• For the Research division workspaces, the members of ResearchReviewersGroup1 must be able to read lakehouse and warehouse data and shortcuts by using SQL endpoints.• For the Research division workspaces, the members of ResearchReviewersGroup2 must be able to read lakehouse data by using Lakehouse explorer.• All the semantic models and reports for the Research division must use version control that supports branching.Data Preparation Requirements -Contoso identifies the following data preparation requirements:• The Research division data for Productline1 must be retrieved from Lakehouse1 by using Fabric notebooks.• All the Research division data in the lakehouses must be presented as managed tables in Lakehouse explorer.Semantic Model Requirements -Contoso identifies the following requirements for implementing and managing semantic models:• The number of rows added to the Orders table during refreshes must be minimized.• The semantic models in the Research division workspaces must use Direct Lake mode.General Requirements -Contoso identifies the following high-level requirements that must be considered for all solutions:• Follow the principle of least privilege when applicable.• Minimize implementation and maintenance effort when possible.You need to migrate the Research division data for Productline2. The solution must meet the data preparation requirements.How should you complete the code? To answer, select the appropriate options in the answer area.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: Nov. 2, 2024, 1:49 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/150637-exam-dp-600-topic-1-question-110-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 111 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 111
Topic #: 1

[All DP-600 Questions]

Case study -This is a case study. Case studies are not timed separately. You can use as much exam time as you would like to complete each case. However, there may be additional case studies and sections on this exam. You must manage your time to ensure that you are able to complete all questions included on this exam in the time provided.To answer the questions included in a case study, you will need to reference information that is provided in the case study. Case studies might contain exhibits and other resources that provide more information about the scenario that is described in the case study. Each question is independent of the other questions in this case study.At the end of this case study, a review screen will appear. This screen allows you to review your answers and to make changes before you move to the next section of the exam. After you begin a new section, you cannot return to this section.To start the case study -To display the first question in this case study, click the Next button. Use the buttons in the left pane to explore the content of the case study before you answer the questions. Clicking these buttons displays information such as business requirements, existing environment, and problem statements. If the case study has an All Information tab, note that the information displayed is identical to the information displayed on the subsequent tabs. When you are ready to answer a question, click the Question button to return to the question.Overview -Contoso, Ltd. is a US-based health supplements company. Contoso has two divisions named Sales and Research. The Sales division contains two departments named Online Sales and Retail Sales. The Research division assigns internally developed product lines to individual teams of researchers and analysts.Existing Environment -Identity Environment -Contoso has a Microsoft Entra tenant named contoso.com. The tenant contains two groups named ResearchReviewersGroup1 and ResearchReviewersGroup2.Data Environment -Contoso has the following data environment:• The Sales division uses a Microsoft Power BI Premium capacity.• The semantic model of the Online Sales department includes a fact table named Orders that uses Import made. In the system of origin, the OrderID value represents the sequence in which orders are created.• The Research department uses an on-premises, third-party data warehousing product.• Fabric is enabled for contoso.com.• An Azure Data Lake Storage Gen2 storage account named storage1 contains Research division data for a product line named Productline1. The data is in the delta format.• A Data Lake Storage Gen2 storage account named storage2 contains Research division data for a product line named Productline2. The data is in the CSV format.Requirements -Planned Changes -Contoso plans to make the following changes:• Enable support for Fabric in the Power BI Premium capacity used by the Sales division.• Make all the data for the Sales division and the Research division available in Fabric.• For the Research division, create two Fabric workspaces named Productline1ws and Productline2ws.• In Productline1ws, create a lakehouse named Lakehouse1.• In Lakehouse1, create a shortcut to storage1 named ResearchProduct.Data Analytics Requirements -Contoso identifies the following data analytics requirements:• All the workspaces for the Sales division and the Research division must support all Fabric experiences.• The Research division workspaces must use a dedicated, on-demand capacity that has per-minute billing.• The Research division workspaces must be grouped together logically to support OneLake data hub filtering based on the department name.• For the Research division workspaces, the members of ResearchReviewersGroup1 must be able to read lakehouse and warehouse data and shortcuts by using SQL endpoints.• For the Research division workspaces, the members of ResearchReviewersGroup2 must be able to read lakehouse data by using Lakehouse explorer.• All the semantic models and reports for the Research division must use version control that supports branching.Data Preparation Requirements -Contoso identifies the following data preparation requirements:• The Research division data for Productline1 must be retrieved from Lakehouse1 by using Fabric notebooks.• All the Research division data in the lakehouses must be presented as managed tables in Lakehouse explorer.Semantic Model Requirements -Contoso identifies the following requirements for implementing and managing semantic models:• The number of rows added to the Orders table during refreshes must be minimized.• The semantic models in the Research division workspaces must use Direct Lake mode.General Requirements -Contoso identifies the following high-level requirements that must be considered for all solutions:• Follow the principle of least privilege when applicable.• Minimize implementation and maintenance effort when possible.Which syntax should you use in a notebook to access the Research division data for Productline1? 
Suggested Answer: B 🗳️ 

A. spark.read.format(“delta”).load(“Files/ResearchProduct”)

B. spark.sql(“SELECT * FROM Lakehouse1.ResearchProduct ”)

C. spark.sql(“SELECT * FROM Lakehouse1.Tables.ResearchProduct ”)

D. external_table(ResearchProduct)

**Answer: B**

**Timestamp: Nov. 2, 2024, 7:17 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/150649-exam-dp-600-topic-1-question-111-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 112 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 112
Topic #: 1

[All DP-600 Questions]

HOTSPOT -You have a Fabric workspace that uses the default Spark starter pool and runtime version 1.2.You plan to read a CSV file named Sales_raw.csv in a lakehouse, select columns, and save the data as a Delta table to the managed area of the lakehouse. Sales_raw.csv contains 12 columns.You have the following code.For each of the following statements, select Yes if the statement is true. Otherwise, select No.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: Oct. 8, 2024, 3:34 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/148872-exam-dp-600-topic-1-question-112-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 113 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 113
Topic #: 1

[All DP-600 Questions]

Note: This question is part of a series of questions that present the same scenario. Each question in the series contains a unique solution that might meet the stated goals. Some question sets might have more than one correct solution, while others might not have a correct solution.After you answer a question in this section, you will NOT be able to return to it. As a result, these questions will not appear in the review screen.You have a Fabric tenant that contains a new semantic model in OneLake.You use a Fabric notebook to read the data into a Spark DataFrame.You need to evaluate the data to calculate the min, max, mean, and standard deviation values for all the string and numeric columns.Solution: You use the following PySpark expression:df.describe().show()Does this meet the goal? 
Suggested Answer: A 🗳️ 

A. Yes

B. No

**Answer: A**

**Timestamp: Oct. 6, 2024, 9:38 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/148730-exam-dp-600-topic-1-question-113-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 114 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 114
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant.You are creating a Fabric Data Factory pipeline.You have a stored procedure that returns the number of active customers and their average sales for the current month.You need to add an activity that will execute the stored procedure in a warehouse. The returned values must be available to the downstream activities of the pipeline.Which type of activity should you add? 
Suggested Answer: D 🗳️ 

A. Switch

B. KQL

C. Append variable

D. Lookup

**Answer: D**

**Timestamp: Oct. 10, 2024, 9:10 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/148965-exam-dp-600-topic-1-question-114-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 115 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 115
Topic #: 1

[All DP-600 Questions]

HOTSPOT -You have a Fabric tenant that contains a semantic model named model1. The two largest columns in model1 are shown in the following table.You need to optimize model1. The solution must meet the following requirements:• Reduce the model size.• Increase refresh performance when using Import mode.• Ensure that the datetime value for each sales transaction is available in the model.What should you do on each column? To answer, select the appropriate options in the answer area.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: Oct. 6, 2024, 9:45 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/148731-exam-dp-600-topic-1-question-115-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 116 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 116
Topic #: 1

[All DP-600 Questions]

DRAG DROP -You have a Fabric tenant that contains a data warehouse named DW1. DW1 contains a table named DimCustomer. DimCustomer contains the fields shown in the following table.You need to identify duplicate email addresses in DimCustomer. The solution must return a maximum of 1,000 records.Which four T-SQL statements should you run in sequence? To answer, move the appropriate statements from the list of statements to the answer area and arrange them in the correct order. 
Suggested Answer: 

**Answer: **

**Timestamp: Oct. 6, 2024, 9:46 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/148732-exam-dp-600-topic-1-question-116-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 117 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 117
Topic #: 1

[All DP-600 Questions]

HOTSPOT -You have a Fabric tenant that contains a warehouse named WH1.You run the following T-SQL query against WH1.For each of the following statements, select Yes if the statement is true. Otherwise, select No.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: Oct. 6, 2024, 9:49 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/148734-exam-dp-600-topic-1-question-117-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 118 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 118
Topic #: 1

[All DP-600 Questions]

Note: This question is part of a series of questions that present the same scenario. Each question in the series contains a unique solution that might meet the stated goals. Some question sets might have more than one correct solution, while others might not have a correct solution.After you answer a question in this section, you will NOT be able to return to it. As a result, these questions will not appear in the review screen.You have a Fabric tenant that contains a semantic model named Model1.You discover that the following query performs slowly against Model1.You need to reduce the execution time of the query.Solution: You replace line 4 by using the following code:NOT ( CALCULATE ( COUNTROWS ( 'Order Item' ) ) < 0)Does this meet the goal? 
Suggested Answer: B 🗳️ 

A. Yes

B. No

**Answer: B**

**Timestamp: Oct. 6, 2024, 9:50 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/148735-exam-dp-600-topic-1-question-118-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 119 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 119
Topic #: 1

[All DP-600 Questions]

Case study -This is a case study. Case studies are not timed separately. You can use as much exam time as you would like to complete each case. However, there may be additional case studies and sections on this exam. You must manage your time to ensure that you are able to complete all questions included on this exam in the time provided.To answer the questions included in a case study, you will need to reference information that is provided in the case study. Case studies might contain exhibits and other resources that provide more information about the scenario that is described in the case study. Each question is independent of the other questions in this case study.At the end of this case study, a review screen will appear. This screen allows you to review your answers and to make changes before you move to the next section of the exam. After you begin a new section, you cannot return to this section.To start the case study -To display the first question in this case study, click the Next button. Use the buttons in the left pane to explore the content of the case study before you answer the questions. Clicking these buttons displays information such as business requirements, existing environment, and problem statements. If the case study has an All Information tab, note that the information displayed is identical to the information displayed on the subsequent tabs. When you are ready to answer a question, click the Question button to return to the question.Overview -Contoso, Ltd. is a US-based health supplements company. Contoso has two divisions named Sales and Research. The Sales division contains two departments named Online Sales and Retail Sales. The Research division assigns internally developed product lines to individual teams of researchers and analysts.Existing Environment -Identity Environment -Contoso has a Microsoft Entra tenant named contoso.com. The tenant contains two groups named ResearchReviewersGroup1 and ResearchReviewersGroup2.Data Environment -Contoso has the following data environment:• The Sales division uses a Microsoft Power BI Premium capacity.• The semantic model of the Online Sales department includes a fact table named Orders that uses Import made. In the system of origin, the OrderID value represents the sequence in which orders are created.• The Research department uses an on-premises, third-party data warehousing product.• Fabric is enabled for contoso.com.• An Azure Data Lake Storage Gen2 storage account named storage1 contains Research division data for a product line named Productline1. The data is in the delta format.• A Data Lake Storage Gen2 storage account named storage2 contains Research division data for a product line named Productline2. The data is in the CSV format.Requirements -Planned Changes -Contoso plans to make the following changes:• Enable support for Fabric in the Power BI Premium capacity used by the Sales division.• Make all the data for the Sales division and the Research division available in Fabric.• For the Research division, create two Fabric workspaces named Productline1ws and Productline2ws.• In Productline1ws, create a lakehouse named Lakehouse1.• In Lakehouse1, create a shortcut to storage1 named ResearchProduct.Data Analytics Requirements -Contoso identifies the following data analytics requirements:• All the workspaces for the Sales division and the Research division must support all Fabric experiences.• The Research division workspaces must use a dedicated, on-demand capacity that has per-minute billing.• The Research division workspaces must be grouped together logically to support OneLake data hub filtering based on the department name.• For the Research division workspaces, the members of ResearchReviewersGroup1 must be able to read lakehouse and warehouse data and shortcuts by using SQL endpoints.• For the Research division workspaces, the members of ResearchReviewersGroup2 must be able to read lakehouse data by using Lakehouse explorer.• All the semantic models and reports for the Research division must use version control that supports branching.Data Preparation Requirements -Contoso identifies the following data preparation requirements:• The Research division data for Productline1 must be retrieved from Lakehouse1 by using Fabric notebooks.• All the Research division data in the lakehouses must be presented as managed tables in Lakehouse explorer.Semantic Model Requirements -Contoso identifies the following requirements for implementing and managing semantic models:• The number of rows added to the Orders table during refreshes must be minimized.• The semantic models in the Research division workspaces must use Direct Lake mode.General Requirements -Contoso identifies the following high-level requirements that must be considered for all solutions:• Follow the principle of least privilege when applicable.• Minimize implementation and maintenance effort when possible.Which syntax should you use in a notebook to access the Research division data for Productline1? 
Suggested Answer: A 🗳️ 

A. spark.read.format(“delta”).load(“Tables/ResearchProduct”)

B. spark.read.format(“delta”).load(“Files/ResearchProduct”)

C. external_table(‘Tables/ResearchProduct)

D. external_table(ResearchProduct)

**Answer: A**

**Timestamp: Oct. 5, 2024, 7:35 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/148668-exam-dp-600-topic-1-question-119-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 120 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 120
Topic #: 1

[All DP-600 Questions]

You have a Microsoft Power BI Premium Per User (PPU) workspace that contains a semantic model.You have an Azure App Service app named App1 that modifies row-level security (RLS) for the model by using the XMLA endpoint.App1 requires users to sign in by using their Microsoft Entra credentials to access the XMLA endpoint.You need to configure App1 to use a service account to access the model.What should you do first? 
Suggested Answer: D 🗳️ 

A. Add a managed identity to the workspace.

B. Modify the XMLA Endpoint setting.

C. Upgrade the workspace to Premium capacity.

D. Add a managed identity to App1.

**Answer: D**

**Timestamp: Nov. 28, 2024, 5:48 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/152301-exam-dp-600-topic-1-question-120-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 121 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 121
Topic #: 1

[All DP-600 Questions]

HOTSPOT -You have a Fabric tenant that contains a warehouse named WH1.You have source data in a CSV file that has the following fields:• SalesTransactionID• SaleDate• CustomerCode• CustomerName• CustomerAddress• ProductCode• ProductName• Quantity• UnitPriceYou plan to implement a star schema for the tables in WH1. The dimension tables in WH1 will implement Type 2 slowly changing dimension (SCD) logic.You need to design the tables that will be used for sales transaction analysis and load the source data.Which type of target table should you specify for the CustomerName, CustomerCode, and SaleDate fields? To answer, select the appropriate options in the answer area.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: Jan. 25, 2025, 5:54 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/155387-exam-dp-600-topic-1-question-121-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 122 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 122
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant.You are creating a Fabric Data Factory pipeline.You have a stored procedure that returns the number of active customers and their average sales for the current month.You need to add an activity that will execute the stored procedure in a warehouse. The returned values must be available to the downstream activities of the pipeline.Which type of activity should you add? 
Suggested Answer: C 🗳️ 

A. Get metadata

B. Copy data

C. Lookup

D. Append variable

**Answer: C**

**Timestamp: Nov. 30, 2024, 4:15 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/152406-exam-dp-600-topic-1-question-122-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 123 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 123
Topic #: 1

[All DP-600 Questions]

HOTSPOT -You have a Fabric tenant that contains a warehouse named Warehouse1. Warehouse1 contains a fact table named FactSales that has one billion rows.You run the following T-SQL statement.CREATE TABLE test.FactSales AS CLONE OF dbo.FactSales;For each of the following statements, select Yes if the statement is true. Otherwise, select No.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: Nov. 18, 2024, 11:04 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/151543-exam-dp-600-topic-1-question-123-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 124 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 124
Topic #: 1

[All DP-600 Questions]

You have an Amazon Web Services (AWS) subscription that contains an Amazon Simple Storage Service (Amazon S3) bucket named bucket1.You have a Fabric tenant that contains a lakehouse named LH1.In LH1, you plan to create a OneLake shortcut to bucket1.You need to configure authentication for the connection.Which two values should you provide? Each correct answer presents part of the solution.NOTE: Each correct selection is worth one point. 
Suggested Answer: BD 🗳️ 

A. the shared access signature (SAS) token

B. the secret access key

C. the access ID

D. the access key ID

E. the certificate thumbprint

**Answer: B**

**Timestamp: Nov. 6, 2024, 7:36 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/150838-exam-dp-600-topic-1-question-124-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 125 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 125
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant that contains a data warehouse.You need to load rows into a large Type 2 slowly changing dimension (SCD). The solution must minimize resource usage.Which T-SQL statement should you use? 
Suggested Answer: A 🗳️ 

A. UPDATE AND INSERT

B. MERGE

C. TRUNCATE TABLE and INSERT

D. CREATE TABLE AS SELECT

**Answer: A**

**Timestamp: Nov. 30, 2024, 4:26 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/152407-exam-dp-600-topic-1-question-125-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 126 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 126
Topic #: 1

[All DP-600 Questions]

Case study -This is a case study. Case studies are not timed separately. You can use as much exam time as you would like to complete each case. However, there may be additional case studies and sections on this exam. You must manage your time to ensure that you are able to complete all questions included on this exam in the time provided.To answer the questions included in a case study, you will need to reference information that is provided in the case study. Case studies might contain exhibits and other resources that provide more information about the scenario that is described in the case study. Each question is independent of the other questions in this case study.At the end of this case study, a review screen will appear. This screen allows you to review your answers and to make changes before you move to the next section of the exam. After you begin a new section, you cannot return to this section.To start the case study -To display the first question in this case study, click the Next button. Use the buttons in the left pane to explore the content of the case study before you answer the questions. Clicking these buttons displays information such as business requirements, existing environment, and problem statements. If the case study has an All Information tab, note that the information displayed is identical to the information displayed on the subsequent tabs. When you are ready to answer a question, click the Question button to return to the question.Overview -Contoso, Ltd. is a US-based health supplements company. Contoso has two divisions named Sales and Research. The Sales division contains two departments named Online Sales and Retail Sales. The Research division assigns internally developed product lines to individual teams of researchers and analysts.Existing Environment -Identity Environment -Contoso has a Microsoft Entra tenant named contoso.com. The tenant contains two groups named ResearchReviewersGroup1 and ResearchReviewersGroup2.Data Environment -Contoso has the following data environment:• The Sales division uses a Microsoft Power BI Premium capacity.• The semantic model of the Online Sales department includes a fact table named Orders that uses Import made. In the system of origin, the OrderID value represents the sequence in which orders are created.• The Research department uses an on-premises, third-party data warehousing product.• Fabric is enabled for contoso.com.• An Azure Data Lake Storage Gen2 storage account named storage1 contains Research division data for a product line named Productline1. The data is in the delta format.• A Data Lake Storage Gen2 storage account named storage2 contains Research division data for a product line named Productline2. The data is in the CSV format.Requirements -Planned Changes -Contoso plans to make the following changes:• Enable support for Fabric in the Power BI Premium capacity used by the Sales division.• Make all the data for the Sales division and the Research division available in Fabric.• For the Research division, create two Fabric workspaces named Productline1ws and Productline2ws.• In Productline1ws, create a lakehouse named Lakehouse1.• In Lakehouse1, create a shortcut to storage1 named ResearchProduct.Data Analytics Requirements -Contoso identifies the following data analytics requirements:• All the workspaces for the Sales division and the Research division must support all Fabric experiences.• The Research division workspaces must use a dedicated, on-demand capacity that has per-minute billing.• The Research division workspaces must be grouped together logically to support OneLake data hub filtering based on the department name.• For the Research division workspaces, the members of ResearchReviewersGroup1 must be able to read lakehouse and warehouse data and shortcuts by using SQL endpoints.• For the Research division workspaces, the members of ResearchReviewersGroup2 must be able to read lakehouse data by using Lakehouse explorer.• All the semantic models and reports for the Research division must use version control that supports branching.Data Preparation Requirements -Contoso identifies the following data preparation requirements:• The Research division data for Productline2 must be retrieved from Lakehouse1 by using Fabric notebooks.• All the Research division data in the lakehouses must be presented as managed tables in Lakehouse explorer.Semantic Model Requirements -Contoso identifies the following requirements for implementing and managing semantic models:• The number of rows added to the Orders table during refreshes must be minimized.• The semantic models in the Research division workspaces must use Direct Lake mode.General Requirements -Contoso identifies the following high-level requirements that must be considered for all solutions:• Follow the principle of least privilege when applicable.• Minimize implementation and maintenance effort when possible.Which syntax should you use in a notebook to access the Research division data for Productline1? 
Suggested Answer: D 🗳️ 

A. spark.sql("SELECT * FROM Lakehouse1.Tables.ResearchProduct")

B. spark.read.format("delta").load("Tables/productline1/ResearchProduct")

C. external_table(ResearchProduct)

D. spark.read.format("delta").load("Tables/ResearchProduct")

**Answer: D**

**Timestamp: Dec. 1, 2024, 5:19 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/152436-exam-dp-600-topic-1-question-126-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 127 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 127
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant that contains a lakehouse named LH1.You create new tables in LH1.You need to ensure that the tables are added automatically to the default semantic model.What should you do? 
Suggested Answer: B 🗳️ 

A. Disable Query Caching for the default semantic model.

B. From the settings pane of LH1, enable Sync the default Power BI semantic model.

C. Enable Refresh for the default semantic model.

D. From the Endorsement and discovery settings of LH1, select Make discoverable.

**Answer: B**

**Timestamp: Nov. 30, 2024, 4:30 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/152408-exam-dp-600-topic-1-question-127-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 128 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 128
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant.You are creating a Fabric Data Factory pipeline.You have a stored procedure that returns the number of active customers and their average sales for the current month.You need to add an activity that will execute the stored procedure in a warehouse. The returned values must be available to the downstream activities of the pipeline.Which type of activity should you add? 
Suggested Answer: B 🗳️ 

A. Append variable

B. Lookup

C. Copy data

D. KQL

**Answer: B**

**Timestamp: Nov. 30, 2024, 4:31 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/152410-exam-dp-600-topic-1-question-128-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 129 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 129
Topic #: 1

[All DP-600 Questions]

Note: This section contains one or more sets of questions with the same scenario and problem. Each question presents a unique solution to the problem. You must determine whether the solution meets the stated goals. More than one solution in the set might solve the problem. It is also possible that none of the solutions in the set solve the problem.After you answer a question in this section, you will NOT be able to return. As a result, these questions do not appear on the Review Screen.Your network contains an on-premises Active Directory Domain Services (AD DS) domain named contoso.com that syncs with a Microsoft Entra tenant by using Microsoft Entra Connect.You have a Fabric tenant that contains a semantic model.You enable dynamic row-level security (RLS) for the model and deploy the model to the Fabric service.You query a measure that includes the USERNAME() function, and the query returns a blank result.You need to ensure that the measure returns the user principal name (UPN) of a user.Solution: You update the measure to use the USEROBJECTID() function.Does this meet the goal? 
Suggested Answer: B 🗳️ 

A. Yes

B. No

**Answer: B**

**Timestamp: Nov. 28, 2024, 6 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/152306-exam-dp-600-topic-1-question-129-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 130 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 130
Topic #: 1

[All DP-600 Questions]

Note: This section contains one or more sets of questions with the same scenario and problem. Each question presents a unique solution to the problem. You must determine whether the solution meets the stated goals. More than one solution in the set might solve the problem. It is also possible that none of the solutions in the set solve the problem.After you answer a question in this section, you will NOT be able to return. As a result, these questions do not appear on the Review Screen.Your network contains an on-premises Active Directory Domain Services (AD DS) domain named contoso.com that syncs with a Microsoft Entra tenant by using Microsoft Entra Connect.You have a Fabric tenant that contains a semantic model.You enable dynamic row-level security (RLS) for the model and deploy the model to the Fabric service.You query a measure that includes the USERNAME() function, and the query returns a blank result.You need to ensure that the measure returns the user principal name (UPN) of a user.Solution: You update the measure to use the USERPRINCIPALNAME() function.Does this meet the goal? 
Suggested Answer: A 🗳️ 

A. Yes

B. No

**Answer: A**

**Timestamp: Nov. 28, 2024, 6 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/152307-exam-dp-600-topic-1-question-130-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 131 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 39
Topic #: 1

[All DP-600 Questions]

Note: This section contains one or more sets of questions with the same scenario and problem. Each question presents a unique solution to the problem. You must determine whether the solution meets the stated goals. More than one solution in the set might solve the problem. It is also possible that none of the solutions in the set solve the problem.After you answer a question in this section, you will NOT be able to return. As a result, these questions do not appear on the Review Screen.Your network contains an on-premises Active Directory Domain Services (AD DS) domain named contoso.com that syncs with a Microsoft Entra tenant by using Microsoft Entra Connect.You have a Fabric tenant that contains a semantic model.You enable dynamic row-level security (RLS) for the model and deploy the model to the Fabric service.You query a measure that includes the USERNAME() function, and the query returns a blank result.You need to ensure that the measure returns the user principal name (UPN) of a user.Solution: You add user objects to the list of synced objects in Microsoft Entra Connect.Does this meet the goal? 
Suggested Answer: B 🗳️ 

A. Yes

B. No

**Answer: B**

**Timestamp: Nov. 16, 2024, 8:19 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/151399-exam-dp-600-topic-1-question-131-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 131 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 131
Topic #: 1

[All DP-600 Questions]

HOTSPOT -You have a Fabric tenant that contains a PySpark notebook named Notebook1.You define sas_token as a variable in the first cell of Notebook1 and store a shared access signature (SAS) token in the variable.In the second cell, you run the following code.For each of the following statements, select Yes if the statement is true. Otherwise, select No.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: Feb. 12, 2025, 1:38 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/156384-exam-dp-600-topic-1-question-131-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 132 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 132
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant that contains a warehouse named DW1 and a lakehouse named LH1. DW1 contains a table named Sales.Product. LH1 contains a table named Sales.Orders.You plan to schedule an automated process that will create a new point-in-time (PIT) table named Sales.ProductOrder in DW1. Sales.ProductOrder will be built by using the results of a query that will join Sales.Product and Sales.Orders.You need to ensure that the types of columns in Sales.ProductOrder match the column types in the source tables. The solution must minimize the number of operations required to create the new table.Which operation should you use? 
Suggested Answer: B 🗳️ 

A. INSERT INTO

B. CREATE TABLE AS SELECT (CTAS)

C. CREATE TABLE AS CLONE OF

D. CREATE MATERIALIZED VIEW AS SELECT

**Answer: B**

**Timestamp: Dec. 28, 2024, 8:21 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/153561-exam-dp-600-topic-1-question-132-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 133 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 133
Topic #: 1

[All DP-600 Questions]

HOTSPOT -You have a Fabric tenant that contains the semantic model shown in the following exhibit.Use the drop-down menus to select the answer choice that completes each statement based on the information presented in the graphic.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: Jan. 15, 2025, 10:23 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/154617-exam-dp-600-topic-1-question-133-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 134 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 134
Topic #: 1

[All DP-600 Questions]

Note: This section contains one or more sets of questions with the same scenario and problem. Each question presents a unique solution to the problem. You must determine whether the solution meets the stated goals. More than one solution in the set might solve the problem. It is also possible that none of the solutions in the set solve the problem.After you answer a question in this section, you will NOT be able to return. As a result, these questions do not appear on the Review Screen.Your network contains an on-premises Active Directory Domain Services (AD DS) domain named contoso.com that syncs with a Microsoft Entra tenant by using Microsoft Entra Connect.You have a Fabric tenant that contains a semantic model.You enable dynamic row-level security (RLS) for the model and deploy the model to the Fabric service.You query a measure that includes the USERNAME() function, and the query returns a blank result.You need to ensure that the measure returns the user principal name (UPN) of a user.Solution: You create a role in the model.Does this meet the goal? 
Suggested Answer: B 🗳️ 

A. Yes

B. No

**Answer: B**

**Timestamp: Dec. 31, 2024, 12:13 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/153713-exam-dp-600-topic-1-question-134-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 135 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 135
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant that contains two workspaces named Workspace1 and Workspace2 and a user named User1.You need to ensure that User1 can perform the following tasks:• Create a new domain.• Create two subdomains named subdomain1 and subdomain2.• Assign Workspace1 to subdomain1.• Assign Workspace2 to subdomain2.The solution must follow the principle of least privilege.Which role should you assign to User1? 
Suggested Answer: C 🗳️ 

A. domain admin

B. domain contributor

C. Fabric admin

D. workspace Admin

**Answer: C**

**Timestamp: Dec. 30, 2024, 2:39 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/153640-exam-dp-600-topic-1-question-135-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 136 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 136
Topic #: 1

[All DP-600 Questions]

HOTSPOT -You have a Fabric tenant that contains three users named User1, User2, and User3. The tenant contains a security group named Group1. User1 and User3 are members of Group1.The tenant contains the workspaces shown in the following table.The tenant contains the domains shown in the following table.User1 creates a new workspace named Workspace3.You assign Domain1 as the default domain of Group1.For each of the following statements, select Yes if the statement is true. Otherwise, select No.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: Jan. 27, 2025, 10:11 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/155502-exam-dp-600-topic-1-question-136-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 137 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 137
Topic #: 1

[All DP-600 Questions]

You have a Fabric warehouse named Warehouse1 that contains a table named Table1. Table1 contains customer data.You need to implement row-level security (RLS) for Table1. The solution must ensure that users can see only their respective data.Which two objects should you create? Each correct answer presents part of the solution.NOTE: Each correct selection is worth one point. 
Suggested Answer: DE 🗳️ 

A. DATABASE ROLE

B. STORED PROCEDURE

C. CONSTRAINT

D. FUNCTION

E. SECURITY POLICY

**Answer: D**

**Timestamp: Dec. 28, 2024, 9:41 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/153562-exam-dp-600-topic-1-question-137-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 138 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 138
Topic #: 1

[All DP-600 Questions]

You have a Fabric workspace named Workspace1 that contains a lakehouse named Lakehouse1. Lakehouse1 contains a table named Table1. Table1 contains the following data.You need to perform the following actions:• Load the data from Table1 into a star schema.• Create a product dimension table named DimProduct and a fact table named FactSales.Which three columns should you include in DimProduct? 
Suggested Answer: A 🗳️ 

A. ProductColor, ProductID, and ProductName.

B. ProductName, SalesAmount, and TransactionlD.

C. Date, ProductID, and TransactionlD.

D. ProductID, ProductName, and SalesAmount

**Answer: A**

**Timestamp: Dec. 29, 2024, 10:09 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/153597-exam-dp-600-topic-1-question-138-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 139 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 139
Topic #: 1

[All DP-600 Questions]

DRAG DROP -You have a Fabric workspace that contains a Dataflow Gen2 query. The query returns the following data.You need to filter the results to ensure that only the latest version of each customer’s record is retained. The solution must ensure that no new columns are loaded to the semantic model.Which four actions should you perform in sequence in Power Query Editor? To answer, move the appropriate actions from the list of actions to the answer area and arrange them in the correct order. 
Suggested Answer: 

**Answer: **

**Timestamp: Feb. 11, 2025, 11:39 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/156350-exam-dp-600-topic-1-question-139-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 140 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 140
Topic #: 1

[All DP-600 Questions]

HOTSPOT -You have a Microsoft Power Bl project that contains a file named definition.pbir. definition.pbir contains the following JSON.For each of the following statements, select Yes if the statement is true. Otherwise, select No.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: Jan. 15, 2025, 3:59 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/154582-exam-dp-600-topic-1-question-140-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 141 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 141
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant that contains a workspace named Workspace1.You plan to deploy a semantic model named Model1 by using the XMLA endpoint.You need to optimize the deployment of Model1. The solution must minimize how long it takes to deploy Model1.What should you do in Workspace1? 
Suggested Answer: D 🗳️ 

A. Select Small semantic model storage format.

B. Select Users can edit data models in the Power BI service.

C. Set Enable Cache for Shortcuts to On.

D. Select Large semantic model storage format.

**Answer: D**

**Timestamp: Jan. 15, 2025, 4:17 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/154585-exam-dp-600-topic-1-question-141-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 142 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 142
Topic #: 1

[All DP-600 Questions]

You have a Microsoft Power BI project that contains a semantic model.You plan to use Azure DevOps for version control.You need to modify the .gitignore file to prevent the data values from the data sources from being pushed to the repository.Which file should you reference? 
Suggested Answer: B 🗳️ 

A. unappliedChanges.json

B. cache.abf

C. localSettings.json

D. model.bim

**Answer: B**

**Timestamp: Jan. 5, 2025, 8:11 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/153920-exam-dp-600-topic-1-question-142-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 143 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 143
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant that contains a workspace named Workspace1. Workspace1 uses Pro license mode and contains a semantic model named Model1.You need to ensure that Model1 supports XMLA connections.Which setting should modify? 
Suggested Answer: D 🗳️ 

A. Users can edit data models in the Power BI service

B. Enforce strict access control for all data connection types

C. Enable Cache for Shortcuts

D. License mode

**Answer: D**

**Timestamp: Jan. 22, 2025, 9:03 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/155217-exam-dp-600-topic-1-question-143-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 144 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 144
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant that contains a complex semantic model. The model is based on a star schema and contains many tables, including a fact table named Sales.You need to visualize a diagram of the model. The diagram must contain only the Sales table and related tables.What should you use from Microsoft Power BI Desktop? 
Suggested Answer: C 🗳️ 

A. data categories

B. Data view

C. Model view

D. DAX query view

**Answer: C**

**Timestamp: Jan. 4, 2025, 9:25 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/153871-exam-dp-600-topic-1-question-144-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 145 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 145
Topic #: 1

[All DP-600 Questions]

HOTSPOT -You have a Fabric tenant that contains a lakehouse named LH1.You need to deploy a new semantic model. The solution must meet the following requirements:• Support complex calculated columns that include aggregate functions, calculated tables, and Multidimensional Expressions (MDX) user hierarchies.• Minimize page rendering times.How should you configure the model? To answer, select the appropriate options in the answer area.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: Jan. 25, 2025, 2:34 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/155374-exam-dp-600-topic-1-question-145-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 146 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 146
Topic #: 1

[All DP-600 Questions]

HOTSPOT -You have the following KQL query.For each of the following statements, select Yes if the statement is true. Otherwise, select No.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: Jan. 15, 2025, 4:30 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/154586-exam-dp-600-topic-1-question-146-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 147 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 147
Topic #: 1

[All DP-600 Questions]

You have a Fabric warehouse that contains a table named SalesOrderDetail, SalesOrderDetail contains three columns named OrderQty, ProductID and SalesOrderlD. SalesOrderDetail contains one row per combination of SalesOrderlD and ProductID.You need to calculate the proportion of the total quantity of each sales order represented by each product within the sales order.Which T-SQL statement should you run? 
Suggested Answer: D 🗳️ 

A.

B.

C.

D.

**Answer: D**

**Timestamp: Jan. 12, 2025, 2:40 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/154435-exam-dp-600-topic-1-question-147-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 148 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 148
Topic #: 1

[All DP-600 Questions]

Case study -This is a case study. Case studies are not timed separately. You can use as much exam time as you would like to complete each case. However, there may be additional case studies and sections on this exam. You must manage your time to ensure that you are able to complete all questions included on this exam in the time provided.To answer the questions included in a case study, you will need to reference information that is provided in the case study. Case studies might contain exhibits and other resources that provide more information about the scenario that is described in the case study. Each question is independent of the other questions in this case study.At the end of this case study, a review screen will appear. This screen allows you to review your answers and to make changes before you move to the next section of the exam. After you begin a new section, you cannot return to this section.To start the case study -To display the first question in this case study, click the Next button. Use the buttons in the left pane to explore the content of the case study before you answer the questions. Clicking these buttons displays information such as business requirements, existing environment, and problem statements. If the case study has an All Information tab, note that the information displayed is identical to the information displayed on the subsequent tabs. When you are ready to answer a question, click the Question button to return to the question.Overview -Contoso, Ltd. is a US-based health supplements company. Contoso has two divisions named Sales and Research. The Sales division contains two departments named Online Sales and Retail Sales. The Research division assigns internally developed product lines to individual teams of researchers and analysts.Existing Environment -Identity Environment -Contoso has a Microsoft Entra tenant named contoso.com. The tenant contains two groups named ResearchReviewersGroup1 and ResearchReviewersGroup2.Data Environment -Contoso has the following data environment:• The Sales division uses a Microsoft Power BI Premium capacity.• The semantic model of the Online Sales department includes a fact table named Orders that uses Import made. In the system of origin, the OrderID value represents the sequence in which orders are created.• The Research department uses an on-premises, third-party data warehousing product.• Fabric is enabled for contoso.com.• An Azure Data Lake Storage Gen2 storage account named storage1 contains Research division data for a product line named Productline1. The data is in the delta format.• A Data Lake Storage Gen2 storage account named storage2 contains Research division data for a product line named Productline2. The data is in the CSV format.Requirements -Planned Changes -Contoso plans to make the following changes:• Enable support for Fabric in the Power BI Premium capacity used by the Sales division.• Make all the data for the Sales division and the Research division available in Fabric.• For the Research division, create two Fabric workspaces named Productline1ws and Productline2ws.• In Productline1ws, create a lakehouse named Lakehouse1.• In Lakehouse1, create a shortcut to storage1 named ResearchProduct.Data Analytics Requirements -Contoso identifies the following data analytics requirements:• All the workspaces for the Sales division and the Research division must support all Fabric experiences.• The Research division workspaces must use a dedicated, on-demand capacity that has per-minute billing.• The Research division workspaces must be grouped together logically to support OneLake data hub filtering based on the department name.• For the Research division workspaces, the members of ResearchReviewersGroup1 must be able to read lakehouse and warehouse data and shortcuts by using SQL endpoints.• For the Research division workspaces, the members of ResearchReviewersGroup2 must be able to read lakehouse data by using Lakehouse explorer.• All the semantic models and reports for the Research division must use version control that supports branching.Data Preparation Requirements -Contoso identifies the following data preparation requirements:• The Research division data for Productline1 must be retrieved from Lakehouse1 by using Fabric notebooks.• All the Research division data in the lakehouses must be presented as managed tables in Lakehouse explorer.Semantic Model Requirements -Contoso identifies the following requirements for implementing and managing semantic models:• The number of rows added to the Orders table during refreshes must be minimized.• The semantic models in the Research division workspaces must use Direct Lake mode.General Requirements -Contoso identifies the following high-level requirements that must be considered for all solutions:• Follow the principle of least privilege when applicable.• Minimize implementation and maintenance effort when possible.Which syntax should you use in a notebook to access the Research division data for Productline1? 
Suggested Answer: A 🗳️ 

A. spark.read.format(“delta”).load(“Tables/ResearchProduct”)

B. spark.read.format(“delta”).load(“Files/ResearchProduct”)

C. spark.sql(“SELECT * FROM Lakehouse1.productline1.ResearchProduct”)

D. spark.read.format(“delta”).load(“Tables/productline1/ResearchProduct”)

**Answer: A**

**Timestamp: Feb. 3, 2025, 3:46 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/155865-exam-dp-600-topic-1-question-148-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 149 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 149
Topic #: 1

[All DP-600 Questions]

HOTSPOT -You have a Fabric lakehouse named Lakehouse1 that contains the following data.You need build a T-SQL statement that will return the total sales amount by OrderDate only for the days that are holidays in Australia. The total sales amount must sum the quantity multiplied by the price on each row in the dbo.sales table.How should you complete the statement? To answer, select the appropriate options in the answer area.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: Jan. 28, 2025, 1:10 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/155506-exam-dp-600-topic-1-question-149-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 150 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 150
Topic #: 1

[All DP-600 Questions]

HOTSPOT -You have a Fabric tenant that contains a workspace named Workspace1. Workspace1 contains a warehouse named DW1. DW1 contains two tables named Employees and Sales. All users have read access to Dw1.You need to implement access controls to meet the following requirements:• For the Sales table, ensure that the users can see only the sales data from their respective region.• For the Employees table, restrict access to all Personally Identifiable Information (PII).• Maintain access to unrestricted data for all the users.What should you use for each table? To answer, select the appropriate options in the answer area.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: Jan. 28, 2025, 1:14 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/155508-exam-dp-600-topic-1-question-150-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 151 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 151
Topic #: 1

[All DP-600 Questions]

You need to create a Microsoft Power BI file that will be used to create multiple reports. The solution must meet the following requirements:• The file must include predefined data source connections.• The file must include the report structure and formatting.• The file must NOT contain any data.Which file format should you use? 
Suggested Answer: A 🗳️ 

A. PBIT

B. PBIDS

C. PBIX

D. PBIP

**Answer: A**

**Timestamp: Jan. 21, 2025, 9:39 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/155065-exam-dp-600-topic-1-question-151-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 152 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 152
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant that contains a workspace named Workspace1. Workspace1 contains a single semantic model that has two Microsoft Power BI reports.You have a Microsoft 365 subscription that contains a data loss prevention (DLP) policy named DLP1.You need to apply DLP1 to the items in Workspace1.What should you do? 
Suggested Answer: C 🗳️ 

A. Create a workspace identity.

B. Apply a certified endorsement to the semantic model.

C. Apply sensitivity labels to the semantic model and reports.

D. Apply a master data endorsement to the semantic model.

**Answer: C**

**Timestamp: Jan. 28, 2025, 1:31 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/155511-exam-dp-600-topic-1-question-152-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 153 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 153
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant that contains a workspace named Workspace1 and a user named User1. User1 is assigned the Contributor role for Workspace1.You plan to configure Workspace1 to use an Azure DevOps repository for version control.You need to ensure that User1 can commit items to the repository.Which two settings should you enable for User1? Each correct answer presents part of the solution.NOTE: Each correct selection is worth one point. 
Suggested Answer: CD 🗳️ 

A. Users can sync workspace items with GitHub repositories

B. Users can create and use Data workflows

C. Users can create Fabric items

D. Users can synchronize workspace items with their Git repositories

**Answer: C**

**Timestamp: Jan. 22, 2025, 9:34 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/155219-exam-dp-600-topic-1-question-153-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 154 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 154
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant that contains a workspace named Workspace1. Workspace1 contains a data pipeline named Pipeline1 and a lakehouse named Lakehouse1.You perform the following actions:• Create a workspace named Workspace2.• Create a deployment pipeline named DeployPipeline1 that will deploy items from Workspace1 to Workspace2.• Add a folder named Folder1 to Workspace1.• Move Lakehouse1 to Folder1.• Run DeployPipeline1.Which structure will Workspace2 have when DeployPipeline1 is complete? 
Suggested Answer: C 🗳️ 

A. \Folder1\Pipeline1\Folder1\Lakehouse1

B. \Pipeline1\Lakehouse1

C. \Pipeline1\Folder1\Lakehouse1

D. \Folder1\Lakehouse1

**Answer: C**

**Timestamp: Jan. 21, 2025, 9:52 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/155067-exam-dp-600-topic-1-question-154-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 155 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 155
Topic #: 1

[All DP-600 Questions]

Your company has a finance department.You have a Fabric tenant, an Azure Storage account named storage1, and a Microsoft Entra group named Group1. Group1 contains the users in the finance department.You need to create a new workspace named Workspace1 in the tenant. The solution must meet the following requirements:• Ensure that the finance department users can create and edit items in Workspace1.• Ensure that Workspace1 can securely access storage1 to read and write data.• Ensure that you are the only admin of Workspace1.• Minimize administrative effort.You create Workspace1.Which two actions should you perform next? Each correct answer presents part of the solution.NOTE: Each correct selection is worth one point. 
Suggested Answer: AB 🗳️ 

A. Assign the Contributor role to Group1.

B. Create a workspace identity.

C. Assign the Admin role to yourself.

D. Assign the Contributor role to each finance department user.

**Answer: A**

**Timestamp: Feb. 16, 2025, 10:40 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/156596-exam-dp-600-topic-1-question-155-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 156 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 156
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant that contains the workspaces shown in the following table.You have a deployment pipeline named Pipeline1 that deploys items from Workspace_DEV to Workspace_TEST. In Pipeline1, all items that have matching names are paired.You deploy the contents of Workspace_DEV to Workspace_TEST by using Pipeline1.What will the contents of Workspace_TEST be once the deployment is complete? 
Suggested Answer: A 🗳️ 

A. Lakehouse1 -Lakehouse2 -Notebook1 -Notebook2 -Pipeline1 -SemanticModel1

B. Lakehouse1 -Notebook1 -Pipeline1 -SemanticModel1

C. Lakehouse2 -Notebook2 -SemanticModel1

D. Lakehouse2 -Notebook2 -Pipeline1 -SemanticModel1

**Answer: A**

**Timestamp: Jan. 28, 2025, 1:49 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/155514-exam-dp-600-topic-1-question-156-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 157 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 157
Topic #: 1

[All DP-600 Questions]

HOTSPOT -You have a Fabric tenant that contains a workspace named Workspace_DEV. Workspace_DEV contains the semantic models shown in the following table.Workspace_DEV contains the dataflows shown in the following table.You create a new workspace named Workspace_TEST.You create a deployment pipeline named Pipeline1 to move items from Workspace_DEV to Workspace_TEST.You run Pipeline1.For each of the following statements, select Yes if the statement is true. Otherwise, select No.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: Jan. 21, 2025, 5:40 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/155056-exam-dp-600-topic-1-question-157-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 158 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 158
Topic #: 1

[All DP-600 Questions]

HOTSPOT -You have a Fabric warehouse that contains two tables named DimDate and Trips.DimDate contains the following fields.Trips contains the following fields.You need to compare the average miles per trip for statutory holidays versus non-statutory holidays.How should you complete the T-SQL statement? To answer, select the appropriate options in the answer area.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: March 8, 2025, 3:09 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/157742-exam-dp-600-topic-1-question-158-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 159 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 159
Topic #: 1

[All DP-600 Questions]

HOTSPOT -You have a Fabric tenant that contains a workspace named Workspace1. Workspace1 contains a lakehouse named LH1 and a warehouse named DW1. LH1 contains a table named signindata that is in the dbo schema.You need to create a stored procedure in DW1 that deduplicates the data in the signindata table.How should you complete the T-SQL statement? To answer, select the appropriate options in the answer area.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: Feb. 12, 2025, 10:31 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/156415-exam-dp-600-topic-1-question-159-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 160 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 160
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant.You are creating a Fabric Data Factory pipeline.You have a stored procedure that returns the number of active customers and their average sales for the current month.You need to add an activity that will execute the stored procedure in a warehouse. The returned values must be available to the downstream activities of the pipeline.Which type of activity should you add? 
Suggested Answer: C 🗳️ 

A. Get metadata

B. Switch

C. Lookup

D. Append variable

**Answer: C**

**Timestamp: Feb. 12, 2025, 2:54 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/156401-exam-dp-600-topic-1-question-160-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 161 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 161
Topic #: 1

[All DP-600 Questions]

HOTSPOT -You have the following T-SQL statement.For each of the following statements, select Yes if the statement is true. Otherwise, select No.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: Jan. 21, 2025, 9:06 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/155112-exam-dp-600-topic-1-question-161-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 162 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 162
Topic #: 1

[All DP-600 Questions]

HOTSPOT -You have a Fabric warehouse that contains the following data.The data has the following characteristics:• Each customer is assigned a unique CustomerID value.• Each customer is associated to a single SalesRegion value.• Each customer is associated to a single CustomerAddress value.• The Customer table contains 5 million rows.• All foreign key values are non-null.You need to create a view to denormalize the data into a customer dimension that contains one row per distinct CustomerID value. The solution must minimize query processing time and resources.How should you complete the T-SQL statement? To answer, select the appropriate options in the answer area.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: Feb. 20, 2025, 8:17 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/156876-exam-dp-600-topic-1-question-162-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 163 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 163
Topic #: 1

[All DP-600 Questions]

You have a query in Microsoft Power BI Desktop that contains two columns named Order_Date and Shipping_Date.You need to create a column that will calculate the number of days between Order_Date and Shipping_Date for each row.Which Power Query function should you use? 
Suggested Answer: B 🗳️ 

A. DateTime.LocalNow

B. Duration.Days

C. Duration.From

D. Date.AddDays

**Answer: B**

**Timestamp: Feb. 12, 2025, 2:59 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/156402-exam-dp-600-topic-1-question-163-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 164 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 164
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant that contains a semantic model.You need to modify object-level security (OLS) for the model.What should you use? 
Suggested Answer: D 🗳️ 

A. the Fabric service

B. Microsoft Power BI Desktop

C. ALM Toolkit

D. Tabular Editor

**Answer: D**

**Timestamp: March 27, 2025, 10:15 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/169935-exam-dp-600-topic-1-question-164-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 165 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 165
Topic #: 1

[All DP-600 Questions]

You have a Microsoft Power BI semantic model that contains a measure named TotalSalesAmount. TotalSalesAmount returns a sales revenue amount that is translated into a selected currency.You need to ensure that the value returned by TotalSalesAmount is formatted to use the correct currency symbol.What should you include in the solution? 
Suggested Answer: C 🗳️ 

A. a field parameter

B. a linguistic schema

C. a dynamic format string

D. the WINDOW DAX function

**Answer: C**

**Timestamp: Feb. 11, 2025, 10:44 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/156348-exam-dp-600-topic-1-question-165-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 166 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 166
Topic #: 1

[All DP-600 Questions]

You plan to use Fabric to store data.You need to create a data store that supports the following:• Writing data by using T-SQL• Multi-table transactions• Dynamic data maskingWhich type of data store should you create? 
Suggested Answer: C 🗳️ 

A. KQL database

B. lakehouse

C. warehouse

D. semantic model

**Answer: C**

**Timestamp: March 31, 2025, 3:55 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/170174-exam-dp-600-topic-1-question-166-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 167 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 167
Topic #: 1

[All DP-600 Questions]

DRAG DROP -You have a Fabric tenant that contains a workspace named Workspace1. Workspace1 uses the Pro license mode and contains a semantic model named Model1.You have an Azure DevOps organization.You need to enable version control for Workspace1. The solution must ensure that Model1 is added to the repository.Which three actions should you perform in sequence? To answer, move the appropriate actions from the list of actions to the answer area and arrange them in the correct order. 
Suggested Answer: 

**Answer: **

**Timestamp: Feb. 13, 2025, 3:46 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/156457-exam-dp-600-topic-1-question-167-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 168 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 168
Topic #: 1

[All DP-600 Questions]

HOTSPOT -You have a Fabric tenant that contains a workspace named Enterprise. Enterprise contains a semantic model named Model1. Model1 contains a date parameter named Date1 that was created in Power Query.You build a deployment pipeline named Enterprise Data that includes two stages named Development and Test. You assign the Enterprise workspace to the Development stage.You need to perform the following actions:• Create a workspace named Enterprise [Test] and assign the workspace to the Test stage.• Configure a rule that will modify the value of Date1 when changes are deployed to the Test stage.Which two settings should you use? To answer, select the appropriate settings in the answer area.NOTE: Each correct answer is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: Feb. 27, 2025, 10:54 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/157185-exam-dp-600-topic-1-question-168-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 169 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 169
Topic #: 1

[All DP-600 Questions]

HOTSPOT -You have two Microsoft Power BI queries named Employee and Retired Roles.You need to merge the Employee query with the Retired Roles query. The solution must ensure that duplicate rows in each query are removed.Which column and Join Kind should you use in Power Query Editor? To answer, select the appropriate options in the answer area.NOTE: Each correct answer is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: Jan. 21, 2025, 8:29 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/155103-exam-dp-600-topic-1-question-169-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 170 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 170
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant that contains a workspace named Workspace1 and a user named User1. Workspace1 contains a warehouse named DW1.You share DW1 with User1 and assign User1 the default permissions for DW1.What can User1 do? 
Suggested Answer: C 🗳️ 

A. Build reports by using the default dataset.

B. Read data from the tables in DW1.

C. Connect to DW1 via the Azure SQL Analytics endpoint.

D. Read the underlying Parquet files from OneLake.

**Answer: C**

**Timestamp: March 12, 2025, 2:51 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/168927-exam-dp-600-topic-1-question-170-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 171 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 171
Topic #: 1

[All DP-600 Questions]

HOTSPOT -You have a Fabric tenant that contains a workspace named Workspace1 and a user named DBUser. Workspace1 contains a lakehouse named Lakehouse1. DBUser does NOT have access to the tenant.You grant DBUser access to Lakehouse1 as shown in the following exhibit.Use the drop-down menus to select the answer choice that completes each statement based on the information presented in the graphic.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: April 23, 2025, 8:13 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/302874-exam-dp-600-topic-1-question-171-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 172 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 172
Topic #: 1

[All DP-600 Questions]

DRAG DROP -You have a Fabric workspace named Workspace1.You have three groups named Group1, Group2, and Group3.You need to assign a workspace role to each group. The solution must follow the principle of least privilege and meet the following requirements:• Group1 must be able to write data to Workspace1, but be unable to add members to Workspace1.• Group2 must be able to configure and maintain the settings of Workspace1.• Group3 must be able to write data and add members to Workspace1, but be unable to delete Workspace1.Which workspace role should you assign to each group? To answer, drag the appropriate roles to the correct groups. Each role may be used once, more than once, or not at all. You may need to drag the split bar between panes or scroll to view content.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: March 23, 2025, 7:01 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/169735-exam-dp-600-topic-1-question-172-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 173 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 173
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant named Tenant1 that contains a lakehouse named Lakehouse1.You need to add data to Lakehouse1 from a CSV file in an Azure Storage account outside of Fabric. The solution must minimize development effort.What should you use to add the data? 
Suggested Answer: B 🗳️ 

A. copy job

B. shortcut

C. pipeline

D. Dataflow Gen2

**Answer: B**

**Timestamp: March 23, 2025, 7:02 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/169736-exam-dp-600-topic-1-question-173-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 174 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 174
Topic #: 1

[All DP-600 Questions]

HOTSPOT -You have a Fabric warehouse that contains a table named Table1. Table1 contains the following data.You need to create a T-SQL statement that meets the following requirements:• Outputs the item name of each item and returns a null value if the item name is longer than 20 characters• Outputs the PurchaseDate value in the format of МММ dd, yyHow should you complete the statement? To answer, select the appropriate options in the answer area.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: March 12, 2025, 3:18 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/168930-exam-dp-600-topic-1-question-174-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 175 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 175
Topic #: 1

[All DP-600 Questions]

DRAG DROP -You have a Fabric warehouse named Warehouse1 that contains a table named dbo.Product.dbo.Product contains the following columns.You need to use a T-SQL query to add a column named PriceRange to dbo.Product. The column must categorize each product based on UnitPrice. The solution must meet the following requirements:• If UnitPrice is 0, PriceRange is "Not for resale".• If UnitPrice is less than 50, PriceRange is "Under $50".• If UnitPrice is between 50 and 250, PriceRange is "Under $250“.• In all other instances, PriceRange is "$250+".How should you complete the query? To answer, drag the appropriate values to the correct targets. Each value may be used once, more than once, or not at all. You may need to drag the split bar between panes or scroll to view content.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: May 17, 2025, 12:28 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/303676-exam-dp-600-topic-1-question-175-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 176 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 176
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant.You are creating a Fabric Data Factory pipeline.You have a stored procedure that returns the number of active customers and their average sales for the current month.You need to add an activity that will execute the stored procedure in a warehouse. The returned values must be available to the downstream activities of the pipeline.Which type of activity should you add? 
Suggested Answer: B 🗳️ 

A. Append variable

B. Script

C. Stored procedure

D. Get metadata

**Answer: B**

**Timestamp: March 12, 2025, 3:26 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/168933-exam-dp-600-topic-1-question-176-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 177 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 177
Topic #: 1

[All DP-600 Questions]

HOTSPOT -You have a Fabric workspace that contains a warehouse named Warehouse1. Warehouse1 contains the following data.You need to create a T-SQL statement that will denormalize the tables and include the ContractType and StartDate attributes in the results. The solution must meet the following requirements:• Include attributes from matching rows in the Contract table.• Ensure that all the rows from the Employee table are preserved.• Return the total number of employees per contract type for all the contract types that have more than two employees.How should you complete the statement? To answer, select the appropriate options in the answer area.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: April 3, 2025, 8 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/178981-exam-dp-600-topic-1-question-177-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 178 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 178
Topic #: 1

[All DP-600 Questions]

HOTSPOT -You have a KQL database that contains a table named Readings.You need to query Readings and return the results shown in the following table.How should you complete the query? To answer, select the appropriate options in the answer area.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: March 12, 2025, 3:39 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/168939-exam-dp-600-topic-1-question-178-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 179 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 179
Topic #: 1

[All DP-600 Questions]

HOTSPOT -You have a Fabric workspace that contains a warehouse named DW1. DW1 contains the following tables and columns.You need to summarize order quantities by year and product. The solution must include the yearly sum of order quantities for all the products in each row.How should you complete the T-SQL statement? To answer, select the appropriate options in the answer area.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: March 12, 2025, 4:05 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/168942-exam-dp-600-topic-1-question-179-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 180 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 180
Topic #: 1

[All DP-600 Questions]

You have a Fabric workspace named Workspace1.Workspace1 contains multiple semantic models, including a model named Model1. Model1 is updated by using an XMLA endpoint.You need to increase the speed of the write operations of the XMLA endpoint.What should you do? 
Suggested Answer: B 🗳️ 

A. Delete any unused semantic models from Workspace1.

B. Select Large semantic model storage format for Workspace1.

C. Configure Model 1 to use the Direct Lake storage format.

D. Delete any unused columns from Model1.

**Answer: B**

**Timestamp: March 12, 2025, 4:14 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/168943-exam-dp-600-topic-1-question-180-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 181 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 181
Topic #: 1

[All DP-600 Questions]

You have a Fabric workspace named Workspace1.You need to create a semantic model named Model1 and publish Model1 to Workspace1. The solution must meet the following requirements:• Can revert to previous versions of Model1 as required.• Identifies differences between saved versions of Model1.• Uses Microsoft Power Bl=I Desktop to publish to Workspace1.• Can edit item definition files by using Microsoft Visual Studio Code.Which two actions should you perform? Each correct answer presents part of the solution.NOTE: Each correct selection is worth one point. 
Suggested Answer: AD 🗳️ 

A. Enable Git integration for Workspace1.

B. Save Model1 in Power BI Desktop as a PBIT file.

C. Enable users to edit data models in the Power BI service.

D. Save Model1 in Power BI Desktop as a PBIP file.

**Answer: A**

**Timestamp: May 1, 2025, 3:31 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/303199-exam-dp-600-topic-1-question-181-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 182 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 182
Topic #: 1

[All DP-600 Questions]

You have a Fabric workspace named Workspace1 that is assigned to a newly created Fabric capacity named Capacity1.You create a semantic model named Model1 and deploy Model1 to Workspace1.You need to publish changes to Model1 directly from Tabular Editor.What should you do? 
Suggested Answer: D 🗳️ 

A. For Workspace1, enable Git integration.

B. For Model1, enable external sharing.

C. For Workspace1, create a managed private endpoint.

D. For Capacity1, set XMLA Endpoint to Read Write.

**Answer: D**

**Timestamp: March 13, 2025, 11:01 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/168987-exam-dp-600-topic-1-question-182-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 183 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 183
Topic #: 1

[All DP-600 Questions]

HOTSPOT -You are creating a report and a semantic model in Microsoft Power BI Desktop.The Value measure has the expression shown in the following exhibit.Use the drop-down menus to select the answer choice that completes each statement based on the information presented in the graphic.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: March 29, 2025, 7:10 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/170143-exam-dp-600-topic-1-question-183-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 184 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 184
Topic #: 1

[All DP-600 Questions]

DRAG DROP -You have a Fabric lakehouse named Lakehouse1.You have the data sources shown in the following table.You need to ingest data from both data sources into Lakehouse1. The solution must minimize maintenance and development time.What should you use to ingest the data into each data source? To answer, drag the appropriate options to the correct data sources. Each option may be used once, more than once, or not at all. You may need to drag the split bar between panes or scroll to view content.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: Aug. 4, 2025, 5:08 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/308458-exam-dp-600-topic-1-question-184-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 186 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 186
Topic #: 1

[All DP-600 Questions]

DRAG DROP -You have a Fabric eventhouse named Eventhouse1 that contains a table named Weatherdata. A sample of the data in Weatherdata is shown in the following table.You plan to use a KQL queryset to manipulate the data in Eventhouse1. The result set must have the following columns.You need to build the query.Which four KQL statements should you use in sequence? To answer, move the appropriate statements from the list of statements to the answer area and arrange them in the correct order. 
Suggested Answer: 

**Answer: **

**Timestamp: Aug. 4, 2025, 5:07 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/308454-exam-dp-600-topic-1-question-186-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 187 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 187
Topic #: 1

[All DP-600 Questions]

You have a Fabric workspace named Workspace1 that contains an eventstream named Eventstream1.Eventstream1 reads data from an Azure event hub named Eventhub1.Eventhub1 contains the following columns.You need to add a continuous percentile calculation to the Payload column. The solution must minimize development effort.What should you do? 
Suggested Answer: D 🗳️ 

A. Add a KQL queryset to Workspace1.

B. Add a Group by transformation to Eventstream1.

C. Add a Manage fields transformation to Eventstream1.

D. Add an Aggregate transformation to Eventstream1.

**Answer: D**

**Timestamp: Aug. 4, 2025, 5:07 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/308450-exam-dp-600-topic-1-question-187-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 188 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 188
Topic #: 1

[All DP-600 Questions]

You have a Fabric warehouse that contains a table named Table1. Table1 contains three columns named SalesAmount, ProductCategory, and TransactionDate.You need to create a Microsoft Power BI query that will calculate the total sales amount of each product category for transactions that occurred during the last quarter.Which two actions should you perform in the visual query editor? Each correct answer presents part of the solution.NOTE: Each correct selection is worth one point. 
Suggested Answer: CD 🗳️ 

A. For the TransactionDate column, select Remove duplicates.

B. For the TransactionDate column, select Keep top rows and set Number of rows to 90.

C. For the TransactionDate column, select Filter rows and set the value to last quarter.

D. For the ProductCategory column, select Group by and sum the SalesAmount column.

E. For the SalesAmount column, select Transformation number column - Standard, select Add, and then set the value to 90.

**Answer: C**

**Timestamp: Aug. 4, 2025, 5:07 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/308448-exam-dp-600-topic-1-question-188-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 189 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 189
Topic #: 1

[All DP-600 Questions]

You have a Microsoft Power BI semantic model.You need to identify any surrogate key columns in the model that have the Summarize By property set to a value other than to None. The solution must minimize effort.What should you use? 
Suggested Answer: C 🗳️ 

A. Performance Analyzer in Power BI Desktop

B. Model explorer in Microsoft Power BI Desktop

C. Model view in Microsoft Power BI Desktop

D. DAX Formatter in DAX Studio

**Answer: C**

**Timestamp: Aug. 4, 2025, 5:07 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/308451-exam-dp-600-topic-1-question-189-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 192 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 192
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant that contains the workspaces shown in the following table.You have a deployment pipeline named Pipeline1 that deploys items from Workspace_DEV to Workspace_TEST. In Pipeline1, all items that have matching names are paired.You deploy the contents of Workspace_DEV to Workspace_TEST by using Pipeline1.What will the contents of Workspace_TEST be once the deployment is complete? 
Suggested Answer: C 🗳️ 

A. Lakehouse2 -Notebook2 -SemanticModel1 -

B. Lakehouse1 -Notebook1 -Pipeline1 -SemanticModel1 -

C. Lakehouse1 -Lakehouse2 -Notebook1 -Notebook2 -Pipeline1 -SemanticModel1 -

D. Lakehouse2 -Notebook2 -Pipeline1 -SemanticModel1

**Answer: C**

**Timestamp: July 24, 2025, 10:20 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/307124-exam-dp-600-topic-1-question-192-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 193 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 193
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant that contains a workspace named Workspace1 and a user named User1. Workspace1 contains a warehouse named DW1.You share DW1 with User1 and assign User1 the default permissions for DW1.What can User1 do? 
Suggested Answer: A 🗳️ 

A. Read data from the tables in DW1.

B. Build reports by using the default dataset.

C. Read the underlying Parquet files from OneLake.

D. Connect to DW1 via the TDS (Tabular Data Stream) endpoint.

**Answer: A**

**Timestamp: Aug. 4, 2025, 5:07 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/308456-exam-dp-600-topic-1-question-193-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 194 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 194
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant that contains two workspaces named Workspace1 and Workspace2.Workspace1 is used as the development environment. Workspace2 is used as the production environment. Each environment uses a different storage account.Workspace1 contains a Dataflow Gen2 named Dataflow1. The data source of Dataflow1 is a CSV file in blob storage.You plan to implement a deployment pipeline to deploy items from Workspace1 to Workspace2.You need to ensure that the data source references the correct location in the production environment.What should you do? 
Suggested Answer: C 🗳️ 

A. Create a data source rule only.

B. Create a parameter rule only.

C. Create a data source rule and a parameter rule.

D. After implementing the deployment pipeline, manually change the data source

**Answer: C**

**Timestamp: Aug. 4, 2025, 5:07 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/308452-exam-dp-600-topic-1-question-194-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 195 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 195
Topic #: 1

[All DP-600 Questions]

You have a semantic model named Model1 that contains data that relates to customers and their bank account balances.Model1 has the following tables and columns.A customer can have one or more accounts. Each account can be associated to multiple customers.You need to ensure that users can query Model1 to identify the total transaction amounts by customer.What should you add to Model1? 
Suggested Answer: B 🗳️ 

A. a many-to-many relationship between FactTransaction and Dim Customer

B. a bridge table with relationships to DimCustomer and DimAccount

C. a bridge table with relationships to FactTransaction and DimCustomer

D. the CustomerKey column in FactTransaction and a relationship to DimCustomer

**Answer: B**

**Timestamp: Aug. 4, 2025, 5:07 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/308457-exam-dp-600-topic-1-question-195-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 196 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 196
Topic #: 1

[All DP-600 Questions]

You have a Fabric tenant that contains 30 CSV files in OneLake. The files are updated daily.You create a Microsoft Power BI semantic model named Model1 that uses the CSV files as a data source. You configure incremental refresh for Model1 and publish the model to an F64 capacity in the Fabric tenant.When you initiate a refresh of Model1, the refresh fails after running out of resources.What is a possible cause of the failure? 
Suggested Answer: E 🗳️ 

A. XMLA Endpoint is set to Read Only.

B. Query folding is occurring.

C. The data type of the column used to partition the data has changed.

D. Only refresh complete days is selected.

E. Query folding is NOT occurring.

**Answer: E**

**Timestamp: July 24, 2025, 10:44 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/307125-exam-dp-600-topic-1-question-196-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 197 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 197
Topic #: 1

[All DP-600 Questions]

DRAG DROP -You are implementing two dimension tables named Customers and Products in a Fabric warehouse.You need to create two slowly changing dimensions that meet the requirements shown in the following table.Which type of SCD should you use for each table? To answer, drag the appropriate SCD types to the correct tables. Each SCD type may be used once, more than once, or not at all. You may need to drag the split bar between panes or scroll to view content.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: July 24, 2025, 12:15 p.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/307126-exam-dp-600-topic-1-question-197-discussion/)

----------------------------------------

## Exam DP-600 topic 1 question 198 discussion

Actual exam question from

Microsoft's
DP-600

Question #: 198
Topic #: 1

[All DP-600 Questions]

HOTSPOT -You have a Fabric eventhouse that contains a KQL database. The database contains a table named TaxiData that stores the following data.You need to create a column named FirstPickupDateTime that will contain the first value of each hour from tpep_pickup_datetime partitioned by payment_type.How should you complete the query? To answer, select the appropriate options in the answer area.NOTE: Each correct selection is worth one point. 
Suggested Answer: 

**Answer: **

**Timestamp: Aug. 4, 2025, 5:07 a.m.**

[View on ExamTopics](https://www.examtopics.com/discussions/microsoft/view/308455-exam-dp-600-topic-1-question-198-discussion/)

----------------------------------------

