# Production-Ready Sales Data Pipeline using Microsoft Fabric

![Microsoft Fabric](https://img.shields.io/badge/Microsoft%20Fabric-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)
![PySpark](https://img.shields.io/badge/PySpark-E25A1C?style=for-the-badge&logo=apache-spark&logoColor=white)
![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)

## Project Overview

An end-to-end Data Engineering pipeline built on **Microsoft Fabric** using the **Medallion Architecture** (Bronze → Silver → Gold) to transform raw sales CSV data into business-ready analytics and reporting through Power BI.

This project demonstrates real-world data engineering practices including automated orchestration, data quality validation, audit logging, and layered data transformation using PySpark.

---

## Architecture

```
Raw CSV Files
      │
      ▼
┌─────────────┐
│   BRONZE    │  ← Raw ingestion · No transformations · Source of truth
│  Lakehouse  │
└─────────────┘
      │
      ▼
┌─────────────┐
│   SILVER    │  ← Cleaned · Validated · Standardised with PySpark
│  Lakehouse  │
└─────────────┘
      │
      ▼
┌─────────────┐
│    GOLD     │  ← Aggregated metrics · Business-ready · Power BI ready
│  Lakehouse  │
└─────────────┘
      │
      ▼
┌─────────────────────┐
│  Sales Decision     │  ← Interactive Power BI Dashboard
│     Dashboard       │
└─────────────────────┘
```

---

## Tech Stack

| Tool | Purpose |
|---|---|
| Microsoft Fabric | Cloud data platform and workspace |
| PySpark | Data transformation and processing |
| Delta Lake | Storage format across all layers |
| Data Factory Pipelines | Orchestration and automation |
| Power BI | Reporting and visualisation |
| Python | Scripting and data quality logic |

---

## Project Structure

```
fabric-medallion-sales-analytics/
│
├── notebooks/
│   ├── bronze_ingestion.ipynb       # Raw CSV ingestion into Bronze lakehouse
│   ├── silver_transform.ipynb       # PySpark cleaning and transformation
│   ├── gold_metrics.ipynb           # Aggregations and business metrics
│   ├── data_quality_checks.ipynb    # Validation rules and quality checks
│   └── inspection.ipynb             # Audit logging and data inspection
│
├── screenshots/
│   ├── pipeline_flow.png            # Medallion automation pipeline
│   └── dashboard.png                # Power BI Sales Decision Dashboard
│
└── README.md
```

---

## Pipeline Stages

### Bronze — Raw Ingestion
- Ingests raw sales CSV files (200 records) into the Bronze lakehouse
- No transformations applied — data stored as-is for traceability
- Maintains the original source of truth

### Silver — Transform and Clean
- Built using **PySpark DataFrames**
- Handles null values, data type casting, and column standardisation
- Removes duplicates and applies business rules
- Writes clean data to Silver lakehouse in Delta format

### Gold — Aggregations and Metrics
- Produces business-ready aggregated tables using PySpark
- Key metrics include:
  - Total sales and revenue summaries
  - Sales aggregations by category, region, and time period
  - Top performing products and trends
- Optimised for Power BI consumption

### Data Quality Checks
- Validates row counts across layers
- Checks for nulls, duplicates, and schema consistency
- Flags anomalies before data moves to the next layer

### Inspection and Audit Logging
- Tracks pipeline run metadata
- Logs record counts, timestamps, and layer status
- Supports traceability and debugging

### Orchestration
- **Medallion_Automation_Pipeline** orchestrates all notebooks end-to-end
- Automated trigger ensures Bronze → Silver → Gold runs in sequence
- Built using Microsoft Fabric Data Factory pipelines

---

## Dataset

- **Source:** Sample sales transaction CSV files
- **Volume:** 200 records
- **Key fields:** Transaction ID, Product, Category, Region, Sales Amount, Date

---

## Key Learnings

- Implementing Medallion Architecture in Microsoft Fabric
- PySpark transformations and DataFrame operations
- Data quality validation patterns in production pipelines
- Pipeline orchestration and automation
- Delta Lake storage and Power BI integration

---

## Author

**Harini**   
