# Education & Occupation Analysis

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








