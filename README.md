# End-to-End Data Engineering Project: Retail Sales Analysis

## Project Overview
This project demonstrates an **end-to-end data engineering pipeline** that extracts, transforms, and loads (ETL) data from various sources into a **Snowflake data warehouse** for analysis. The final goal is to provide **business intelligence (BI)** reports and dashboards using **Metabase** to analyze **retail sales**, **inventory levels**, and **stock trends**. 

Key components of the pipeline include:
- **Data Ingestion** from AWS RDS (Postgres) and AWS S3 using **Airbyte** and **AWS Lambda**.
- **Data Transformation** in **Snowflake** using **DBT** for creating optimized tables and metrics.
- **Data Visualization** with **Metabase** for creating actionable business dashboards.

---

## Data Sources
### 1. **RDS (Relational Database Service)**
   - Stores sales records and customer-related data in a **Postgres database** on AWS.
   - **Tables**: Sales, Customer, Product, and other related tables.
   - Data is refreshed **daily** using the ETL process.

### 2. **S3 Bucket**
   - Stores the **Inventory** table in a CSV format.
   - New inventory data is dumped into the S3 bucket daily, typically recording data at the end of each week.

---

## Business Requirements
1. **Snowflake Data Warehouse**:
   - Integrate several customer-related tables into one.
   - Create new **fact tables** with metrics like:
     - `sum_qty_wk`: Weekly sales quantity.
     - `sum_amt_wk`: Weekly sales amount.
     - `avg_qty_dy`: Average daily sales quantity.
     - `inv_on_hand_qty_wk`: Inventory on hand at the end of each week.
     - `wks_sply`: Weeks of supply (inventory vs. sales).
     - `low_stock_flg_wk`: Flag indicating low stock based on sales trends.

2. **Metabase Reports**:
   - Display dashboards identifying high/low-performing items, weekly sales data, and low-stock items.
   - Enable easy identification of items requiring attention due to low stock.

---

## Project Infrastructure
This project leverages the following cloud-based infrastructure:
- **AWS Servers**: Hosts various tools for data processing and ingestion.
- **Airbyte**: Used for ingesting data from RDS to Snowflake.
- **DBT**: Transforms raw data into clean, structured tables in Snowflake.
- **Snowflake**: Cloud-based data warehouse for storing and processing data.
- **Metabase**: BI tool for creating dashboards and reports.
- **AWS Lambda**: Serverless functions used to ingest inventory data from AWS S3.

---

## Setup & Installation

### Prerequisites:
- **AWS Account**: Necessary for using **AWS RDS**, **S3**, **Lambda**, and **Airbyte**.
