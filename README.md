# HR Attrition Analytics Dashboard

## 1. Project Overview

This project is an interactive **HR Attrition Analytics Dashboard** built with **Power BI**
The dashboard analyzes employee attrition patterns using HR data and provides insights into workforce trends across departments, age groups, salary bands, job roles, overtime status and years at company

The goal of this project is to help HR teams and business users understand key factors related to employee attrition and support data-driven decision-making

---

## 2. Dashboard Preview

The report includes two main pages:

### Page 1: Overview Dashboard
This page provides a high-level summary of employee attrition and workforce metrics

Main components:
- Total Employees
- Attrition Rate
- Average Salary
- Average Age
- Attrition Distribution
- Attrition by Department
- Attrition by Age Group
- Attrition by Salary Band
- Interactive slicers
- Overview & Insights section

### Page 2: Detail Analysis
This page provides a deeper analysis of salary, tenure, overtime and attrition patterns

Main components:
- Average Salary by Department and Job Role
- Average Monthly Income by Years at Company
- Attrition Count by OverTime
- Detail Insights section
- Interactive slicers for Department, Job Role and Attrition

---

## 3. Dataset

The project uses an HR employee attrition dataset containing employee-related information such as:

- Age
- Department
- Job Role
- Monthly Income
- Years at Company
- OverTime
- Attrition
- Gender
- Job Satisfaction
- Work Life Balance
- Education Field

The dataset was cleaned and transformed before building the dashboard

---

## 4. Tools Used

- **Power BI Desktop**
- **Power Query**
- **DAX**
- **Data Visualization**
- **HR Analytics**

---

## 5. Data Preparation

The data preparation process included:

- Importing the HR dataset into Power BI
- Checking column data types
- Cleaning and transforming data using Power Query
- Creating calculated columns for analysis
- Creating DAX measures for KPI calculations
- Designing interactive visuals and slicers

---

## 6. DAX Calculations

Several calculated columns and measures were created to support the analysis

### Attrition Flag

```DAX
AttritionFlag = IF('HR'[Attrition] = "Yes", 1, 0)
```

This column converts employee attrition status into numeric values:
- Yes = 1
- No = 0

### Age Group

```DAX
AgeGroup =
SWITCH(
    TRUE(),
    'HR'[Age] <= 25, "Under 25",
    'HR'[Age] <= 35, "26-35",
    'HR'[Age] <= 45, "36-45",
    "Over 45"
)
```

This column groups employees into age categories for easier analysis

### Salary Band

```DAX
SalaryBand =
SWITCH(
    TRUE(),
    'HR'[MonthlyIncome] <= 3000, "Low",
    'HR'[MonthlyIncome] <= 6000, "Medium",
    'HR'[MonthlyIncome] <= 10000, "High",
    "Very High"
)
```

This column groups employees by monthly income level

### Attrition Rate

```DAX
AttritionRate =
DIVIDE(
    SUM('HR'[AttritionFlag]),
    COUNT('HR'[EmployeeNumber]),
    0
)
```

This measure calculates the overall attrition rate

---

## 7. Key Insights

Some key insights identified from the dashboard include:

- The overall attrition rate is approximately **16.12%**.
- The **Research & Development** department has the highest attrition count
- Employees in the **26-35 age group** show the highest attrition count
- Employees in the **Low salary band** have the highest attrition count
- Monthly income generally increases with years at company
- Employees who work overtime show a higher attrition count

---

## 8. Dashboard Design

The dashboard uses a modern pastel theme with:

- Soft background colors
- Rounded visual cards
- Drop shadows
- Pastel color palette
- Clear KPI cards
- Interactive filters
- Clean chart layout

The design focuses on readability, consistency and professional presentation

---

## 9. Skills Demonstrated

This project demonstrates the following skills:

- Data cleaning and transformation
- Power Query usage
- DAX calculated columns and measures
- KPI dashboard design
- Data visualization best practices
- Business insight generation
- HR data analysis
- Interactive Power BI report development

---

## 10. Project Files

Recommended files for this repository:

```text
HR_Analytics_Dashboard.pbix
README.md
screenshots/
dataset/
```

Suggested screenshot files:

```text
screenshots/overview-dashboard.png
screenshots/detail-analysis.png
```

---

## 11. How to Use

1. Download or clone this repository
2. Open the `.pbix` file using Power BI Desktop
3. Navigate between the report pages:
   - Overview Dashboard
   - Detail Analysis
4. Use slicers to filter the data by department, gender, age group, salary band, job role and attrition status

---

## 12. Future Improvements

Possible future improvements include:

- Adding predictive analytics for employee attrition risk
- Creating more advanced DAX measures
- Adding drill-through pages for individual employee segments
- Improving tooltip pages for deeper insights
- Publishing the dashboard to Power BI Service

---

## 13. Author: LE THANH TRUNG
*Tools: Power BI | Power Query | DAX | Python*

