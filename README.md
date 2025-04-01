# SQL Data Warehouse Project

This project demonstrates the end-to-end development of a modern data warehouse using **SQL Server**. It follows the **Medallion Architecture** and simulates integrating data from multiple business systems (ERP and CRM) into a centralized analytical store using ETL best practices, dimensional modeling, and SQL scripting.

---

## 🧱 Architecture Overview

The solution is designed using a three-layered Medallion Architecture:

### 🥉 Bronze Layer – Raw Data Ingestion
- Raw CSV exports from ERP and CRM systems are ingested.
- Data is loaded into staging tables without transformation.
- Serves as the immutable source of truth.

### 🥈 Silver Layer – Cleansed & Integrated Data
- Standardization, deduplication, and normalization are applied.
- Null handling, type casting, and relationship building (joins).
- Integrates raw data into structured business entities.

### 🥇 Gold Layer – Star Schema (Analytics-Ready)
- Business-ready fact and dimension tables are created:
  - `Fact_Sales`
  - `Dim_Customers`
  - `Dim_Products`
  - `Dim_Employees`
  - `Dim_Location`
  - `Dim_Date`
- Optimized for BI tools and analytical querying.

```mermaid
flowchart TD
  A[ERP & CRM CSV Files] --> B[Bronze: Raw Staging Tables]
  B --> C[Silver: Cleaned and Integrated Tables]
  C --> D[Gold: Star Schema - Fact and Dimensions]
  D --> E[BI Tools / Reporting Layer]
