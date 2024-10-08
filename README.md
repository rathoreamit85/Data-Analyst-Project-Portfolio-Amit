# Data-Analyst-Project-Portfolio-Amit

## Project 1 Descriptive Analysis
### Project Title: Management of External Research Funding: Data Cleansing and Structuring for Material Pending Requests
#### Objective:
The primary goal of this project is to cleanse, structure, and prepare a dataset related to external research funding requests in an academic setting. The project focuses on ensuring data quality and structuring it for future analyses, such as funding trend analysis based on time and departmental allocation. This project aims to improve data accuracy for operational decision-making regarding funding management.
#### Dataset:
The dataset includes operational data on material pending requests for external research funding, with the following key features:
- Application ID: A unique identifier for each funding request.
- Applicant Name: The individual or team submitting the request.
- Department: The academic department seeking the funding.
- Submission Date: The date when the application was submitted.
- Funding Amount Requested: The total requested amount in the application.
- Funding Type: The category of the requested funding (e.g., research grant, scholarship).
- Application Status: The current status of the application (e.g., pending, approved, rejected).
- Review Deadline: The deadline for reviewing the application.
- Reviewer Assigned: The individual assigned to review the application.
- Notes: Any additional remarks or comments related to the request.
#### Methodology:
##### 1.	Data Collection and Preparation:
- The raw dataset is stored in the "landing" folder in an AWS S3 bucket.
- AWS Glue DataBrew is used for data cleansing, which includes handling missing values, checking for incorrect data types, and removing null entries from critical columns.

##### 2.	Data Cleaning and Structuring:
- Clean the dataset by identifying and addressing:
- Missing or null values in key fields (e.g., "Application ID", "Funding Amount").
- Inconsistencies in the formatting of date fields such as "Submission Date" and "Review Deadline".
- Addition of a "Year" column based on the "Submission Date" to enable year-wise data analysis.
- After the data cleansing, the structured dataset is stored in the "raw" folder in S3 for further analysis and reporting.

##### 3.	Descriptive Statistics:
- Calculate summary statistics for key variables, including:
- Total number of applications submitted.
- Average funding amount requested per application.
- Distribution of applications by department and funding type.
- Status of applications (e.g., percentage of pending, approved, and rejected applications).
Year-based analysis using the newly added "Year" column to track trends in funding requests over time.

##### 4.	Data Visualization:
- Create visual representations to present findings:
- Bar charts showing the distribution of applications by department.
- Pie charts depicting the status of applications (pending, approved, rejected).
- Line charts displaying the number of funding requests submitted over time, broken down by year.
  Graphs showing the trends in requested funding amounts across departments.

##### 5.	Insights and Findings:
- Key insights derived from the analysis include:
- Peak submission periods for funding requests (e.g., end of academic terms or grant deadlines).
- Departments requesting the highest and lowest funding.
- Common application statuses and trends over the past few years.
  The typical funding amounts requested by various departments and funding types.

##### 6.	Recommendations:
- Based on the findings, the following recommendations are provided:
- Implement stricter application deadlines to prevent an overload of submissions near the end of the review period.
- Allocate more resources to departments with a higher volume of funding requests to ensure timely review.
  Improve the application process for departments with consistently rejected applications to increase success rates.

##### Tools and Technologies:
- AWS S3 for data storage.
- AWS Glue DataBrew for data cleansing and transformation.
- Excel for calculating descriptive statistics and creating visualizations.

##### Deliverables:
- A detailed report summarizing the data preparation, findings, and recommendations for improving research funding management.
- Visualizations and dashboards displaying key trends and insights.
- A presentation for stakeholders, highlighting the primary outcomes and actionable insights for process optimization.

This descriptive analysis project provides a structured understanding of external research funding requests, enabling the academic institution to optimize its funding allocation processes and improve overall efficiency.

#### Screenshots for Refernce:
- Goal to achieve and the results to achieve
![Goal to achieve and the results to achieve](Goal and Results required.png)

