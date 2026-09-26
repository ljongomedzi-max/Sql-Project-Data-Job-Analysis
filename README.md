# Data Analyst Job Market Analysis Using SQL

A SQL-based analysis of job market trends for Data Analyst roles using PostgreSQL. The project explores job demand, salaries, skills, geographic distribution, remote work, and monthly hiring trends across a large real-world dataset.

## Project Highlights
- Analyzed 787,686 job postings
- Focused on Data Analyst roles and related skills
- Used PostgreSQL and SQL for large-scale exploratory analysis
- Identified salary and demand patterns by country, skill, company, and work arrangement

## Repository Structure

```text
.
├── data/
│   ├── job_postings_fact.csv
│   ├── company_dim.csv
│   ├── skills_dim.csv
│   └── skills_job_dim.csv
├── sql/
│   ├── 01_create_tables.sql
│   ├── 02_load_data.sql
│   ├── 03_exploratory_analysis.sql
│   ├── 04_skill_salary_analysis.sql
│   └── 05_dashboard_queries.sql
├── dashboard/
│   └── screenshots/
├── README.md
└── requirements.txt
```

## Table of Contents
- [Project Objective](#project-objective)
- [Business Questions](#business-questions)
- [Dataset](#dataset)
- [Database Design](#database-design)
- [Tools and Technologies](#tools-and-technologies)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Key Findings](#key-findings)
- [Career Insights](#career-insights)
- [Recommendations](#recommendations)
- [Limitations](#limitations)
- [Conclusion](#conclusion)

## How to Run

1. Create a PostgreSQL database named `job_market_analysis`
2. Import the dataset tables:
   - `job_postings_fact`
   - `company_dim`
   - `skills_dim`
   - `skills_job_dim`
3. Run the SQL scripts in the `sql/` folder in order
4. Execute the dashboard queries to generate visual summaries

## Project Objective

The primary goal of this project is to use SQL to investigate the Data Analyst job market and answer questions about:

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

This project answers the following questions:

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

The database contains four main relational tables:

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

The `skills_job_dim` table acts as a bridge table because a job can require multiple skills and a skill can appear in many job postings.

## Database Design

The relational structure can be represented as:

```text
company_dim
    ↓
job_postings_fact
    ↓
skills_job_dim
    ↓
skills_dim
```

Primary and foreign keys were used to maintain relationships between the tables. This design supports analysis such as:

- Which skills are required by Data Analyst jobs?
- What salaries are associated with those jobs?
- How do skill requirements vary by location or work arrangement?

## Tools and Technologies

### Database
- PostgreSQL

### Query Language
- SQL

### Command-Line Interface
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

## Exploratory Data Analysis

### 1. Job Category Demand

The largest job categories were:

- Data Analyst — 196,593
- Data Engineer — 186,679
- Data Scientist — 172,726
- Business Analyst — 49,160
- Software Engineer — 45,019

This demonstrates substantial demand across data and technology-related roles.

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

Only postings containing annual salary information were included in this analysis.

### 3. Highest Individual Salaries

The analysis identified several unusually high-paying postings, including Data Scientist, Senior Data Scientist, Data Analyst-related roles, and senior leadership and analytics positions. These outliers show why median salary is often more informative than a simple average.

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

SQL and Python stood out as particularly prominent across the job market.

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
- Python had a higher median salary association than SQL
- Tableau and R also showed substantial demand
- Cloud and data-platform technologies were less common but sometimes had higher salary associations

These are associations rather than causal effects. Salary can also reflect seniority, company, location, industry, and job responsibilities.

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

These figures represent job postings associated with company names in the dataset and should not be interpreted as employee counts or confirmed unique vacancies.

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

Remote Data Analyst postings were identified across many countries. Among countries with at least 500 Data Analyst postings, the proportion marked as remote varied considerably.

Examples:

- Brazil — 24.34%
- Canada — 21.28%
- India — 17.12%
- Sudan — 15.84%
- Romania — 14.29%
- Philippines — 12.70%
- United Kingdom — 9.06%
- United States — 7.51%

These percentages describe dataset postings and should not be interpreted as national workforce-wide remote-work rates.

### 10. Remote vs Non-Remote Salary

For Data Analyst postings containing salary information:

| Work Arrangement | Average Salary | Median Salary |
| --- | ---: | ---: |
| Remote | $94,770 | $87,250 |
| Non-remote | $93,765 | $90,000 |

The average and median produced different comparisons, demonstrating the importance of using multiple measures when examining salary distributions.

### 11. Monthly Job Demand

Data Analyst job-posting volume varied throughout 2023.

- Highest observed monthly volume: January 2023 — 23,697 postings
- Lowest complete month in the main 2023 period: May 2023 — 13,457 postings
- December 2022 had only 485 Data Analyst postings and was treated as a partial-data period rather than a complete month for comparison

### 12. Monthly Salary Trend

Salary levels were generally stronger around July and August 2023. The median salary reached approximately:

- $95,000 in July and August 2023

Later months showed lower median salary levels. December 2022 had only six salary observations and was not suitable for meaningful trend comparison.

## Key Findings

The analysis produced several important conclusions:

### Finding 1 — Strong Data Analyst Demand
Data Analyst was one of the largest job categories in the dataset, with approximately 196,593 postings.

### Finding 2 — SQL Is Central to Data Analyst Roles
SQL was the most frequently requested Data Analyst skill.

### Finding 3 — Technical Skills Have Different Salary Associations
Skill demand and salary association do not necessarily move together. Some highly demanded skills had lower median salaries than less frequently requested technologies.

### Finding 4 — Geography Matters
The distribution of Data Analyst opportunities varied substantially between countries.

### Finding 5 — Remote Opportunities Vary
Remote-work availability differed considerably across countries.

### Finding 6 — Salary Measures Tell Different Stories
Average and median salary comparisons can produce different results, particularly when salary distributions contain high-value observations.

### Finding 7 — Job Demand Changes Over Time
The number of Data Analyst postings varied considerably across months during the observed period.

## Career Insights

The findings suggest several practical areas for Data Analyst skill development.

A strong progression is:

SQL → Excel → Python → Power BI/Tableau → Statistics → Business Communication

- SQL provides a foundation for querying and manipulating data
- Python extends analytical and automation capabilities
- Excel remains useful for business analysis and spreadsheet workflows
- Power BI and Tableau support dashboarding and data storytelling
- Business communication is essential for turning analytical results into decisions

## Recommendations

### For Aspiring Data Analysts
- Develop strong SQL skills
- Learn Python for data analysis and automation
- Become proficient in Excel
- Learn at least one BI / visualization platform
- Develop statistical and analytical thinking
- Build practical portfolio projects
- Practice explaining technical findings in business language

### For Employers
- Monitor changing skill requirements
- Evaluate skills in combination rather than individually
- Consider geographic and remote-work patterns when recruiting
- Use median salary alongside average salary
- Improve standardization of job titles, locations, companies, and skills

## Limitations

Several limitations should be considered:

- Salary information is available for only a subset of job postings
- A job posting does not necessarily represent a unique vacancy or an actual hire
- The analysis identifies associations between skills and salaries rather than causal relationships
- Some company records represent recruiters, staffing firms, or generic names rather than employers
- Geographic classification is not always standardized; `job_country` was used for country-level comparisons
- The analysis reflects the period represented in the dataset and should not automatically be treated as a current market snapshot

## Conclusion

This project demonstrates how SQL and PostgreSQL can be used to analyze a large real-world dataset and transform raw job-posting information into meaningful insights. The analysis examined job demand, salaries, skills, companies, geography, remote work, and time trends.

SQL was central to connecting multiple relational tables, calculating statistics, and delivering evidence-based insights. The findings highlight the importance of SQL within Data Analyst roles while also demonstrating the value of complementary skills such as Python, Excel, Tableau, Power BI, and R.

More broadly, the project demonstrates the complete analytical workflow:

Raw Data → Database → SQL → EDA → Insights → Recommendations

This provides a practical example of applying SQL not merely as a querying language, but as a tool for solving real-world analytical problems and communicating evidence-based findings.

## Dashboard

The final dashboard should provide visual summaries of:

- Job category demand
- Data Analyst skill demand
- Salary by job category
- Skill demand vs salary
- Geographic distribution
- Remote-work percentage
- Remote vs non-remote salary
- Monthly job demand
- Monthly salary trends
- Companies with the most Data Analyst postings

The dashboard should allow users to interact with the analysis through filters such as:

- Country
- Company
- Job category
- Skill
- Remote status
- Time period

## Project Skills Demonstrated

This project demonstrates practical experience in:

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
- Data loading and validation

### Business Analytics
- Translating data into insights
- Identifying patterns
- Communicating findings
- Making evidence-based recommendations

## Portfolio Project Summary

### Project Title
Data Analyst Job Market Analysis Using SQL

### Tools
PostgreSQL | SQL | psql | PowerShell | Data Visualization

### Dataset
787,686 job postings

### Primary Focus
Data Analyst jobs, skills, salaries, geography, remote work, and hiring trends

### Main Outcome
A complete SQL-based analysis demonstrating how a large relational dataset can be transformed into meaningful career and business insights.

## Notes

This README was designed to function both as a project overview for GitHub users and as a portfolio-ready summary for recruiters, employers, and collaborators.

If you want to make the project even stronger, consider adding:

- screenshots of the dashboard
- a schema diagram
- sample SQL queries
- a results dashboard image
- a link to a portfolio or LinkedIn profile
