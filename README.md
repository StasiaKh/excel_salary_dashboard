# Excel Salary Dashboard
Excel dashboard analyzing salaries across multiple IT roles by country and employment type.

![Dashboard Demo](https://github.com/user-attachments/assets/d6f8da89-6baa-4747-9809-f2355ada5adb)

## Project Overview
This project was completed as part of the Excel for Data Analytics course by Luke Barousse.
I independently recreated the dashboard to practice Excel-based data analysis, dashboard design, and business reporting.

### Dashboard File

My final dashboard is in **[excel-salary-dashboard.xlsx](excel-salary-dashboard.xlsx)**.

## Excel Skills Used

The following Excel skills were applied to analyze and visualize the data:

- 📈 **Charts** – for visualizing salary distributions and comparisons;  
- 🧮 **Formulas and Functions** – to calculate key metrics and support analysis;  
- ✅ **Data Validation** – to create structured and user-friendly dashboard controls.  

## 📂 Data Jobs Dataset

This project uses a real-world dataset with **IT and data-related job information from 2023**, provided as part of the *Excel for Data Analytics* course.

The dataset was used to practice **business-oriented data analysis** and dashboard creation in Excel.  
It includes information about:

- 💼 **Job titles** across multiple IT and data roles  
- 💰 **Salaries**  
- 🌍 **Locations**  
- 🛠️ **Skills and job platforms**

## Dashboard Build
### Charts

Data Science Job Salaries - Bar Chart

<img width="951" height="463" alt="image" src="https://github.com/user-attachments/assets/339e7329-46f9-48a5-8c8d-4bec4247ed3b" />

- 🛠️ **Excel Features Used:** Applied bar charts with formatted salary values and a clean layout to ensure clarity and ease of interpretation.  
- 🎨 **Design Choice:** Used a horizontal bar chart to make salary comparisons across different IT roles more intuitive.  
- 📉 **Data Organization:** Job titles were sorted by descending median salary to improve readability and highlight differences between roles.  
- 💡 **Insights Gained:** The dashboard allows for quick identification of salary trends, showing that senior-level positions and engineering roles generally offer higher salaries compared to analyst roles.



Country Median Salaries - Map Chart

<img width="940" height="432" alt="image" src="https://github.com/user-attachments/assets/d1b04891-3d62-4336-b391-a3d560cf3487" />

- 🛠️ **Excel Features Used:** Used Excel’s map chart feature to visualize median salaries across different countries.  
- 🎨 **Design Choice:** Applied a color-coded map to clearly distinguish salary levels between regions and support quick visual comparison.  
- 📊 **Data Representation:** Displayed median salary values for each country with available data to provide a global overview.  
- 👁️ **Visual Enhancement:** Improved readability and immediate understanding of geographic salary trends through visual mapping.  
- 💡 **Insights Gained:** The map enables a quick assessment of global salary differences and helps identify regions with higher and lower compensation levels.

## Formulas and Functions
Median Salary by Job Titles

```excel
=MEDIAN(
  IF(
    (jobs[job_title_short]=A2)*
    (jobs[job_country]=country)*
    (ISNUMBER(SEARCH(type,jobs[job_schedule_type)))*
    (jobs[salary_year_avg]<>0),
    jobs[salary_year_avg]
  )
)
```

- 🔎 **Multi-Criteria Filtering:** Filters data by job title, country, and schedule type while excluding blank salary values.
- 📊 **Array Formula:** Uses the `MEDIAN()` function combined with a nested `IF()` statement to analyze an array of values.
- 🎯 **Tailored Insights:** Returns specific salary insights based on selected job roles, regions, and employment types.
- 🧮 **Formula Purpose:** Calculates the median salary based on the selected filters.

### Background Table
<img width="336" height="272" alt="image" src="https://github.com/user-attachments/assets/bb11e193-3255-4b72-b316-5fb777c62969" />

### Dashboard Implementation
<img width="672" height="310" alt="image" src="https://github.com/user-attachments/assets/08b27ad4-8e76-490c-ba85-7be4b2a0bd3a" />

### Count of Job Schedule Type

```excel
=FILTER(
  J2#,
  (NOT(ISNUMBER(SEARCH("and", J2#))) +
   ISNUMBER(SEARCH(", ", J2#))) *
  (J2# <> 0)
)
```
- 🔍 **Unique List Generation:** This formula uses the `FILTER()` function to clean the data by excluding entries that contain multiple schedule types (such as those joined by "and" or commas) and by removing zero values.
- 🔢 **Formula Purpose:** The resulting list provides a set of valid job schedule types, which is then used as the basis for further analysis and counting.

### Table
<img width="278" height="146" alt="image" src="https://github.com/user-attachments/assets/5f0dfd66-de76-46db-8c7f-5a03f3198f4d" />

### Dashboard Implementation
<img width="587" height="588" alt="image" src="https://github.com/user-attachments/assets/90b04132-d9ae-484b-a20b-ac3c07afa050" />

## Data Validation

- 🔍 **Filtered Lists:** Filtered values were applied as data validation rules for the **Job Title**, **Country**, and **Type** selectors within the dashboard.
- 🔒 **Controlled User Input:** Users can select only predefined and validated values, ensuring consistent filtering across the dashboard.
- 🚫 **Error Prevention:** Invalid or inconsistent entries are prevented, reducing the risk of incorrect analysis.
- 🎯 **Improved Usability:** Data validation enhances the overall usability of the dashboard and makes interactions more intuitive for end users.

## Conclusion

This project demonstrates how Excel can be used to transform raw job market data into clear and actionable insights.  
The dashboard enables users to compare salaries across roles, countries, and employment types, helping to identify meaningful compensation patterns.

The focus of this project was on clarity, usability, and delivering insights that support informed decision-making.




