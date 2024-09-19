# Cloud Computing Portfolio

This repository contains two key projects focused on data analysis and ETL processes using AWS services. Both projects demonstrate various stages of data extraction, transformation, and loading (ETL), data governance, and the use of visualization tools. The first project deals with the building permits data of the City of Vancouver, while the second project involves analyzing conflict resolution data within the HR department.

---

## Project 1: DAP for Issued Building Permits (City of Vancouver)

### Description

The **DAP for Issued Building Permits** project leverages AWS and advanced data analytics tools to analyze and visualize building permit data from the City of Vancouver for the years 2023 and 2024. The objective is to identify trends, implications, and actionable insights that can inform decision-making for stakeholders. By exploring the dynamics of building permits across different property types, neighborhoods, and activity levels, the analysis aims to provide data-driven recommendations to support future urban planning and development initiatives.

### Key Features:

- **Data Source:** City of Vancouver Building Permit Data (2023-2024)
- **ETL Process:** AWS Glue for transformation, Amazon Athena for querying, and S3 for data storage
- **Data Governance:** KMS encryption, scheduled data quality checks, workflow automation
- **Tools Used:** AWS Glue, Amazon Athena, Amazon S3, EC2
- **Visualization:** Excel visualizations deployed through an EC2 instance web server

### Project Highlights:

- Created an ETL pipeline using AWS Glue for cleaning and transforming building permit data.
- Implemented security strategies like KMS encryption and S3 bucket policies.
- Automated workflow processes and set replication rules for efficient data management.
- Performed data querying using Amazon Athena and visualized insights using Excel.

[Link to Project 1](./City%20of%20Vancouver%20DAP/)

---

## Project 2: HR Policy of Conflict Resolution Analysis

### Description

The **HR Policy of Conflict Resolution** project focuses on analyzing conflict resolution data within the HR department. The main goal is to find approved and solved conflicts, providing insights that can help improve HR policies and procedures related to conflict resolution. By leveraging AWS services and data visualization tools, the project provides actionable insights to enhance HR policies and conflict management procedures.

### Key Features:

- **Data Source:** Conflict resolution data from the HR department
- **ETL Process:** AWS Glue for data transformation, Amazon Athena for querying, and S3 for data storage
- **Data Governance:** KMS encryption, scheduled data quality checks, workflow automation
- **Tools Used:** AWS Glue, Amazon Athena, Amazon S3, EC2
- **Visualization:** Excel dashboards showcasing conflict resolution statistics

### Project Highlights:

- Implemented an ETL pipeline using AWS Glue for processing conflict resolution data.
- Utilized Amazon Athena for data querying and analysis.
- Ensured data security with KMS encryption and S3 bucket policies.
- Developed interactive dashboards in Excel to visualize conflict resolution trends.

[Link to Project 2](./UCW%20HR%20Policy%20Project/)


