# Real-Time ELT Pipeline on Snowflake using Snowpipe

## Overview

This project demonstrates a production-style Real-Time ELT Pipeline built on Snowflake using modern Data Engineering concepts.

The pipeline handles:

- Real-time ingestion using Snowpipe
- Incremental processing with Streams
- Automated ELT workflows using Tasks
- Analytics modeling with Dynamic Tables
- Secure data sharing and monitoring

---

## Architecture Flow

```text
01 Setup
   ↓
02 Ingestion (Snowpipe Auto Ingestion)
   ↓
03 Streams & Tasks
   ↓
04 Analytics

Tech Stack
Snowflake
SQL
Snowpipe
Streams
Tasks
Dynamic Tables
Stored Procedures

.
├── LICENSE
├── README.md
├── analytics
├── ingestion
├── setup
└── stream&tasks

Project Modules
setup

Contains:

Database creation
Schemas
Warehouses
Roles & Grants
Stages
File formats
ingestion

Handles:

File ingestion
Internal stages
Snowpipe configuration
Loading raw data into Snowflake

Supported formats:

CSV
JSON
Parquet
stream&tasks

Implements:

Streams for CDC (Change Data Capture)
Tasks for automated ELT workflows
Incremental transformations
Scheduled processing
analytics

Contains:

Dynamic Tables
Fact tables
Dimension tables
Sales analytics
Customer LTV models
Key Features
Real-time ingestion with Snowpipe
Incremental ELT processing
Automated workflows
Analytics-ready data models
Scalable Snowflake architecture
Secure and governed data access
Example Workflow
-- Snowpipe auto ingestion
COPY INTO RAW_ORDERS
FROM @RAW_STAGE;

-- Stream captures changes
CREATE STREAM RAW_STREAM ON TABLE RAW_ORDERS;

-- Task automates transformations
CREATE TASK ELT_TASK
AS
CALL SP_REFRESH_FACTS();
Future Improvements
dbt integration
Airflow orchestration
CI/CD pipeline
Data quality framework
External stages with AWS S3
Author

Data Engineering project built using Snowflake to demonstrate modern ELT architecture and real-time analytics pipelines.
