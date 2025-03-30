# Education & Occupation Analysis

## Table of Contents

 - [Project Overview](#project-overview)
 - [Data Sources](#data-sources)
 - [Tools Used](#tools-used)
 - [Data Cleaning and Preparation](#data-cleaning-and-preparation)
 - [Exploratory Data Analysis](#exploratory-data-analysis)
 - [Data Analysis](#data-analysis)
 - [Results/Findings](#results-/-findings)
 - [Key Insights](#key-insights)
 - [Recommendations](#recommendations)
 - [Limitations](#limitations)
 - [References](#references)
 - 
### Project Overview
---
This project analyzes the relationship between education levels and occupations, uncovering key workforce trends. Using Excel, SQL, and Power BI, it explores how educational attainment influences career paths, highlighting the most common education levels and occupations.
By providing data-driven insights, this analysis helps policymakers, job seekers, and educators understand the impact of education on career choices.

### Data Sources
---
The dataset for this analysis comes from Kaggle. It includes key variables such as education level, occupation, and age, providing insights into workforce trends.
Data was cleaned and processed using Excel and SQL, with visualizations built in Power BI for deeper insights.

### Tools Used
---
- Excel – Data cleaning, preprocessing, and exploratory analysis
   - [Download here](https://microsoft.com)
     
- SQL Server – Data transformation, querying, and extracting insights
- Power BI – Data visualization and dashboard creation

### Data Cleaning and Preparation
---
In the initial data preparation phase, we performed the following tasks:

1. Data loading and inspection.
2. Converted data into a structured table format.
3. Standardized column names for consistency.

### Exploratory Data Analysis
---
During the EDA phase, we examined the dataset to uncover key patterns and insights:

 - Occupation by Race: Analyzed racial representation across occupations.
 - Country & Occupations: Identified dominant countries in specific job roles.
 - Education & Work Class: Explored how education influences work class categories.
 - Education & Occupation: Examined job trends based on education levels.

### Data Analysis
---
include interesting code/features worked with
  - Education Level VS Occupation
```sql
SELECT Education, Occupation,
COUNT(*) AS Total_People
FROM [dbo].['Education USA$']
GROUP BY Education,Occupation
ORDER BY Education,Total_People DESC;
```

  - Gender Representation Across Occupation
```
SELECT * FROM [dbo].['Education USA$']
SELECT Gender, Occupation,
COUNT(*) AS Total_Count
FROM [dbo].['Education USA$']
GROUP BY Gender, Occupation
ORDER BY Gender, Total_Count DESC;
```
  - Age VS Education Level
``` SELECT * FROM [dbo].['Education USA$']istribution....
SELECT 
    CASE 
        WHEN Age BETWEEN 18 AND 25 THEN '18-25'
        WHEN Age BETWEEN 26 AND 35 THEN '26-35'
        WHEN Age BETWEEN 36 AND 45 THEN '36-45'
        WHEN Age BETWEEN 46 AND 55 THEN '46-55'
        ELSE '56+' 
    END AS Age_Group, 
    Education, 
    COUNT(*) AS Total_People
FROM [dbo].['Education USA$']
GROUP BY 
    CASE 
        WHEN Age BETWEEN 18 AND 25 THEN '18-25'
        WHEN Age BETWEEN 26 AND 35 THEN '26-35'
        WHEN Age BETWEEN 36 AND 45 THEN '36-45'
        WHEN Age BETWEEN 46 AND 55 THEN '46-55'
        ELSE '56+' 
    END,
    Education
ORDER BY Age_Group, Total_People DESC;
```

### Results/Findings
---
1. Administrative Clerical Roles Dominate the U.S. – The United States has the highest number of people (819) in admin clerical roles, followed by Mexico (13) and Cuba (2).
2. Craft Repair is Common in Europe – Countries like Colombia (3), Germany (3), Poland (8), Portugal (3), Laos (1), and Cambodia (1) have craft repair as the dominant occupation.
3. Machine Operators & Inspectors – Found in Canada (4), El Salvador (4), Ecuador (2) as the top occupation.
4. Professional & Executive Roles in Asia – India (2) in professional specialty, while Taiwan (3), Thailand (1), and France (2) have executive managerial roles as top occupations.
5. Other Service & Handlers/Cleaners in Latin America & the Caribbean – Haiti (1) and Jamaica (3) have other service roles as their dominant occupation, while Nicaragua (3) leads in handlers/cleaners.
6. Smaller Trends – Countries like Italy (3) and France (2) lean toward executive managerial roles, while China (2) and the Philippines (3) are strong in admin clerical position.

   ### Key Insigts
---
- **Total Individuals Analyzed**: 899
- **Most Common Education Level**: HS Grad
- **Most Common Occupation**: Administrative Clerical
- **Average Age**: 39 years

### Recommendations
---
#### 1. Encourage Higher Education for Better Job Opportunities

 - The majority of high-paying and professional roles, such as Executive Managerial and Professional Specialty, are held by individuals with a Bachelor’s degree or higher.

 - Expanding access to higher education, scholarships, and vocational training can help more people qualify for these roles and reduce the concentration of lower-income jobs among those with only a high school diploma.

#### 2. Address Racial Disparities in Occupations

 - The data shows that certain occupations are disproportionately dominated by specific racial groups. For example, Admin Clerical and Craft Repair roles are held mainly by White workers, while Other Services and Machine Operations have a higher proportion of Black workers.

 - This suggests potential barriers to career mobility for some racial groups. Implementing equal employment opportunities, skill development programs, and mentorship initiatives can help diversify job roles and ensure fair career growth.

#### 3. Expand Self-Employment and Government Job Access

 - The majority of people work in the private sector, with fewer in self-employment or government jobs.

 - To increase economic stability and job security, policies should focus on:

    - Entrepreneurship programs that provide funding, training, and mentorship to encourage self-employment.

    - Government job recruitment drives to attract more diverse candidates into stable career paths with benefits.

#### 4. Improve Employment Support for Immigrants

 - The United States has the highest number of workers, but immigrants from Mexico, India, the Philippines, and other countries tend to dominate specific job sectors.

 - For instance, many immigrants work in Admin Clerical, Craft Repair, and Professional Specialty roles.

 - To help immigrants integrate and move into higher-paying jobs, targeted policies should include:

    - Recognition of foreign qualifications to prevent skilled immigrants from being underemployed.

    - Language and technical skill training to bridge gaps and open more career opportunities.

 #### 5. Promote High-Paying Careers Through Education & Skill Development

 - Careers in Executive Management and Professional Specialty fields tend to require higher education and specialized training.

 - Investing in STEM education, leadership programs, and technical certifications will help more people move into these lucrative fields.

#### 6. Use Country-Specific Employment Trends to Guide Workforce Policies

 - The data shows that certain occupations are dominated by workers from specific countries.

   - Poland and Portugal have more workers in Craft Repair.

   - India and the Philippines have more professionals in Specialty and Managerial Roles.

- These insights can help shape immigration and workforce policies by:

   - Identifying skill shortages and creating targeted recruitment strategies for foreign workers.

   - Offering industry-specific training programs for new immigrants based on their home country’s expertise.

### limitations

Some adjustments were made to improve the clarity and usability of the dataset. Column headings were reformatted by capitalizing them for consistency and readability. Additionally, race categories were broad, meaning the analysis could not capture more specific ethnic differences in employment trends.

The dataset was heavily dominated by records from the United States, which influenced occupation distribution by country. While other countries were represented, their sample sizes were significantly smaller, making it difficult to draw strong conclusions about global workforce trends.

### References 

-  Dataset Source:
  
The dataset was gotten from Kaggle.

 - Tools Used:
   - SQL / Excel – for data cleaning and exploratory analysis (if applicable
   -  Microsoft Power BI – for data visualization
   -  GitHub – for version control and documentation








