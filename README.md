# Consumer Financial Complaints Analytics
### End-to-End Microsoft Fabric Data Engineering & Analytics Project

[DRAG & DROP: Title Banner — "Consumer Financial Complaints Analytics"]

This project transforms nearly 900,000 consumer financial complaints from the Consumer Financial Protection Bureau (CFPB) into a modern analytics platform using Microsoft Fabric, PySpark, Delta Lake, SQL Warehouse, and Power BI.

Starting with a raw CSV dataset, I designed and implemented a complete Bronze-Silver-Gold Medallion Architecture, built a dimensional data model, automated the data pipeline, and developed an interactive Power BI solution that enables users to analyze complaint volumes, complaint drivers, and company response outcomes across the U.S. financial services industry.

The project demonstrates practical skills in data engineering, analytics engineering, data modelling, ETL development, data quality management, business intelligence, dashboard design, and automated reporting.

### Executive Highlights
* **Market Concentration:** Mortgages (26.8%), Credit Reporting (22.1%), and Debt Collection (18.9%) generate **67.8%** of all consumer complaints.
* **Digital Shift & Speed:** Web submissions rose from **44.8% (2012)** to **81.5% (2017)**, cutting average company routing time to **3.0 days** vs. **8.2 days** for postal mail.
* **Timeliness vs. Relief Gap:** Companies respond on time in **97.3%** of cases, yet only **18.8%** result in consumer relief (while **77.9%** close with an explanation alone).
* **Remediation Impact:** Providing monetary or non-monetary relief cuts consumer dispute rates by more than half (**26.9%** disputed without relief vs. **10.6%–11.6%** with relief).

## Live Project

🔗 Interactive Dashboard: [Add Link]  
📓 Bronze to Silver PySpark Notebook: [Add Link]  
🗄️ Gold Layer SQL Scripts: [Add Link]  
📄 Project Documentation: [Add Link]  

## Project Overview

The Consumer Financial Protection Bureau (CFPB) maintains a public database of complaints submitted by consumers regarding financial products and services including mortgages, credit reporting, debt collection, bank accounts, credit cards, student loans, and money transfer services.

[DRAG & DROP: Slide — "How a complaint moves through the process"]

This project converts that raw operational dataset into a structured analytics solution that answers three business questions:

| Dashboard Area | Business Question |
| :--- | :--- |
| **Overview** | What is happening across complaint volume, products, companies, channels, and locations? |
| **Drivers** | What issues are generating complaints and how are trends changing over time? |
| **Resolution** | How effectively are companies responding and resolving customer complaints? |

### Interactive Dashboard Preview

#### 1. Complaint Overview
[DRAG & DROP: Screenshot — "Consumer Complaints Overview.jpg"]

#### 2. Complaint Drivers
[DRAG & DROP: Screenshot — "Complaint Drivers.jpg"]

#### 3. Complaint Resolution
[DRAG & DROP: Screenshot — "Complaint Resolutions.jpg"]

## Architecture

[DRAG & DROP: Slide — "Our project workflow"]

[DRAG & DROP: Slide — "Microsoft Fabric End-to-End Data Pipeline"]

## Skills Demonstrated

### Data Engineering
- Microsoft Fabric
- Medallion Architecture (Bronze, Silver, Gold)
- Lakehouse Design
- Delta Lake
- PySpark Data Processing
- Data Quality Validation
- Data Standardisation
- ETL / ELT Development
- Data Pipeline Automation
- Deployment Pipelines

### Analytics Engineering
- Star Schema Design
- Fact & Dimension Modelling
- SQL Data Warehousing
- Semantic Modelling
- Direct Lake Implementation

### Business Intelligence
- Power BI Development
- DAX Measures
- KPI Design
- Interactive Reporting
- Dashboard UX Design
- Data Storytelling

## Dataset & Data Quality Engineering

[DRAG & DROP: Slide — "Understanding all 18 source columns"]

[DRAG & DROP: Slide — "One complaint becomes one row"]

| Metric | Value |
| :--- | :--- |
| **Source** | CFPB Consumer Complaint Database |
| **Raw Records (Bronze)** | 903,983 |
| **Clean Records (Silver)** | 896,931 (99.2%) |
| **Quarantined Records** | 7,052 (0.8%) |
| **Date Range** | Dec 2011 – Nov 2017 |
| **Distinct Companies (Cleaned)** | 4,502 |
| **Dashboard Pages** | 3 |
| **Products Covered** | Mortgage, Credit Reporting, Debt Collection, Credit Cards, Banking, Student Loans and more |

### Key Data Engineering Decisions
* **Quarantine Gate:** Isolated **7,052 records** where `date_sent_to_company` preceded `date_received` into a separate Delta quarantine table rather than silently deleting anomalies.
* **Taxonomy & Entity Standardization:** Harmonized **166** raw issue strings into **154** post-2017 standardized categories and cleaned company whitespace/encoding variants across **4,502** institutions.
* **Privacy & ZIP Repair:** Restored dropped leading zeros on 4-digit ZIP codes (validated against state prefixes) and masked all ZIPs to `NNNXX`.
* **Direct Lake Optimization:** Dropped the sparse free-text `consumer_complaint_narrative` field (77.9% null) from Silver/Gold while preserving it in Bronze, keeping the semantic model lightweight and fast.

## Key Results

* **High Concentration:** Analysis of 896,931 validated complaints revealed that Mortgages (241K), Credit Reporting (198K), and Debt Collection (170K) account for **67.8%** of all complaints, while the top five companies account for **34.5%**.
* **Maturing Growth & Digital Shift:** Annual complaint volume grew **2.65×** between 2012 (72K) and 2016 (192K), while web submissions climbed from **44.8%** to **81.5%** of total intake.
* **High Compliance, Low Remediation:** Despite companies responding on time in **97.3%** of cases, only **18.8%** of complaints resulted in consumer relief, while **77.9%** closed with an explanation alone.
* **Rate-Based Benchmarking:** Complaint volume alone is a poor indicator of service quality—organizations of similar size displayed wide variation in dispute rates, response times, and relief outcomes (e.g., Experian achieved **100.0%** timeliness and **40.0%** relief with an **11.6%** dispute rate, compared to Wells Fargo at **95.2%** timeliness, **14.7%** relief, and **21.8%** disputes).

## Technology Stack

| Layer | Technology |
| :--- | :--- |
| **Data Source** | Kaggle API |
| **Storage** | Microsoft Fabric Lakehouse |
| **Processing** | PySpark |
| **Storage Format** | Delta Lake |
| **Data Warehouse** | Fabric Warehouse |
| **Modelling** | Star Schema (1 Fact, 7 Dimensions) |
| **Semantic Layer** | Direct Lake |
| **Reporting** | Power BI |
| **Orchestration** | Fabric Data Pipeline (`PL_CFPB_EndToEnd`) |
| **Deployment** | Fabric Deployment Pipelines (`DEV` → `PROD`) |
| **Version Control** | Git & GitHub |

## License

This repository is licensed under the MIT License.

The CFPB Consumer Complaint dataset is not owned by the author and remains subject to the original terms and conditions published by the Consumer Financial Protection Bureau (CFPB). The raw dataset is not distributed as part of this repository and should be obtained directly from the source.

Dataset source: https://www.consumerfinance.gov/data-research/consumer-complaints/
