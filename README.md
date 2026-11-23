# Consumer Financial Complaints Analytics
### End-to-End Microsoft Fabric Data Engineering & Analytics Project

<img width="939" height="540" alt="WhatsApp Image 2026-11-23 at 12 30 02 PM" src="https://github.com/user-attachments/assets/ea008764-894c-4910-8bcd-367221aeae57" />

This project transforms nearly 900,000 consumer financial complaints from the Consumer Financial Protection Bureau (CFPB) into a modern analytics platform using Microsoft Fabric, PySpark, Delta Lake, SQL Warehouse, and Power BI.

Starting with a raw CSV dataset, I designed and implemented a complete Bronze-Silver-Gold Medallion Architecture, built a dimensional data model, automated the data pipeline, and developed an interactive Power BI solution that enables users to analyze complaint volumes, complaint drivers, and company response outcomes across the U.S. financial services industry.

The project demonstrates practical skills in data engineering, analytics engineering, data modelling, ETL development, data quality management, business intelligence, dashboard design, and automated reporting.

### Executive Highlights
* **Market Concentration:** Mortgages (26.8%), Credit Reporting (22.1%), and Debt Collection (18.9%) generate **67.8%** of all consumer complaints.
* **Digital Shift & Speed:** Web submissions rose from **44.8% (2012)** to **81.5% (2017)**, cutting average company routing time to **3.0 days** vs. **8.2 days** for postal mail.
* **Timeliness vs. Relief Gap:** Companies respond on time in **97.3%** of cases, yet only **18.8%** result in consumer relief (while **77.9%** close with an explanation alone).
* **Remediation Impact:** Providing monetary or non-monetary relief cuts consumer dispute rates by more than half (**26.9%** disputed without relief vs. **10.6%–11.6%** with relief).

## Live Project

🔗 Interactive Dashboard: https://app.fabric.microsoft.com/links/ItRMCSt6Zi?ctid=e0239e4e-d03c-45af-8d39-8e4920dfd982&pbi_source=linkShare&bookmarkGuid=3f2d2efa-5ace-4e64-b752-4413c8481a2f


## Project Overview

The Consumer Financial Protection Bureau (CFPB) maintains a public database of complaints submitted by consumers regarding financial products and services including mortgages, credit reporting, debt collection, bank accounts, credit cards, student loans, and money transfer services.

<img width="948" height="540" alt="WhatsApp Image 2026-11-23 at 12 30 02 PM (1)" src="https://github.com/user-attachments/assets/cb5dc1fc-e577-4489-8103-cf7b44d05ac9" />

This project converts that raw operational dataset into a structured analytics solution that answers three business questions:

| Dashboard Area | Business Question |
| :--- | :--- |
| **Overview** | What is happening across complaint volume, products, companies, channels, and locations? |
| **Drivers** | What issues are generating complaints and how are trends changing over time? |
| **Resolution** | How effectively are companies responding and resolving customer complaints? |

### Interactive Dashboard Preview

#### 1. Complaint Overview
<img width="1885" height="996" alt="Consumer Complaints Overview" src="https://github.com/user-attachments/assets/53b0d9c5-d05b-472f-ab2e-7aa231d8417c" />

#### 2. Complaint Drivers
<img width="1338" height="712" alt="Complaint Drivers" src="https://github.com/user-attachments/assets/bc2ae4e4-3c07-461b-83a6-f1319b7844a6" />


#### 3. Complaint Resolution
<img width="1876" height="1001" alt="Complaint Resolutions" src="https://github.com/user-attachments/assets/d5a32dd8-c40f-40aa-a0ca-c434e369d2a8" />


## Architecture

<img width="950" height="540" alt="WhatsApp Image 2026-11-23 at 12 30 02 PM (3)" src="https://github.com/user-attachments/assets/d56320a3-d818-413f-b17d-124add9aa77b" />


<img width="3000" height="1380" alt="image" src="https://github.com/user-attachments/assets/870dd537-0574-40c6-a8c8-183072d4ec16" />

<img width="960" height="504" alt="Pipeline" src="https://github.com/user-attachments/assets/4f36beba-db8e-4f09-ab15-51dd5ddf8453" />



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

<img width="1024" height="572" alt="image" src="https://github.com/user-attachments/assets/44341404-2f8a-47f5-80c6-2806285930f9" />

<img width="1024" height="572" alt="image" src="https://github.com/user-attachments/assets/8f3ba115-374d-415c-9820-8f38d508073e" />


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

The CFPB Consumer Complaint dataset is not owned by the author and remains subject to the original terms and conditions published by the Consumer Financial Protection Bureau (CFPB). The raw dataset is not distributed as part of this repository and should be obtained directly from the source or on kaggle.

Dataset source: https://www.consumerfinance.gov/data-research/consumer-complaints/