- Draw IO Chart for AWS services used for this project
![Draw IO Chart for AWS services used for this project](DRAWIO.png)

- Data cleaning and Structuring using AWS Glue Data Brew
![Data cleaning and Structuring using AWS Glue Data Brew](Cleaning and Structuring.png)

# Project 2  Exploratory Data Analysis on External Research Funding Requests

## Project Title: Managing External Research Funding: An Exploratory Data Analysis on Material Pending Requests

### Objective:
The goal of this project is to analyze pending research funding requests over multiple years at University Canada West (UCW). By exploring key features from the dataset such as application status, funding amount, and submission deadlines, we aim to provide insights that will streamline the external research funding management process.

### Dataset:
This dataset is clean and structured after using Glue Dtaabrew services The dataset includes information on material pending research funding requests, with the following key columns:

- Application ID: Unique identifier for each funding request.
- Applicant Name: Name of the individual applying for funding.
- Department: The department responsible for the funding request.
- Submission Date: The date the application was submitted.
- Funding Amount Requested: The total amount of funding requested.
- Funding Type: Type of funding (e.g., Grant, Fellowship).
- Application Status: Current status (e.g., Pending, Approved, Rejected).
- Review Deadline: The deadline for the funding request review.
- Reviewer Assigned: Reviewer responsible for evaluating the request.
- Notes: Additional comments or context on the funding request.

### Methodology:
#### Data Pipeline Creation (AWS Glue):
- Here we get a curated dataset which is required for analysis in our case only two columns year and Percentage of pending applications. 
- Data Collection: Load the raw dataset containing material pending requests from the UCW data storage.
- Data Cleaning: Use schema changes to modify column types, drop unnecessary columns, and rename them for consistency.
- Feature Engineering: Apply aggregation functions to calculate the percentage of material pending requests per year.
- Joining Datasets: Perform joins between multiple datasets to combine related information on funding requests, such as applicant demographics and departmental details.
- Data Aggregation and Schema Transformation:
- Column Management: Use AWS Glue’s schema features to drop irrelevant columns (e.g., "Notes") and restructure the data for consistency.
- Aggregate Calculations: Calculate the percentage of records submitted each year based on the Submission Date field.
- Use an aggregation function to count the number of requests per year and compute the percentage share of the total.

#### Exploratory Data Analysis (AWS Athena):
- Query the dataset using Athena to generate yearly statistics.
- Perform calculations to find the proportion of applications submitted each year.
- Analyze trends in funding requests, including changes in funding types or amounts requested over time.

#### Data Joins and Analysis:
- Join datasets to enrich analysis, combining research funding requests with additional data like departmental budget allocations or previous funding success rates.
- Results Publishing:
- The results, including trends in submission rates and funding allocations, are published on both local and web servers for easy access by stakeholders.
- Insights and Findings:
- Key insights will include the percentage of pending requests each year, trends in funding requests by department, and the impact of funding types on request approval rates.
- Identification of departments with the highest volume of pending requests, enabling more efficient allocation of resources for review.

#### Conclusion:
The project helps UCW's external research funding management team streamline the request review process by identifying high-priority areas and optimizing the review workload. Further analysis can focus on improving approval times or predicting the likelihood of request approval.

#### Tools and Technologies:
- AWS Glue: For managing ETL (Extract, Transform, Load) processes, schema changes, and data transformations.
- AWS Athena: To run SQL queries and perform percentage calculations and aggregations.
- Excel: For additional data manipulation and analysis.
- Web Servers: For publishing the results of the analysis for access by UCW stakeholders.

#### Deliverables:
- A well-documented Jupyter Notebook covering the entire data pipeline, cleaning, analysis, and visualization process.
- Cleaned and structured datasets, including the percentage of pending records per year.
- A final report summarizing the key insights from the EDA and suggestions for improving the management of external research funding requests.

#### Screenshot for reference related to Project 2:

- Draw IO for Project 2
![Draw IO for Project 2](Draw IO for Project 2.png)

