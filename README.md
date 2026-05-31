# Production-Ready Sales Data Pipeline using Microsoft Fabric

## Project Overview

This project demonstrates an end-to-end Data Engineering solution built using Microsoft Fabric.

The solution implements the Medallion Architecture pattern (Bronze, Silver, Gold) to transform raw sales transaction data into business-ready analytics consumed through Power BI.

Additional production-oriented features such as automated orchestration, data quality validation, audit logging, and scheduled refresh were implemented to simulate a real-world enterprise deployment.

## Technologies Used

- Microsoft Fabric
- Lakehouse
- PySpark
- Power BI
- DAX
- Data Pipelines
- Direct Lake
- SQL
- Medallion Architecture

## Architecture

Raw CSV
↓
Bronze Layer
↓
Silver Layer
↓
Gold Layer
↓
Semantic Model
↓
Power BI Dashboard
