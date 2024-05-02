# Azure-Cloud-Data-Management-Integrating-SQL-Databricks-and-Power-BI-for-Enhanced-Reporting

## Introduction

The project provides a practical learning platform for data engineering, focusing on ETL pipeline construction and techniques. It's an invaluable resource for businesses transitioning from local databases to cloud-based solutions, enhancing their data management and reporting capabilities.

## Environment and Setup

-   AdventureWorks, a well-known database from Microsoft, was utilized.
-   A local Microsoft SQL Server setup on a personal computer was employed for initial data management.
-   User credentials, including those for the new "nik" user profile, were securely stored in Azure Key Vault.

## Data Engineering Pipeline Overview

### Data Ingestion

Data migration from the on-premises SQL server to Azure SQL involved:

-   Installing Self-Hosted Integration Runtime.
-   Integrating Azure Data Factory with the local SQL server.
-   Automating data transfers to Azure Data Lake's "bronze" folder.

### Data Transformation

Using Azure Databricks and PySpark, data underwent transformation across the medallion architecture (bronze, silver, gold layers):

-   Data stored in parquet format in the "bronze" layer was transformed to delta format as it advanced through to the "gold" layer.
-   Azure Data Factory managed the orchestration of Databricks notebooks to automate these transformations.

### Data Loading

Azure Synapse was instrumental in loading transformed data from the "gold" folder into a server-less SQL database, facilitating direct queries from Power BI.

### Data Reporting

A dynamic Power BI report was created, enabling real-time data visualization of the AdventureWorks dataset. This included sales metrics, product details, and customer demographics, among other insights.

### Security and Governance

Implementation of Azure Active Directory and Azure Key Vault ensured robust data security and compliance monitoring throughout the project.

## Insights and Analytics

-   Revenue distribution by product categories and demographic insights highlighted key business metrics.
-   Geographical sales data underscored regional market strengths and opportunities.

## Project Validation

The pipeline's functionality was tested by simulating the addition of new customer data, which was successfully reflected in the Power BI report.
