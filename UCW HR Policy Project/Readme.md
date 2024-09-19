# Project Title: HR Policy of Conflict Resolution Analysis

## Objective

The objective of this project is to analyze and manage conflict resolution data within the HR department. The main goal is to find approved and solved conflicts, providing insights that can help improve HR policies and procedures related to conflict resolution.

![Project Diagram](https://github.com/user-attachments/assets/e418948a-6b8c-47e6-9ae6-9d9b6a731055)

## Dataset

**Source:** Conflict resolution datasets were collected from the HR department's internal systems.

**Fields:**

- **Employee IDs:** Unique identifiers for staff involved in conflicts.
- **Conflict Types:** Categories of conflicts (e.g., interpersonal, procedural).
- **Resolution Status:** Whether conflicts were resolved or pending.
- **Approval Status:** Approval of conflict resolution procedures by HR managers.
- **Resolution Dates:** Dates when conflicts were resolved.

![Data Collection](https://github.com/user-attachments/assets/0beb74e8-744a-4103-88d0-950283f16fbd)

## Methodology

### 1. Data Collection and Storage

**Data Acquisition:**

- Conflict resolution data was collected from HR's internal case management systems.

**Storage Solution:**

- The dataset was uploaded and stored in AWS S3.
- Data was organized into S3 landing zones, categorized by year and conflict type.
- **Security:** AWS KMS encryption was applied to protect sensitive employee data.

### 2. Data Cleaning and Transformation

**Data Preparation Using AWS Glue DataBrew:**

- Standardized fields such as Employee IDs, Conflict Types, and Resolution Status.
- Added a "Year" column to facilitate annual analysis.
- Cleaned data was stored in the Raw S3 bucket.

![Data Cleaning](https://github.com/user-attachments/assets/eae7689c-1816-478b-a2dc-194c0f83cad3)

### 3. ETL Pipeline Design

**ETL Pipeline Design:**

- Designed an ETL pipeline using Draw.io to map data flow from the Landing S3 bucket to the Curated S3 bucket.
- Key transformations included renaming columns for consistency, filtering out irrelevant data, and aggregating conflict resolution data.

![ETL Pipeline](https://github.com/user-attachments/assets/103cb2e6-3082-4950-aad6-40f312c2df10)

**ETL Implementation Using AWS Glue:**

- Implemented the ETL pipeline in AWS Glue to extract, transform, and load data.
- Automated processes ensured data was up-to-date and accurate.

![AWS Glue ETL](https://github.com/user-attachments/assets/317d8350-5361-4169-bd4c-2d9f33e753f0)

### 4. Data Analysis

**Amazon Athena for Querying Data:**

- Created external tables in Amazon Athena linked to the curated S3 data.
- Used SQL queries to organize and retrieve data for analysis.

![Amazon Athena](https://github.com/user-attachments/assets/51e20f50-b23f-4af9-bb3e-7a420afbaeaf)

**Data Analysis:**

- Excel was used for in-depth analysis of conflict resolution trends.
- Identified patterns in conflict types, resolution rates, and departmental differences.

### 5. Data Protection and Governance

**Data Encryption:**

- Utilized AWS KMS keys to encrypt all data stored in S3 buckets.

**Backup and Replication:**

- Created a backup S3 bucket for data redundancy.
- Applied replication rules to securely transfer data between primary and backup buckets with encryption.

**Automated Data Governance:**

- Employed AWS Glue for regular data quality checks.
- Scheduled automation processes to maintain data integrity.

![Data Governance](https://github.com/user-attachments/assets/0dcd5244-ca8d-45f1-8f55-ee561bbcb3f1)

### 6. Data Monitoring

- **Amazon CloudWatch:** Monitored resource usage and cost estimations.
- **AWS CloudTrail:** Tracked user activities and API calls, storing logs in S3 for auditing.

![Data Monitoring](https://github.com/user-attachments/assets/651e7053-9b4d-448e-936c-3d7645c8e6ac)

### 7. Data Visualization

**Visualization Tools:**

- Created interactive charts and graphs using Excel.
- Developed dashboards to present insights on conflict resolution trends and statistics.

![Data Visualization](https://github.com/user-attachments/assets/cd5c3b26-f349-4cfe-b7ff-4ac79ed6a616)

### 8. Data Publishing

**Server Setup:**

- Configured AWS EC2 instances to host and publish processed data and visualizations.
- Provided stakeholders with web access to reports and dashboards.

![EC2 Instances](https://github.com/user-attachments/assets/9d2b5fab-9866-40d8-9d46-36a71be9a904)

**Data Storage:**

- Uploaded transformed data and reports to remote access points for easy sharing.

## Tools and Technologies

**AWS Services:**

- **S3:** Data storage and management.
- **AWS Glue:** Data cleaning, transformation, and ETL implementation.
- **Amazon Athena:** SQL querying for data retrieval.
- **Amazon CloudWatch:** System monitoring.
- **AWS CloudTrail:** User activity tracking.
- **AWS KMS:** Data encryption.
- **EC2 Instances:** Hosting and publishing reports.

**Data Visualization:**

- **Excel:** Chart creation and dashboard development.
- **Draw.io:** ETL pipeline visualization.

## Deliverables

- An automated ETL pipeline using AWS Glue.
- Interactive Excel dashboards showcasing conflict resolution statistics.
- Web-accessible reports hosted on AWS EC2 instances.
- Comprehensive analysis report with insights on approved and solved conflicts.

## Outcomes and Insights

1. **Conflict Resolution Rates:** Identified the percentage of conflicts that were resolved versus those pending.
2. **Approval Process Efficiency:** Analyzed the time taken for conflict resolution approvals and suggested improvements.
3. **Common Conflict Types:** Determined the most frequent types of conflicts within the organization.
4. **Departmental Analysis:** Provided insights into which departments had higher rates of conflicts and resolutions.
5. **Policy Recommendations:** Offered data-driven suggestions to enhance the HR conflict resolution policy.

## Conclusion

This project successfully analyzed the HR conflict resolution data, focusing on approved and solved conflicts. By leveraging AWS services and data visualization tools, we provided actionable insights to improve HR policies and conflict management procedures. The findings will assist the HR department in enhancing employee relations and fostering a more collaborative work environment.
