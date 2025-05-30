🚀 Azure EdgeFlow Data Engineering Project
📌 Overview
This project is a complete end-to-end Azure Data Engineering solution designed to simulate real-world enterprise data pipelines using modern Azure services. The project demonstrates data ingestion from external APIs, multi-layered storage using Medallion Architecture (Bronze → Silver → Gold), transformation via Azure Databricks, and reporting integration with Power BI.

The project is based on practical, real-time scenarios asked in interviews and implements automation, dynamic pipelines, and parameterization using low/no-code Azure tools.

🧰 Tools & Technologies
Azure Data Factory (ADF) – ETL orchestration & dynamic pipeline creation

Azure Data Lake Storage Gen2 – Raw/Silver/Gold zone architecture

Azure Databricks – Data transformation using PySpark

Azure Synapse Analytics – Data warehousing and SQL analytics

Power BI – Dashboarding and reporting

GitHub – Source data access via public API

JSON – Parameter config file for dynamic ADF pipelines

🏗️ Architecture
pgsql
Copy
Edit
                 +-------------------------+
                 |     GitHub API (CSV)    |
                 +-----------+-------------+
                             |
                             ▼
                    [Azure Data Factory]
                    (Dynamic Copy Activity)
                             |
           +----------------+------------------+
           |                                   |
           ▼                                   ▼
     Bronze Zone (Raw) → ADF → Silver Zone (Cleaned) → Databricks → Gold Zone (Modeled)
                                                    |
                                                    ▼
                                           Azure Synapse Analytics
                                                    |
                                                    ▼
                                                Power BI

⚙️ Features
✅ Ingest data from GitHub REST API using ADF (via HTTP linked service)

✅ Store raw data in Bronze layer using ADLS Gen2

✅ Use Dynamic Pipelines in ADF with parameterized JSON input (for multiple files)

✅ Transform data in Databricks (PySpark) and write to Silver layer

✅ Load transformed data into Azure Synapse Analytics (Gold layer)

✅ Connect Power BI to Synapse for real-time reporting

✅ Use of Medallion Architecture (Bronze → Silver → Gold)

✅ Followed real-world DevOps-style project structure

🚀 Setup Instructions
1. Prerequisites
Azure account (Free Tier works)
GitHub account
VS Code (recommended)
Basic knowledge of Azure Portal, Python, and SQL

2. Create Resources
Create:

Azure Resource Group

Azure Data Lake Gen2 with Hierarchical Namespace

Azure Data Factory

Azure Databricks workspace

Azure Synapse workspace

Power BI Desktop (optional)

3. Pipeline Steps
Phase 1: Ingest Data via ADF (Static & Dynamic Pipelines)
Use Copy Activity to pull data from GitHub API to Bronze container

Configure Linked Services for HTTP & ADLS

Set up parameterized JSON and use ForEach Activity for dynamic ingestion

Phase 2: Transform with Databricks
Read Bronze data into Spark DataFrames

Apply transformation logic

Write output to Silver Zone in ADLS

Phase 3: Model in Synapse
Create Fact and Dimension tables in Synapse

Load Silver data into Synapse tables

Phase 4: Visualize with Power BI
Connect Power BI to Synapse SQL endpoint

Build interactive dashboards