- Draw IO flow chart explains the steps performed in pipeline to achieve specific results step by step
![Draw IO flow chart explains the steps performed in pipeline to achieve specific results step by step](Draw IO Pipeline result structure design.png)

- AWS Pipeline creation using AWS Glue and store results in Curated Folder
![AWS Pipeline creation using AWS Glue](AWS Glue Pipeline.png)
  

# Project 3: AWS Data Analytic Platform for Vancouver Voting Results

## Project Title: Building an AWS ETL Pipeline for Council Voting Data

### Objective:
The goal of this project is to create an end-to-end AWS ETL pipeline to analyze council voting results for 2023 and 2024. This project focuses on creating a clean, structured dataset to calculate voting percentages and compare the results across both years, facilitating decision-making for the Vancouver City Council.

### Dataset:
Data used in this project is sourced from the Open Data Vancouver website. Key features of the dataset include:
- Vote Year: The year the vote took place.
- Vote Results: Votes in favor, opposition, and absent members.
- Total Votes: Total number of votes cast in each council decision.

### Methodology:

##### 1.	Data Storage Setup:
- Created three folders in AWS S3:
- Landing Folder: Raw datasets from 2023 and 2024.
- Raw Folder: Data after initial cleaning.
- Curated Folder: Final structured dataset for analysis.

##### 2.	Data Pipeline Creation (AWS Glue):
- Created Glue DataBrew projects to handle ETL (Extract, Transform, Load) operations.
- Two projects were created:
- project-counvot-2023
- project-counvot-2024
- Jobs were created for each year’s data to clean, transform, and load the results.
  
##### 3.	ETL Pipeline Design:
- Extract: Raw datasets for 2023 and 2024 were ingested into AWS S3.
- Transform: Applied the following transformations:
- Schema change to remove unnecessary columns and rename key columns.
- Aggregate function to group votes by year and count votes in favor, opposition, and absent members.
- Join datasets for 2023 and 2024 to calculate the overall percentage of votes in favor and opposition.
- Derived new fields to calculate voting percentages.
- Load: Transferred the final, clean dataset to the Curated folder for analysis.

##### 4.	Data Analysis (AWS Athena):
- Created tables for 2023 and 2024 data in Athena.
- Queried and compared voting results, calculating the percentage of votes in favor and opposition for each year.

### Tools and Technologies:
- AWS Glue: For building the ETL pipeline.
- AWS S3: For data storage.
- AWS Athena: For querying and analyzing data.
- Excel: For basic data visualization due to AWS student account limitations.

### Deliverables:
•	Cleaned and structured datasets for 2023 and 2024 voting data.
•	A fully functional AWS Glue pipeline to handle ETL operations.
•	A detailed report of voting percentages for both years.
•	Visualizations generated in Excel to show the trends in council voting.

This Project structure will provide a clear overview of the first part of your AWS project, helping to organize and explain the process of building an ETL pipeline for the Vancouver voting data.

#### Screenshots for Third Project Refernce:

- Draw IO DAP for Project 3
![Draw IO DAP for Project 3](Draw IO DAP for Project 3.png)
- Description Of dataset
![Description Of dataset](Description Of dataset.png)
- Dataset Exported for 2024 and 2023
![Dataset Exported for 2024 and 2023](Dataset Exported for 2024 and 2023.png)
- Folder Creation in S3
![Folder Creation in S3](Folder Creation in S3.png)
- Landing Dataset
![Landing Dataset](Landing Dataset.png)
- Cleaning from AWS Data Brew Service
![Cleaning from AWS Data Brew Service](Cleaning.png)
- Structuring from AWS Data Brew Service
![Structuring from AWS Data Brew Service](Structuring.png)
- Pipeline steps to reach the required dataset to analyze
![Pipeline steps to reach required dataset to analyze](Pipeline steps to reach required dataset to analyze.png)
- Run Pipeline job to store dataset in Curated Folder
![Run Pipeline job to store dataset in Curated Folder](Run Pipeline job to store dataset in Curated Folder.png)
- Created Tables  to analyze datasets from
![Created Tables  to analyze dataset from](Created Tables to analyze dataset from.png)
- Athena Analysis Script and Results
![Athena Analysis Script and Results](Athena Analysis Script and Results.png)
- Excel Chart Analysis
![Excel Chart Analysis](Excel Chart Analysis.png)
- WEB Publishing Analyzed Results
![WEB Publishing Analyzed Results](WEB Publishing Analyzed Results.png)

