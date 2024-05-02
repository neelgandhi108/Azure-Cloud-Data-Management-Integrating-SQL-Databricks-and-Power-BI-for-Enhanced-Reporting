# Azure Cloud Data-Management Integrating SQL,Databricks and Power-BI for Enhanced-Reporting
[Azure Architecture](https://github.com/neelgandhi108/Azure-Cloud-Data-Management-Integrating-SQL-Databricks-and-Power-BI-for-Enhanced-Reporting/tree/main/assets/Azure_Architecture.png)

## Introduction

The project provides a practical learning platform for data engineering, focusing on ETL pipeline construction and techniques. It's an invaluable resource for businesses transitioning from local databases to cloud-based solutions, enhancing their data management and reporting capabilities.

## Environment and Setup

- AdventureWorks, a well-known database from Microsoft, was utilized.
- A local Microsoft SQL Server setup on a personal computer was employed for initial data management.
- User credentials, including those for the new "nik" user profile, were securely stored in Azure Key Vault.

## Data Engineering Pipeline Overview

### Data Ingestion

Data migration from the on-premises SQL server to Azure SQL involved:

- Installing Self-Hosted Integration Runtime.
- 
- Integrating Azure Data Factory with the local SQL server.
 - **Screenshot:  [Table_Connect](https://github.com/neelgandhi108/Azure-Cloud-Data-Management-Integrating-SQL-Databricks-and-Power-BI-for-Enhanced-Reporting/tree/main/assets/Table_Connect.png),[On-premis SQL server](https://github.com/neelgandhi108/Azure-Cloud-Data-Management-Integrating-SQL-Databricks-and-Power-BI-for-Enhanced-Reporting/tree/main/assets/On-premis_SQL_server.png)**
   
- Automating data transfers to Azure Data Lake's "bronze" folder.
- **Screenshot: [Bronze_Silver_Gold](https://github.com/neelgandhi108/Azure-Cloud-Data-Management-Integrating-SQL-Databricks-and-Power-BI-for-Enhanced-Reporting/tree/main/assets/Bronze_Silver_Gold.png)**

### Data Transformation

Using Azure Databricks and PySpark, data underwent transformation across the medallion architecture (bronze, silver, gold layers):

- Data stored in parquet format in the "bronze" layer was transformed to delta format as it advanced through to the "gold" layer.
- Azure Data Factory managed the orchestration of Databricks notebooks to automate these transformations.
- **Screenshots: [db-synapse](https://github.com/neelgandhi108/Azure-Cloud-Data-Management-Integrating-SQL-Databricks-and-Power-BI-for-Enhanced-Reporting/tree/main/assets/db-synapse.png), [df-pipeline](https://github.com/neelgandhi108/Azure-Cloud-Data-Management-Integrating-SQL-Databricks-and-Power-BI-for-Enhanced-Reporting/tree/main/assets/df-pipeline.png), [synapse-pipeline](https://github.com/neelgandhi108/Azure-Cloud-Data-Management-Integrating-SQL-Databricks-and-Power-BI-for-Enhanced-Reporting/tree/main/assets/synapse-pipeline.png)**

### Data Loading

Azure Synapse was instrumental in loading transformed data from the "gold" folder into a server-less SQL database, facilitating direct queries from Power BI.

- **Screenshot: [Azure Synapse](https://github.com/neelgandhi108/Azure-Cloud-Data-Management-Integrating-SQL-Databricks-and-Power-BI-for-Enhanced-Reporting/tree/main/assets/Azure_Synapse.png)**

### Data Reporting

A dynamic Power BI report was created, enabling real-time data visualization of the AdventureWorks dataset. This included sales metrics, product details, and customer demographics, among other insights.

- **Screenshot: [PowerBI-dashboard](https://github.com/neelgandhi108/Azure-Cloud-Data-Management-Integrating-SQL-Databricks-and-Power-BI-for-Enhanced-Reporting/tree/main/assets/PowerBI-dashboard.png)**

### Security and Governance

Implementation of Azure Active Directory and Azure Key Vault ensured robust data security and compliance monitoring throughout the project.

- **Screenshots: , [ressource-group](https://github.com/neelgandhi108/Azure-Cloud-Data-Management-Integrating-SQL-Databricks-and-Power-BI-for-Enhanced-Reporting/tree/main/assets/ressource-group.png) , [Activity_runs](https://github.com/neelgandhi108/Azure-Cloud-Data-Management-Integrating-SQL-Databricks-and-Power-BI-for-Enhanced-Reporting/tree/main/assets/Activity_runs.png)**

## Insights and Analytics

- Revenue distribution by product categories and demographic insights highlighted key business metrics.
- Geographical sales data underscored regional market strengths and opportunities.
- **Screenshots: [Azure Dashboard](https://github.com/neelgandhi108/Azure-Cloud-Data-Management-Integrating-SQL-Databricks-and-Power-BI-for-Enhanced-Reporting/tree/main/assets/Azure_Dashboard.png), [Storage_Mount](https://github.com/neelgandhi108/Azure-Cloud-Data-Management-Integrating-SQL-Databricks-and-Power-BI-for-Enhanced-Reporting/tree/main/assets/Storage_Mount.png), [Query_Execution](https://github.com/neelgandhi108/Azure-Cloud-Data-Management-Integrating-SQL-Databricks-and-Power-BI-for-Enhanced-Reporting/tree/main/assets/Query_Execution.png)**

## Project Validation

The pipeline's functionality was tested by simulating the addition of new customer data, which was successfully reflected in the Power BI report.

- **Screenshots: [Process_Flow](https://github.com/neelgandhi108/Azure-Cloud-Data-Management-Integrating-SQL-Databricks-and-Power-BI-for-Enhanced-Reporting/tree/main/assets/Process_Flow.png)**
