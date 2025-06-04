🚀 Azure EdgeFlow – Enterprise Data Engineering Project

📊 End-to-End Azure Data Pipeline | Medallion Architecture | Real-World Scenario

---

📌 Overview

**Azure EdgeFlow** is a complete enterprise-grade Data Engineering project simulating real-world use cases using Azure's modern cloud services. It showcases:

- 🔗 Data ingestion from GitHub REST API  
- 🧱 Medallion Architecture (Bronze → Silver → Gold)  
- ⚙️ Transformations using Azure Databricks (PySpark)  
- 🗃️ Modeling in Azure Synapse Analytics  
- 📊 Visualization via Power BI

Built to reflect actual **interview use cases**, it uses low/no-code approaches (ADF dynamic pipelines, JSON config) and production best practices.

---

## 🧰 Tools & Technologies

| Layer               | Tool/Service Used                |
|---------------------|----------------------------------|
| Ingestion           | Azure Data Factory (ADF)         |
| Storage             | Azure Data Lake Storage Gen2     |
| Processing          | Azure Databricks (PySpark)       |
| Modeling            | Azure Synapse Analytics          |
| Reporting           | Power BI                         |
| Orchestration Logic | JSON Parameterization in ADF     |
| Source Data         | GitHub REST API (CSV format)     |

---

## 🏗️ Architecture Diagram
,
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
1️⃣ Prerequisites
✔️ Azure Account (Free Tier is fine)

✔️ GitHub Account

✔️ VS Code (optional, for JSON/parameter editing)

✔️ Basic knowledge of Azure, Python, SQL

2️⃣ Create Required Azure Resources
Azure Resource Group

Azure Data Lake Gen2 (with Hierarchical Namespace)

Azure Data Factory

Azure Databricks Workspace

Azure Synapse Analytics Workspace

(Optional) Power BI Desktop

3️⃣ Pipeline Steps
🟤 Phase 1: Ingest Data via ADF
Use Copy Activity to pull data from GitHub API to Bronze layer

Configure Linked Services (HTTP & ADLS)

Use parameterized JSON and ForEach loop for dynamic ingestion

🟠 Phase 2: Transform with Databricks
Read raw data into Spark DataFrames

Apply transformation logic (filter, enrich, dedupe)

Write cleaned data to Silver zone

🟡 Phase 3: Model in Synapse
Create fact and dimension tables

Load data from Silver into Synapse SQL pool

🔵 Phase 4: Visualize with Power BI
Connect Power BI to Synapse

Build real-time dashboards using Gold layer



