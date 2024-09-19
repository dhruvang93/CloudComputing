# Issued Building Permits DAP (City of Vancouver - Dhruvang)

## Overview

This project leverages AWS and advanced data analytics tools to analyze and visualize building permit data from the City of Vancouver for the years 2023 and 2024. The objective is to identify trends, implications, and actionable insights that can inform decision-making for stakeholders. By exploring the dynamics of building permits across different property types, neighborhoods, and activity levels, the analysis aims to provide data-driven recommendations to support future urban planning and development initiatives.

## Table of Contents

- [Step 1: Formulate Focused Data Analytical Questions](#step-1-formulate-focused-data-analytical-questions)
- [Step 2: Data Discovery for Issued Building Permits](#step-2-data-discovery-for-issued-building-permits)
- [Step 3: AWS-Based Storage Solution for Issued Building Permits Data](#step-3-aws-based-storage-solution-for-issued-building-permits-data)
- [Step 4: Data Preparation](#step-4-data-preparation)
- [Step 5: Designing a Data Pipeline for Building Permits](#step-5-designing-a-data-pipeline-for-building-permits)
- [Step 6: Implementing the Data Pipeline using AWS Glue](#step-6-implementing-the-data-pipeline-using-aws-glue)
- [Step 7: Data Preparation and Query Execution](#step-7-data-preparation-and-query-execution)
- [Step 8: Data Visualization](#step-8-data-visualization)
- [Step 9: Data Publishing](#step-9-data-publishing)
- [Data Protection](#data-protection)
- [Data Governance](#data-governance)
- [Data Monitoring](#data-monitoring)

## Step 1: Formulate Focused Data Analytical Questions

To guide this analysis, we formulated specific questions related to the 2023 and 2024 building permit datasets:

- **Year-over-Year Trends**: How are the issuance and approval rates of building permits changing from 2023 to 2024?
- **Permit Activity Analysis**: What is the trend for building permits that were approved in 2023 but became inactive in 2024?

![image](https://github.com/user-attachments/assets/9fe01575-f783-4d1c-9cd1-f9c70768d6b9)

---

## Step 2: Data Discovery for Issued Building Permits

In the analysis of issued building permits within the City of Vancouver, datasets for 2023 and 2024 were sourced from the City of Vancouver Open Data Portal in Excel format. The initial phase involved a thorough examination of the dataset structure to familiarize with key fields such as `PermitNumber`, `IssueDate`, `PermitElapsedDays`, `ProjectValue`, `TypeOfWork`, `Address`, `PermitCategory`, `Applicant`, `PropertyUse`, `SpecificUseCategory`, and `GeoLocalArea`. Following this, detailed data profiling was conducted to identify patterns, detect anomalies, and generate descriptive statistics, which provided a comprehensive summary of the building permits data. This profiling was essential for understanding the distribution of project values, types of work, and the timelines for permit issuance.

Additionally, the datasets were scrutinized for any missing or incomplete data, particularly in critical fields like `PermitNumberCreatedDate`, `IssueDate`, and `ApplicantAddress`. This step ensured that any data gaps were identified and managed effectively to maintain the integrity of the analysis. Early insights were gathered during this discovery phase, offering preliminary observations on trends in permit issuance by year, common project types, and the geographic concentration of permits. These insights laid the groundwork for a more detailed and effective analysis in the subsequent stages of the project.

![image](https://github.com/user-attachments/assets/7ac50450-920e-4e78-b632-7a9cf856dc53)

---

## Step 3: AWS-Based Storage Solution for Issued Building Permits Data

To effectively manage the building permits datasets for 2023 and 2024, a robust storage solution was designed using AWS. The Excel files containing the permit data were securely stored in Amazon S3, providing scalable and reliable storage. The datasets were meticulously organized into distinct S3 buckets, separated by the years 2023 and 2024, within dedicated landing zones to streamline access and management.

In addition to storage and organization, stringent security measures were implemented, including access controls and encryption, to safeguard sensitive information. To facilitate accessibility for analysis, AWS Glue and Amazon Athena were employed, enabling the data to be structured, secure, and readily available for processing and analysis. This approach ensured that the building permits data was efficiently stored, well-organized, and maintained to high security standards, supporting seamless analytical workflows.

### PLACEHOLDER FOR "Data Organizing in Landing Zone of S3 Bucket in AWS in Excel Format"

---

## Step 4: Data Preparation

Data transformation was undertaken, including the addition of a new column representing the year, which facilitated comparisons between the 2023 and 2024 datasets. The cleaned and transformed datasets were then securely stored in their respective S3 bucket folders, organized under the "Raw" section for each year. This preparation phase ensured that the building permits data was clean, well-organized, and primed for in-depth analysis, laying a solid foundation for the subsequent stages of the project.


![image](https://github.com/user-attachments/assets/07a1a83e-33f7-414e-bb3b-db408a492471)

---

## Step 5: Designing a Data Pipeline for Building Permits

A data pipeline was designed to efficiently process and load the issued building permits data. The plan mapped the data flow from the Landing S3 bucket to the Curated S3 bucket, detailing the transformation steps, including adding a year column for comparisons and aggregating the data for analysis. AWS Glue was selected for the ETL process, ensuring smooth data transformation and loading. A visual workflow in AWS Glue outlined each stage of the pipeline, establishing a streamlined process ready for implementation.

![image](https://github.com/user-attachments/assets/9c949f6e-f0ea-4500-8be1-59d80efbd483)

---

## Step 6: Implementing the Data Pipeline using AWS Glue

- **Data Sources (AWS S3)**: Datasets for 2023 (`BuildingPermit2023`) and 2024 (`BuildingPermit2024`) are sourced from S3 buckets.
- **Standardization**: Columns such as `TypeOfWork`, `Year`, and `Count of Each Work` are standardized for both datasets.
- **Data Cleaning**: Null or incomplete fields are removed to ensure clean data.
- **Filtering**: Rows are filtered based on schema and standardized criteria, ensuring relevance to the analysis.
- **Merging Datasets**: `BuildingPermit2023` and `BuildingPermit2024` datasets are merged on `TypeOfWork` to create a unified dataset.
- **Final Mapping**: The combined dataset is re-mapped to focus on `TypeOfWork` and `Count of Work` (one column per year) of permits.
- **Aggregation**: Data is aggregated by `TypeOfWork` and `Count of Work`, calculating the total number of permits issued.
- **Output**: The final aggregated dataset is output to an S3 bucket, organized by `TypeOfWork` and `Count of Work` for easy access and analysis.

![image](https://github.com/user-attachments/assets/8b50ce35-c877-43a4-b5da-a62513a3dece)

---

## Step 7: Data Preparation and Query Execution

The process commenced with the creation of external tables in Amazon Athena, which were linked to the curated S3 data on building permits. Using SQL, queries were executed to extract pertinent information from the datasets. This was followed by a thorough data analysis phase:

- **Descriptive Analysis**: Identifying trends and patterns in the aggregated building permit data.
- **Diagnostic Analysis**: Investigating the causes behind observed trends and anomalies.
- **Predictive Analysis**: Forecasting property tax trends into the future.
- **Validation**: Checking the accuracy of query results.
- **Exporting Results**: Important results were exported for visualization.

This step effectively provided valuable insights using the querying power of Athena.

![image](https://github.com/user-attachments/assets/a3906c15-0139-4a1c-9a7e-3db62e43ca01)

---

## Step 8: Data Visualization

### Tool Selection and Chart Generation

Given budget constraints, Excel was chosen for data visualization due to its robust charting capabilities. Various types of charts, including pie, bar, and line charts, were generated to effectively represent the insights derived from the data. These visualizations helped in illustrating different aspects of the building permit data in a clear and comprehensible manner.

### Dashboard Design and Presentation

The generated charts were consolidated into an interactive Excel dashboard, allowing stakeholders to explore the data dynamically. This dashboard was then compiled into a PDF report, providing a structured and actionable presentation of the analysis results. This approach ensured that the findings were accessible and easily interpretable for decision-makers.

![image](https://github.com/user-attachments/assets/48ddb26a-0474-4ec0-8bb2-66820a197bf6)

---

## Step 9: Data Publishing

### Server Setup and Cost Efficiency

To manage costs effectively, a Linux server was utilized for setting up server instances dedicated to storing and publishing results. This approach included a general server instance for holding the processed data and visualizations, and a web server instance for hosting findings via a web interface. Data storage involved uploading datasets and reports to a centralized location, facilitating easy access.

### Web Publishing and Prescriptive Analytics

The published report was made accessible through a browser interface. Additionally, prescriptive analytics were provided to offer recommendations based on the analysis, aiding in informed decision-making. This setup ensured secure storage, efficient publishing, and easy accessibility of the findings.

![image](https://github.com/user-attachments/assets/7f3e0341-e352-4da5-ae79-6c6ab5e8898b)


---

## Data Protection

### Steps Taken for Data Protection

- **KMS Key Setup**: Established a KMS key to encrypt data stored in the main S3 bucket, ensuring all building permit data is encrypted at rest.
- **Backup S3 Bucket**: Created a backup S3 bucket containing a duplicate of the building permit data for high availability and disaster recovery.
- **Replication Rules**: Set up replication rules to securely transfer data from the primary S3 bucket to the backup bucket, using the same KMS key for encryption during the transfer.

![image](https://github.com/user-attachments/assets/a9c8f486-c65c-4334-8874-cf2b0bb74bc0)

![image](https://github.com/user-attachments/assets/509274ab-2dc3-4198-90f8-feefc35dad5f)


---

## Data Governance

A workflow for building permits was developed to enable the data governance process. This process ensures that the output data follows the rules and passes all the quality checks. The ETL pipeline was developed in AWS Glue.

![image](https://github.com/user-attachments/assets/58c32cfb-80c8-4ca9-abde-2fc03ac63718)

Data was checked and cleaned on a daily schedule since new permits are applied daily.

![image](https://github.com/user-attachments/assets/419e3f9b-9c0a-4770-a09d-b3fbffc1bc71)


![image](https://github.com/user-attachments/assets/6da9666b-24ce-4d95-baf4-0ba19374498f)

---

## Data Monitoring

For this part, a dashboard was developed to monitor the objects in S3 buckets and ensure that costs are managed by the billing metric in the dashboard. An alarm was set up to monitor the estimated charges, which will be triggered if billing above $35 occurs in the last 6 hours.

![image](https://github.com/user-attachments/assets/3e388aca-251c-4375-a7e2-f457ac2f6695)


AWS CloudTrail was set up to monitor all the bucket activity and the Glue activity logs.

![image](https://github.com/user-attachments/assets/3b27615c-d012-4b94-8f58-8ef0cce24b30)

```
