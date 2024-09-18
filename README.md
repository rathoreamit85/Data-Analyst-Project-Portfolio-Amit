
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

This README structure will provide a clear overview of the first part of your AWS project, helping to organize and explain the process of building an ETL pipeline for the Vancouver voting data.