# Project 4: Data Protection, Governance, and Monitoring

## Project Title: Data Protection, Governance, and Monitoring for AWS-Based Council Voting Analytics

#### Introduction
This project aims to ensure data protection, governance, and monitoring of datasets used for analyzing voting results of the City of Vancouver for the years 2023 and 2024. These datasets have been ingested and processed using various AWS services (S3, Glue, Athena) in the first part of the project.

#### Dataset Overview
•	Project 1 Dataset: Vancouver City Council Voting Results for 2023 and 2024.
•	Purpose: Analyze voting percentages in favor or opposition over both years for decision-making support.
•	Data Size: 200 records for both years.

#### Data Protection
Data protection involves securing sensitive information and ensuring its availability and confidentiality.
-	KMS (Key Management Service):
-	Create and assign an encryption key to the S3 bucket holding the dataset.
-	Key Name: project-counvot-key-amit.
-	This encryption ensures that only authorized users can access the dataset.
-	Backup Strategy:
-	Backup the S3 bucket containing the dataset to another S3 bucket.
-	Enable versioning in the S3 bucket to keep track of changes, ensuring the ability to restore previous versions in case of data loss.
-	Replication:
-	Set up replication from the main S3 bucket to the backup bucket to ensure data redundancy.

#### Data Governance
Governance ensures data integrity, accountability, and management across its lifecycle.
-	Creating a Trusted Folder:
-	Establish a separate, controlled folder for critical datasets with specific access policies to ensure only authorized users can modify or access the data.
-	Workflow: Automate governance processes by setting up a schedule to move and process data periodically.
-	Workflow Name: project-group5-workflow-amit.
-	Trigger: Runs every Sunday at 23:59 to ensure data is processed and governed regularly.

#### Data Monitoring
Monitoring is critical for tracking the health and usage of datasets.
-	CloudWatch:
-	Create a CloudWatch dashboard to monitor S3 usage and billing.
-	Dashboard Name: project-group5-dashboard-amit.
-	Include widgets that display the estimated billing and storage usage of the S3 buckets.
- Alerting: Create an alarm to notify if costs exceed a defined threshold (e.g., $38).
- Automation & Alerts:
- Set up CloudFormation scripts to automate resource provisioning and CloudWatch alerts. This will minimize manual interventions and enhance data protection efforts.

#### Conclusion
By implementing the above data protection, governance, and monitoring processes, the datasets used in this project are secured and managed effectively. The monitoring setup ensures proactive tracking of usage and potential issues, while backup and governance workflows guarantee the data remains available and trusted.

#### Screenshots for Project 4 for Reference of work done:

- Draw IO for Project 4
![Draw IO for Project 4.png](Draw IO for Project 4.png)
- Key Created using KMS
![Key Created using KMS](KMS Key Created.png)
- Encrypting Bucket with Key
![Encrypting Bucket with Key](Encrypting Bucket with Key.png)
- Rule Creation for Backup automation under the management tab for a bucket in S3
![Rule Creation for Backup automation under management tab for bucket in S3](Rule Creation for Backup automation.png)
- Data Quality Data Protection Pipeline
![Data Quality Data Protection Pipeline](DQDP Pipeline.png)
- Dashboard Created for Cost Estimation
![Dashboard Created for Cost Estimation](Dashboard Created for Cost Estimation.png)
- Alarm Creation to schedule
![Alarm Creation to schedule](Alarm Creation to schedule.png)
- Weekly scheduling for workflow firing
![Weekly scheduling for workflow firing](Weekly scheduling for workflow firing.png)
