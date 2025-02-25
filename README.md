# HR Employment Analysis Report
![HR0](https://github.com/user-attachments/assets/022e8fe3-6b3a-43a0-b16b-5dc4dc84b1c4)
![HR!](https://github.com/user-attachments/assets/8c68dc5f-6fd8-4d38-9286-3899748c5a02)


## Project Overview

This Data analysis project aims to provide insights into employees age, race, gender, job title, location and the length of employment from 2000 to 2019. By analyzing various aspects, we seek to uncover actionable insights, identify trends, gain a deeper understanding of the employee performance and make data-driven recommendations.

## Data Sources

Human Resource data: The primary dataset used for this analysis is the "human-resourse_csv" file, containing 22000 rows from the year 2000 to 2019.

## Tools

- Data Cleaning & Analysis: MYSQL workbench.
- Data Visualization: Power BI.
  
## Data Cleaning/Preparation

In the initial data preparation phase, we performed the following tasks;
- Data loading and inspection.
- Handling missing and incorrect values.
- Data Cleaning and formatting.
- 
## Exploratory Data Analysis (EDA)

EDA involved exploring the HR dataset and writing SQL queries. 
We created different required columns in the analysis, e.g i^?id to emp_id.
## Data Analysis
Includes some interesting code/features worked with;
```sql
ALTER TABLE hr
CHANGE COLUMN ï»¿id emp_id VARCHAR(20) NULL;

DESCRIBE hr;

ALTER TABLE hr
MODIFY COLUMN birthdate DATE;
SELECT birthdate FROM hr;

UPDATE hr
SET birthdate = CASE
	WHEN birthdate LIKE '%/%' THEN date_format(str_to_date(birthdate,'%m/%d/%Y'), '%Y-%m-%d')
    WHEN birthdate LIKE '%-%' THEN date_format(str_to_date(birthdate,'%m-%d-%Y'), '%Y-%m-%d')
    ELSE NULL
END
;
```

  
## Questions

1. What is the gender breakdown of employees in the company?
2. What is the race/ethnicity breakdown of employees in the company?
3. What is the age distribution of employees in the company?
4. How many employees work at headquarters versus remote locations?
5. What is the average length of employment for employees who have been terminated?
6. How does the gender distribution vary across departments and job titles?
7. What is the distribution of job titles across the company?
8. Which department has the highest turnover rate?
9. What is the distribution of employees across locations by state?
10. How has the company's employee count changed over time based on hire and term dates?
11. What is the tenure distribution for each department?

## Findings

- The youngest employee is 20 years and the oldest is 57 years.
- A large number of employees work at the headquarters versus remotely.
- The gender distribution across departments is balanced.
- A large number of employees reside in Ohio.
- There are more male employees.
- The white people are more dominant as compared to other races.
- The net change in employees has increased over the years.

## Limitations

- Some termdates were far into the future and were not used in the analysis. The termdates were those that are equal to or less than the current date.
- Some records had negative ages and therefore were excluded from our analysis. Ages 18 years and above were the ones used.












































































































































