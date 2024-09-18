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

![Reference Images] (/screenshots/DRAWIO.png)
