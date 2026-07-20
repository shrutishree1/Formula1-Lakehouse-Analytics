
This project demonstrates a modern end-to-end Lakehouse Data Engineering and Analytics solution built on Databricks. It showcases industry best practices for designing scalable, governed, and high-performance data platforms using Unity Catalog, Volumes, Apache Spark (PySpark), Delta Lake, and the Medallion Architecture, transforming raw Formula 1 data into analytics-ready datasets.

------------------------------------------------------------------------------------------------------------------------------

### 🎯 Objectives

- ✅ Build an end-to-end ETL pipeline
- ✅ Implement Medallion Architecture
- ✅ Use Unity Catalog & Volumes
- ✅ Store data in Delta Lake
- ✅ Automate pipelines with Lakeflow Jobs
- ✅ Perform Incremental Data Processing
- ✅ Build analytical SQL dashboards
------------------------------------------------------------------------------------------------------------------------------

### 🏁  Project Overview
This project involves:

1. ### 🏗️ Data Architecture
Designing a modern Lakehouse Architecture using the Medallion Architecture (Bronze, Silver, and Gold layers).

2. ### ⚡ Data Engineering
Building scalable ETL pipelines using **PySpark on Databricks** to ingest, transform, and process structured (CSV) and semi-structured nested (JSON) data - including custom schema definitions, metadata tracking, and reusable ingestion logic.

3. ### ⚙️ Orchestration
Automating and scheduling the end-to-end pipeline using **Lakeflow Jobs**  managing task dependencies across Bronze → Silver → Gold layers with monitoring and retry handling.


4. ### 📦 Delta Lake
Leveraging Delta Lake for reliable, ACID-compliant storage with optimized performance and data consistency across all medallion layers.

5. ### 🔐 Data Governance & Security
Managing data access using **Unity Catalog** with a structured Catalog → Schema → Volume hierarchy for centralized governance across Bronze, Silver, and Gold layers.

6. ### 📊 Data Modeling
Developing fact and dimension tables optimized for analytical queries and reporting.

7. ### 📈 Data Analytics
Creating analytics-ready Gold layer datasets queried via **Databricks SQL**, enabling charts, dashboards, and insights on driver/constructor performance across seasons.

------------------------------------------------------------------------------------------------------------------------------

### 📊 Dataset:

🏁 Circuits (CSV)
🏁 Races (CSV)
👨‍🏎️ Drivers (JSON)
🏭 Constructors (JSON)
🏆 Results (1950–2025 JSON)
⚡ Sprints (2021–2025 JSON)

------------------------------------------------------------------------------------------------------------------------------

#### 🥉 Bronze Layer
- Raw ingestion
- Explicit & inferred schemas
- Metadata columns
- Delta tables
- Data lineage
- Metadata:
        - ingestion_timestamp
        - source_file
        - source_path
#### 🥈 Silver Layer
- Data cleaning
- Null handling
- Deduplication
- Standardization
- Business transformations
#### 🥇 Gold Layer
- Fact tables
- Dimension tables
- KPI generation
- Analytics-ready datasets
#### 🔄 Incremental Processing
- MERGE INTO
- Upserts
- Watermark strategy
- Optimized Delta writes
#### 🏗️ Lakeflow Jobs
- Automated scheduling
- Dependency management
- Monitoring
- Retry & alerts

<hr>

### Architecture

```text
CSV / JSON Files (Batch Processing)
        │
        ▼
 Databricks Volumes
        │
        ▼
 Bronze Layer
        │
        ▼
 Lakeflow Jobs
        │
        ▼
 Silver Layer
        │
        ▼
 Lakeflow Jobs
        │
        ▼
 Gold Layer
      
