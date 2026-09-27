# Data Analyst Job Market Analysis Using SQL

An exploratory analysis of 787,686 job postings using PostgreSQL and SQL to investigate job demand, salaries, skills, remote work, geography, and hiring trends.

![PostgreSQL](https://img.shields.io/badge/Database-PostgreSQL-336791)
![SQL](https://img.shields.io/badge/Language-SQL-blue)
![Status](https://img.shields.io/badge/Project-Completed-success)

## Table of Contents

- [Why This Project Matters](#why-this-project-matters)
- [Project Objective](#project-objective)
- [Business Questions](#business-questions)
- [Dataset](#dataset)
- [Database Design](#database-design)
- [Tools and Technologies](#tools-and-technologies)
- [Project Workflow](#project-workflow)
- [SQL Queries](#sql-queries)
- [Exploratory Data Analysis](#exploratory-data-analysis)
  - [1. Job Category Demand](#1-job-category-demand)
  - [2. Salary by Job Category](#2-salary-by-job-category)
  - [3. Highest Individual Salaries](#3-highest-individual-salaries)
  - [4. Most In-Demand Skills](#4-most-in-demand-skills)
  - [5. Most In-Demand Data Analyst Skills](#5-most-in-demand-data-analyst-skills)
  - [6. Skills and Salary](#6-skills-and-salary)
  - [7. Company Analysis](#7-company-analysis)
  - [8. Geographic Distribution](#8-geographic-distribution)
  - [9. Remote Work](#9-remote-work)
  - [10. Remote vs Non-Remote Salary](#10-remote-vs-non-remote-salary)
  - [11. Monthly Job Demand](#11-monthly-job-demand)
  - [12. Monthly Salary Trend](#12-monthly-salary-trend)
- [Key Findings](#key-findings)
- [Career Insights](#career-insights)
- [Recommendations](#recommendations)
- [Limitations](#limitations)
- [Conclusion](#conclusion)
- [Dashboard](#dashboard)
- [Skills Demonstrated](#skills-demonstrated)
- [Portfolio Summary](#portfolio-summary)
- [Contact / Portfolio](#contact--portfolio)

A portfolio-ready SQL project analyzing the Data Analyst job market using PostgreSQL. This project examines hiring demand, salaries, skill requirements, geographic distribution, remote work patterns, and hiring trends across a large dataset of job postings.

## Why This Project Matters

The Data Analyst role sits at the intersection of business, technology, and decision-making. This project explores how SQL can be used to turn a large relational dataset into evidence-based insights for career planning, hiring strategy, and market analysis.

By combining job-posting data with skill, company, and geographic information, the analysis answers practical questions such as:

- Which roles are growing fastest?
- Which skills are most in demand for Data Analysts?
- Where are the strongest opportunities located?
- How do salaries vary by country, role, and work arrangement?
- What trends can be seen over time?

## Project Objective

The primary objective of this project is to use SQL to investigate the Data Analyst job market and answer business and career-focused questions related to:

- Job demand
- Salary levels
- Required technical skills
- Companies hiring Data Analysts
- Geographic distribution
- Remote opportunities
- Salary differences by work arrangement
- Monthly hiring trends
- Skills associated with higher pay

## Business Questions

This project addresses the following questions:

1. Which job categories have the highest demand?
2. Which job categories have the highest median salaries?
3. What are the highest-paying individual job postings?
4. Which skills are most frequently requested?
5. Which skills are most frequently requested for Data Analyst positions?
6. Which Data Analyst skills are associated with higher salaries?
7. Which companies have the most Data Analyst postings?
8. Which countries have the most Data Analyst opportunities?
9. Which countries have the highest proportion of remote Data Analyst postings?
10. How do remote and non-remote Data Analyst salaries compare?
11. How does Data Analyst job demand change over time?
12. How does Data Analyst salary change over time?

## Dataset

The analysis uses a relational dataset containing job postings and supporting dimension tables.

| Table | Purpose |
| --- | --- |
| `job_postings_fact` | Main job-posting information |
| `company_dim` | Company information |
| `skills_dim` | Skill information |
| `skills_job_dim` | Relationship between jobs and skills |

### Dataset Size

| Table | Records |
| --- | ---: |
| `job_postings_fact` | 787,686 |
| `company_dim` | 140,033 |
| `skills_dim` | 259 |
| `skills_job_dim` | 3,669,604 |

The `skills_job_dim` table acts as a bridge table because a single job can require multiple skills, and a single skill can appear in many job postings.

## Database Design

The dataset uses a normalized relational design based on fact and dimension tables.

```text
company_dim
    ↓
job_postings_fact
    ↓
skills_job_dim
    ↓
skills_dim
```

Primary and foreign keys are used to maintain integrity across the dataset. This structure enables analyses such as:

- Which skills are required for Data Analyst jobs?
- What salaries are associated with those jobs?
- How do skill requirements vary by country or work arrangement?

## Tools and Technologies

### Database
- PostgreSQL

### Query Language
- SQL

### Command-line Interface
- psql

### Operating Environment
- Windows PowerShell

### SQL Techniques Used
- `SELECT`
- `WHERE`
- `GROUP BY`
- `ORDER BY`
- `LIMIT`
- `COUNT`
- `AVG`
- `ROUND`
- `HAVING`
- `INNER JOIN`
- `PERCENTILE_CONT`
- `DATE_TRUNC`
- `STRING_AGG`
- Conditional aggregation
- Filtering
- Data validation

## Project Workflow

This project follows a structured SQL-driven workflow:

1. Load raw job data into PostgreSQL
2. Validate table relationships and data quality
3. Filter to Data Analyst-related postings
4. Aggregate demand, salaries, and skills
5. Join job, company, and skill tables for deeper context
6. Analyze trends by month, country, skill, and work arrangement
7. Summarize findings and recommendations

## SQL Queries

Each analysis in this project is stored in a dedicated SQL file. The queries below map directly to the findings presented in this README:

- [1 Highest-paying data jobs](1%20Highest-paying%20data%20jobs)
- [2 Remote job opportunities](2%20Remote%20job%20opportunities)
- [3 Salaries trend over time](3%20Salaries%20trend%20over%20time)
- [4 Remote data analyst jobs by country](4%20Remote%20data%20analyst%20jobs%20by%20country)
- [5 Companies with highest data analyst salaries](5%20Companies%20with%20highest%20data%20analyst%20salaries)
- [6 Most in-demand skills for data analysts and their salaries](6%20Most%20in-demand%20skills%20for%20data%20analysts%20and%20their%20salaries)
- [7 Highest-paying data analyst jobs and their skills](7%20Highest-paying%20data%20analyst%20jobs%20and%20their%20skills)

## Exploratory Data Analysis

### 1. Job Category Demand

The largest job categories were:

- Data Analyst — 196,593
- Data Engineer — 186,679
- Data Scientist — 172,726
- Business Analyst — 49,160
- Software Engineer — 45,019

This highlights strong demand across analytics and data-focused roles.

### 2. Salary by Job Category

Median annual salaries included:

| Job Category | Median Salary |
| --- | --- |
| Senior Data Scientist | $155,000 |
| Senior Data Engineer | $147,500 |
| Data Scientist | $127,500 |
| Data Engineer | $125,000 |
| Senior Data Analyst | $111,175 |
| Machine Learning Engineer | $106,000 |
| Software Engineer | $99,150 |
| Data Analyst | $90,000 |
| Cloud Engineer | $90,000 |
| Business Analyst | $85,000 |

![1 Median salary by job category](C:\Users\JONGOMEDZI\Sql Project Data Job Analysis\project_sql\assets\1 Median salary by job category.png)

Only postings with annual salary information were included in this analysis.

### 3. Highest Individual Salaries

The analysis identified several unusually high-paying job postings, including senior Data Scientist, Data Analyst, and analytics leadership positions. These extremes illustrate why median salary is a more informative summary than average salary alone in a skewed distribution.

### 4. Most In-Demand Skills

Across the overall dataset, the most common skills included:

1. SQL
2. Python
3. AWS
4. Azure
5. R
6. Tableau
7. Excel
8. Spark
9. Power BI
10. Java

SQL and Python were particularly prominent across the wider job market.

### 5. Most In-Demand Data Analyst Skills

The leading Data Analyst skills were:

1. SQL
2. Excel
3. Python
4. Tableau
5. Power BI
6. R
7. SAS
8. PowerPoint
9. Word
10. SAP

SQL appeared in approximately 92,628 Data Analyst postings.

### 6. Skills and Salary

When Data Analyst skills were compared using postings with salary information, some less frequently requested technologies showed relatively high median salaries. In general:

- SQL had the greatest demand
- Python was associated with higher salaries than SQL in many comparisons
- Tableau and R also showed substantial demand
- Cloud and data-platform technologies were less common but sometimes showed elevated salary associations

These are associations, not causal effects. Salary can also reflect seniority, company, location, industry, and job responsibilities.

### 7. Company Analysis

Companies and organizations with large numbers of Data Analyst postings included:

- Emprego
- Robert Half
- Insight Global
- Citi
- Dice
- UnitedHealth Group
- Confidenziale
- Get It Recruit - Information Technology
- Michael Page
- Randstad

These figures represent job postings associated with company names in the dataset and should not be interpreted as employee counts or unique vacancies.

### 8. Geographic Distribution

The United States had the largest number of Data Analyst postings, followed by several European and Asian markets.

| Country | Data Analyst Postings |
| --- | ---: |
| United States | 67,956 |
| France | 13,855 |
| United Kingdom | 10,509 |
| Germany | 7,141 |
| Singapore | 6,642 |
| India | 6,133 |
| Spain | 5,182 |
| Philippines | 4,770 |
| Italy | 4,570 |
| Netherlands | 4,126 |

### 9. Remote Work

Remote Data Analyst postings were found across many countries. Among countries with at least 500 Data Analyst postings, the share marked as remote varied considerably.

Examples:

- Brazil — 24.34%
- Canada — 21.28%
- India — 17.12%
- Sudan — 15.84%
- Romania — 14.29%
- Philippines — 12.70%
- United Kingdom — 9.06%
- United States — 7.51%

These percentages describe the dataset and should not be interpreted as national workforce-wide remote work rates.

### 10. Remote vs Non-Remote Salary

For Data Analyst postings containing salary information:

| Work Arrangement | Average Salary | Median Salary |
| --- | ---: | ---: |
| Remote | $94,770 | $87,250 |
| Non-remote | $93,765 | $90,000 |

The average and median produced different comparisons, reinforcing the importance of using multiple salary measures when reviewing salary distributions.

### 11. Monthly Job Demand

Data Analyst job-posting volume varied throughout 2023.

- Highest observed monthly volume: January 2023 — 23,697 postings
- Lowest complete month in the main 2023 period: May 2023 — 13,457 postings
- December 2022 had only 485 Data Analyst postings and was treated as a partial-data period rather than a complete month for comparison

### 12. Monthly Salary Trend

Salary levels were generally strongest around July and August 2023. The median salary reached approximately:

- $95,000 in July and August 2023

Later months showed lower median salary levels. December 2022 had only six salary observations and was not suitable for meaningful trend comparison.

## Key Findings

The analysis produced several important conclusions:

### Finding 1 — Strong Data Analyst Demand
Data Analyst was one of the largest job categories in the dataset, with approximately 196,593 postings.

### Finding 2 — SQL Is Central to Data Analyst Roles
SQL was the most frequently requested Data Analyst skill.

### Finding 3 — Skill Demand and Salary Do Not Always Align
Some highly demanded skills had lower median salaries than less frequently requested technologies.

### Finding 4 — Geography Matters
Data Analyst opportunities varied substantially by country.

### Finding 5 — Remote Opportunities Vary Widely
Remote-work availability differed considerably across countries.

### Finding 6 — Salary Measures Tell Different Stories
Average and median salary comparisons can produce different conclusions, especially when salary distributions include high-value observations.

### Finding 7 — Hiring Demand Changes Over Time
The number of Data Analyst postings varied considerably across months.

## Career Insights

The findings suggest several practical areas for Data Analyst skill development.

A strong progression is:

SQL → Excel → Python → Power BI/Tableau → Statistics → Business Communication

- SQL provides a foundation for querying and transforming data
- Python extends analytical and automation capabilities
- Excel remains valuable for business analysis and spreadsheet workflows
- Power BI and Tableau support dashboarding and data storytelling
- Business communication is essential for turning analysis into decisions

## Recommendations

### For Aspiring Data Analysts
- Develop strong SQL skills
- Learn Python for data analysis and automation
- Become proficient in Excel
- Learn at least one business intelligence or visualization platform
- Develop statistical and analytical thinking
- Build portfolio projects that demonstrate SQL and business analysis
- Practice translating technical findings into business language

### For Employers
- Monitor changing skill requirements
- Evaluate skills in combination rather than individually
- Consider geographic and remote-work patterns when recruiting
- Use median salary alongside average salary
- Improve standardization of job titles, locations, companies, and skill labels

## Limitations

Several limitations should be considered:

- Salary information is available for only a subset of job postings
- A job posting does not necessarily represent a unique vacancy or an actual hire
- The analysis identifies associations between skills and salaries rather than causal relationships
- Some company records represent recruiters, staffing firms, or generic names rather than employers
- Geographic classification is not always standardized; `job_country` was used for country-level comparisons
- The dataset reflects the period represented in the source data and should not automatically be treated as a current market snapshot

## Conclusion

This project demonstrates how SQL and PostgreSQL can be used to analyze a large real-world dataset and transform raw job-posting information into meaningful insights. The analysis examined job demand, salaries, skills, companies, geography, remote work, and time trends.

SQL was central to connecting multiple relational tables, calculating statistics, and supporting evidence-based decision-making. The findings highlight the importance of SQL within Data Analyst roles while also emphasizing complementary skills such as Python, Excel, Tableau, Power BI, and R.

More broadly, the project demonstrates the complete analytical workflow:

Raw Data → Database → SQL → EDA → Insights → Recommendations

This provides a practical example of applying SQL not just as a query language, but as a tool for solving real-world analytical problems and communicating actionable findings.

## Dashboard

The final dashboard should provide visual summaries of:

- Job category demand
- Data Analyst skill demand
- Salary by job category
- Skill demand vs salary
- Geographic distribution
- Remote-work share
- Remote vs non-remote salary
- Monthly job demand
- Monthly salary trends
- Companies with the most Data Analyst postings

The dashboard can be enhanced with filters for:

- Country
- Company
- Job category
- Skill
- Remote status
- Time period

## Skills Demonstrated

This project highlights practical experience in several areas:

### SQL
- Complex queries
- Joins
- Aggregations
- Filtering
- Statistical calculations
- Date analysis
- Relational database analysis

### Data Analysis
- Exploratory data analysis
- Salary analysis
- Demand analysis
- Geographic analysis
- Trend analysis

### Data Engineering Fundamentals
- Relational database design
- Primary and foreign keys
- Fact and dimension tables
- Bridge/junction tables
- Data validation

### Business Analytics
- Translating data into insights
- Identifying patterns
- Communicating findings
- Making evidence-based recommendations

## Portfolio Summary

### Project Title
Data Analyst Job Market Analysis Using SQL

### Tools
PostgreSQL | SQL | psql | PowerShell | Data Visualization

### Dataset
787,686 job postings

### Primary Focus
Data Analyst roles, salaries, skill requirements, geography, remote work, and hiring trends

### Main Outcome
A complete SQL-based analysis demonstrating how a large relational dataset can be transformed into meaningful career and business insights.

## Contact / Portfolio

For more information or to view additional work, connect via GitHub or portfolio links as appropriate.

---

This project is designed to function both as a technical GitHub project and as a strong portfolio piece for recruiters, employers, and collaborators.
