# 🚀 Azure Data Factory End-to-End Data Engineering Project

## 📌 Project Overview

This project demonstrates an end-to-end ETL (Extract, Transform, Load) pipeline built using **Azure Data Factory (ADF)**. The solution ingests data from multiple sources, performs data transformation using Mapping Data Flows, implements incremental loading using a watermark approach, and stores the processed data in Azure Data Lake for analytics.

The project follows the Medallion Architecture (Bronze → Silver → Gold) to build a scalable and production-ready data pipeline.

---

## 🎯 Objectives

* Build an automated ETL pipeline using Azure Data Factory.
* Ingest data from multiple sources.
* Implement Incremental Loading using Watermark.
* Transform data using Mapping Data Flows.
* Store processed data into Azure Data Lake.
* Create reusable and modular ADF pipelines.

---

# 🏗 Architecture

```
                SQL Database
                     │
                     │
             Azure Data Factory
                     │
     ┌───────────────┼────────────────┐
     │               │                │
 On-Prem Files     REST API     Incremental SQL
     │               │                │
     └───────────────┼────────────────┘
                     │
              Azure Data Lake
                     │
               Bronze Layer
                     │
              Mapping Data Flow
                     │
               Silver Layer
                     │
              Mapping Data Flow
                     │
                Gold Layer
```

---

# ⚙ Technologies Used

* Azure Data Factory
* Azure Data Lake Storage Gen2
* Azure SQL Database
* REST API
* Self Hosted Integration Runtime
* Mapping Data Flows
* Git Integration
* JSON Datasets
* Incremental Loading (Watermark)

---

# 📂 Repository Structure

```
Azure-ADF-Project/
│
├── pipeline/
│     ├── Parent Pipeline
│     ├── API_Ingestion
│     ├── SQLToDataLake
│     ├── Silver Layer
│     └── Gold Layer
│
├── dataset/
│
├── linkedService/
│
├── dataflow/
│
├── integrationRuntime/
│
├── trigger/
│
└── factory/
```

---

# 🔄 Pipeline Workflow

## 1. Parent Pipeline

The Parent Pipeline orchestrates the complete ETL workflow.

It executes:

* On-Premises Data Ingestion
* API Data Ingestion
* Incremental SQL Loading
* Failure Alert Activity

---

## 2. API Ingestion

* Calls REST API using Web Activity.
* Copies API response into Azure Data Lake.

---

## 3. SQL to Data Lake

This pipeline performs incremental loading.

Steps:

* Read previous watermark value.
* Read latest available timestamp.
* Copy only newly inserted records.
* Update watermark after successful execution.

---

## 4. Silver Layer

* Cleans raw data.
* Removes unwanted columns.
* Performs transformations.
* Standardizes data format.

---

## 5. Gold Layer

* Performs business transformations.
* Creates analytics-ready datasets.
* Final curated layer for reporting.

---

# 📁 Data Layers

### Bronze Layer

* Raw ingested data
* No transformations

### Silver Layer

* Cleaned and validated data
* Data quality improvements

### Gold Layer

* Business-ready data
* Optimized for reporting and analytics

---

# 🔑 Key Features

* End-to-End ETL Pipeline
* Incremental Data Loading
* REST API Integration
* SQL Database Integration
* Azure Data Lake Storage
* Mapping Data Flows
* Modular Pipeline Design
* Error Handling
* Git Version Control
* Production-style Architecture

---

# 📈 Use Cases

* Data Warehousing
* Business Intelligence
* Analytics
* Reporting
* Data Engineering Learning
* Azure Data Factory Practice

---

# ▶ How to Run

1. Create an Azure Data Factory instance.
2. Import the ARM/JSON pipeline files.
3. Configure Linked Services.
4. Connect Azure SQL Database.
5. Configure Azure Data Lake Storage.
6. Set up Self Hosted Integration Runtime (if required).
7. Publish all changes.
8. Trigger the Parent Pipeline.

---

# 📚 Learning Outcomes

Through this project, I learned:

* Azure Data Factory Pipelines
* Linked Services
* Datasets
* Copy Activity
* Mapping Data Flows
* Incremental Loading
* Watermark Technique
* Azure Data Lake Storage
* Pipeline Orchestration
* Git Integration
* Error Handling
* ETL Best Practices

---

# 👨‍💻 Author

**Deepak Vyas**

Final Year Computer Engineering Student

Aspiring Azure Data Engineer | Data Engineer | Cloud Enthusiast

