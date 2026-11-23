# Consumer-Financial-Complaints-Analytics
End-to-end Microsoft Fabric analytics project transforming 900K+ CFPB consumer complaints into a production-ready Lakehouse, star schema, automated data pipeline, and interactive Power BI dashboard.

![Consumer Financial Complaints Analytics](images/slides/project_cover.png)

This project transforms nearly 900,000 consumer financial complaints from the Consumer Financial Protection Bureau (CFPB) into a modern analytics platform using Microsoft Fabric, PySpark, Delta Lake, SQL Warehouse, and Power BI.

Starting with a raw CSV dataset, I designed and implemented a complete Bronze-Silver-Gold Medallion Architecture, built a dimensional data model, automated the data pipeline, and developed an interactive Power BI solution that enables users to analyze complaint volumes, complaint drivers, and company response outcomes across the U.S. financial services industry.

The project demonstrates practical skills in data engineering, analytics engineering, data modelling, ETL development, data quality management, business intelligence, dashboard design, and automated reporting.

# Live Project

🔗 Interactive Dashboard: [Add Link]

📓 Bronze to Silver PySpark Notebook: [notebooks/CFPB_Bronze_to_Silver_Documented.ipynb](notebooks/CFPB_Bronze_to_Silver_Documented.ipynb)

🗄️ Gold Layer SQL Scripts: [sql/](sql/)

📄 Project Documentation: [README.md](README.md)

# Project Overview

The Consumer Financial Protection Bureau (CFPB) maintains a public database of complaints submitted by consumers regarding financial products and services including mortgages, credit reporting, debt collection, bank accounts, credit cards, student loans, and money transfer services.

![How a complaint moves through the process](images/slides/cfpb_process.png)

This project converts that raw operational dataset into a structured analytics solution that answers three business questions:

| Dashboard Area | Business Question |
| :--- | :--- |
| **Overview** | What is happening across complaint volume, products, companies, channels, and locations? |
| **Drivers** | What issues are generating complaints and how are trends changing over time? |
| **Resolution** | How effectively are companies responding and resolving customer complaints? |

# Dashboard Preview

### Complaint Overview
![Consumer Complaints Overview](images/dashboard/overview_dashboard.png)

### Complaint Drivers
![Complaint Drivers](images/dashboard/drivers_dashboard.png)

### Complaint Resolution
![Complaint Resolution](images/dashboard/resolution_dashboard.png)

# Architecture

![Project Workflow](images/slides/project_workflow.png)

![Microsoft Fabric End-to-End Data Pipeline](images/slides/fabric_architecture.png)

```text
Kaggle API
    │
    ▼
Bronze Layer (Raw CSV)
    │
    ▼
PySpark Transformations
    │
    ▼
Silver Layer (Delta Tables)
    │
    ▼
Fabric Warehouse
(Gold Star Schema)
    │
    ▼
Direct Lake Semantic Model
    │
    ▼
Power BI Dashboard
