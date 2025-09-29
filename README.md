# End-to-End Data Engineering Workflow for Adventure Works Dataset

## 📌 Project Overview

This project demonstrates an **end-to-end data engineering workflow** using the **Adventure Works dataset** (CSV files). The workflow is built on a **medallion architecture (Bronze → Silver → Gold)** and leverages multiple Azure services to build a modern data pipeline for reporting and analytics.

## ⚙️ Architecture

* **Bronze Layer (Raw Data):**

  * Adventure Works CSV files fetched dynamically from an API source.
  * Stored as raw files in **Azure Data Lake Storage (ADLS) containers** using **Azure Data Factory (Copy Data Activity pipeline)**.

* **Silver Layer (Cleaned & Transformed Data):**

  * Data pulled from ADLS into **Azure Databricks**.
  * Transformations performed (data cleaning, standardization, joining, enrichment).
  * Processed data written back to ADLS.

* **Gold Layer (Analytics & Reporting):**

  * Transformed data loaded into **Azure Synapse Analytics** for further aggregation and analysis.
  * **Power BI** dashboards built on top of Synapse to provide insights and visualization.

## 🏗️ Tech Stack

* **Data Ingestion:** Azure Data Factory (ADF)
* **Storage:** Azure Data Lake Storage (ADLS Gen2)
* **Transformations:** Azure Databricks (PySpark)
* **Data Warehouse:** Azure Synapse Analytics
* **Visualization:** Power BI
* **Architecture Pattern:** Medallion (Bronze, Silver, Gold)

## 🚀 Workflow

1. **Ingestion:**

   * ADF pipeline fetches CSV files from API source.
   * Files are stored in the **Raw (Bronze) container** of ADLS.

2. **Transformation (Silver Layer):**

   * Databricks cluster connected to ADLS.
   * Data cleaning, transformations, and schema unification performed.
   * Output stored in the **Silver container** of ADLS.

3. **Analytics (Gold Layer):**

   * Silver data loaded into **Azure Synapse Analytics**.
   * Fact and dimension tables created for reporting.

4. **Visualization:**

   * Power BI connected to Synapse for dashboards and reports.

## 📊 Example Use Cases

* Sales performance tracking
* Product category analysis
* Store-level insights
* Customer purchasing patterns

## 🔧 How to Run

1. Clone this repository.
2. Set up Azure services:

   * Create ADLS Gen2 container.
   * Configure ADF linked services (API source + ADLS).
   * Create and run the **Copy Data pipeline**.
3. Configure Databricks cluster and connect with ADLS.
4. Run transformation notebooks for **Silver layer**.
5. Load cleaned data into Synapse (Gold layer).
6. Connect Power BI to Synapse and build dashboards.

## 📐 Architecture Diagram
Raw Data (API Source)
        |
        v
Azure Data Factory (Pipelines)
        |
        v
Azure Data Lake Storage (Bronze Layer)
        |
        v
Azure Databricks (Silver Layer)
        |
        v
Azure Synapse Analytics (Gold Layer)
        |
        v
Power BI (Visualization)


## 📜 License

This project is for educational and portfolio purposes.

---

✨ Built as part of a data engineering learning journey to showcase Azure-based ETL pipelines and reporting.
