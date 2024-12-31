
# Excel Salary Dashboard

![1_Salary_Dashboard.png](Project/Images/1_Salary_Dashboard_Final_Dashboard.gif)

## Introduction

This data jobs salary dashboard was created to help job seekers explore salaries for their desired jobs and ensure they're getting fair compensation. The data, sourced from my Excel course, provides a detailed look into job titles, salaries, locations, and essential skills.

### Dashboard File
My final dashboard is in [1_Salary_Dashboard.xlsx](1_Salary_Dashboard.xlsx).

### Excel Skills Used

I used several key Excel skills for this analysis:

- ** Charts**
- ** Formulas and Functions**
- ** Data Validation**

### Data Jobs Dataset

The dataset used for this project contains real-world data science job information from 2023, available through my Excel course. It includes:

- ** Job titles**
- ** Salaries**
- ** Locations**
- ** Skills**

## Dashboard Build

###  Charts

####  Data Science Job Salaries - Bar Chart

<img src="Project/Images/1_Salary_Dashboard_Chart1.png" width="850" height="550" alt="Salary Dashboard Chart1">

-  **Excel Features:** Used bar chart feature with formatted salary values and optimized layout for clarity.
-  **Design Choice:** Horizontal bar chart for easy comparison of median salaries.
-  **Data Organization:** Sorted job titles by descending salary for better readability.
-  **Insights Gained:** Quickly identified that Senior roles and Engineers earn more than Analyst roles.

#### Country Median Salaries - Map Chart

![1_Salary_Dashboard_Chart2.png](Project/Images/1_Salary_Dashboard_Country_Map.gif)

-  **Excel Features:** Used map chart feature to plot median salaries globally.
-  **Design Choice:** Color-coded map for visual differentiation of salary levels by region.
-  **Data Representation:** Plotted median salary for each country.
-  **Visual Enhancement:** Improved readability and quick understanding of geographic salary trends.
-  **Insights Gained:** Highlighted global salary disparities and identified high/low salary regions.

###  Formulas and Functions

#### Median Salary by Job Titles

```
=MEDIAN(
IF(
    (jobs[job_title_short]=A2)*
    (jobs[job_country]=country)*
    (ISNUMBER(SEARCH(type,jobs[job_schedule_type])))*
    (jobs[salary_year_avg]<>0),
    jobs[salary_year_avg]
)
)
```

-  **Multi-Criteria Filtering:** Checks job title, country, schedule type, and excludes blank salaries.
-  **Array Formula:** Utilizes `MEDIAN()` function with nested `IF()` statement to analyze an array.
-  **Tailored Insights:** Provides specific salary information for job titles, regions, and schedule types.
- **Formula Purpose:** This formula populates the table below, returning the median salary based on job title, country, and type specified.

 Background Table

![1_Salary_Dashboard_Screenshot1.png](Project/Images/1_Salary_Dashboard_Screenshot1.png)

 Dashboard Implementation

<img src="Project/Images/1_Salary_Dashboard_Job_Title.png" width="400" height="500" alt="Salary Dashboard Title">

####  Count of Job Schedule Type

```
=FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#))))*(J2#<>0))
```

-  **Unique List Generation:** This Excel formula below employs the `FILTER()` function to exclude entries containing "and" or commas, and omit zero values.
- ** Formula Purpose:** This formula populates the table below, which gives us a list of unique job schedule types.

 Background Table

![1_Salary_Dashboard_Type.png](Project/Images/1_Salary_Dashboard_Screenshot2.png)

 Dashboard Implementation:

<img src="Project/Images/1_Salary_Dashboard_Type.png" width="350" height="500" alt="Salary Dashboard Type">

### Data Validation

#### Filtered List

-  **Enhanced Data Validation:** Implementing the filtered list as a data validation rule under the `Job Title`, `Country`, and `Type` option in the Data tab ensures:
    -  User input is restricted to predefined, validated schedule types
    -  Incorrect or inconsistent entries are prevented
    -  Overall usability of the dashboard is enhanced

<img src="Project/Images/1_Salary_Dashboard_Data_Validation.gif" width="425" height="400" alt="Salary Dashboard Data Validation">

## Conclusion

This dashboard showcases insights into salary trends across various data-related job titles. By using data from my Excel course, it allows users to make informed decisions about their career paths, exploring how location and job type influence salaries. This project highlights the power of Excel for data analysis and visualization.
