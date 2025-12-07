# Data job market salary analysis
## Introduction
As a former job seeker, I’ve always been surprised by the lack of data exploring the most optimal jobs and skills in the data science market. I set out to understand what skills top employers request and how to land more pay.
## Questions to Analyze 
To understand the data science job market, I asked the following:
- Do more skills get you better pay?
- What’s the salary for data jobs in different regions?
- What are the top skills of data professionals?
- What’s the pay for the top 10 skills?
  
## Excel Skills Used
The following Excel skills were utilized for analysis:
- 📊 Pivot Tables
- 📈 Pivot Charts
- 🧮 DAX (Data Analysis Expressions)
- 🔍 Power Query
- 💪 Power Pivot
  
## Data Jobs Dataset
The dataset used for this project contains real-world data science job information from 2023. The dataset is available via my Excel course,
which provides a foundation for analyzing data using Excel.
It includes detailed information on:
- 👨‍💼 Job titles
- 💰 Salaries
- 📍 Locations
- 🛠️ Skills

## 1️⃣ Do more skills get you better pay?
### 🔍 Skill: Power Query (ETL)
#### 📥 Extract
- I first used Power Query to extract the original data (data_salary_all.xlsx) and create two queries:
   - 🗃️ First one with all the data jobs information.
   - 🔧 The second listing the skills for each job ID.

#### 🔄 Transform
- Then, I transformed each query by changing column types, removing unnecessary columns, cleaning text to eliminate specific words, and trimming excess whitespace.
   - 📊 data_jobs_salary
     
<img width="320" height="527" alt="Data_Job_salary_Properties" src="https://github.com/user-attachments/assets/2f8585c9-3655-4dc7-bd7b-ef713f3674ab" />
  
  - 🛠️ data_job_skills
     
<img width="327" height="566" alt="Data_Job_Skill_Properties" src="https://github.com/user-attachments/assets/c3e8749e-fdcc-417b-b012-dcb1ddda90d1" />

#### 🔗 Load
- Finally, I loaded both transformed queries into the workbook, setting the foundation for my subsequent analysis.
  - 📊 data_jobs_salary

<img width="1897" height="938" alt="Data_Job_Salary" src="https://github.com/user-attachments/assets/16ed204f-72c1-4e22-b117-6c8ef523657b" />

- 🛠️ data_job_skills
<img width="1891" height="857" alt="Data_Job_Skills" src="https://github.com/user-attachments/assets/6bbddb81-ec0a-482c-b0df-b3fa62e30d87" />

### 📊 Analysis
#### 💡 Insights

- 📈 There is a positive correlation between the number of skills requested in job postings and the median salary, particularly in roles like Senior Data Engineer and Data Scientist.
- 💼 Roles that require fewer skills, like Business Analyst, tend to offer lower salaries, suggesting that more specialized skill sets command higher market value.
<img width="741" height="453" alt="Salary VS Skills" src="https://github.com/user-attachments/assets/d926623c-b694-490f-b734-05fc14248959" />

#### 🤔 So What
- This trend emphasizes the value of acquiring multiple relevant skills, particularly for individuals aiming for higher-paying roles.
## 2️⃣ What’s the salary for data jobs in different regions?
### 🧮 Skills: PivotTables & DAX
#### 📈Pivot Table

- 🔢 I created a PivotTable using the Data Model I created with Power Pivot.
- 📊 I moved the 'job_title_short' to the rows area and 'salary_year_avg' into the values area.
- 🧮 Then I added new measure to calculate the median salary for United States jobs.

`=CALCULATE(
    MEDIAN(data_jobs_all[salary_year_avg]),
    data_jobs_all[job_country] = "United States")`

  #### 🧮 DAX
To calculate the median year salary I used DAX.
`Median Salary := MEDIAN(data_jobs_all[salary_year_avg])`

### 📊 Analysis
#### 💡 Insights

- 💼 Job roles like Senior Data Engineer and Data Scientist command higher median salaries both in the US and internationally, showcasing the global demand for high-level data expertise.
- 💰 The salary disparity between US and Non-US roles is particularly notable in high-tech jobs, which might be influenced by the concentration of tech industries in the US.


  
<img width="911" height="292" alt="Salary_Analysis" src="https://github.com/user-attachments/assets/89e03070-247f-437f-8a00-dccb3e22767b" />

#### 🤔 So What
- These salary insights are important for planning and salary negotiations, helping professionals and companies align their offers with market standards while considering geographical variations.


## 3️⃣ What are the top skills of data professionals?
### 🔧 Skill: Power Pivot
#### 💪 Power Pivot

- 🔗 I created a data model by integrating the `data_jobs_all` and `data_jobs_skills` tables into one model.
- 🧹 Since I had already cleaned the data using Power Query; Power Pivot created a relationship between these two tables.






