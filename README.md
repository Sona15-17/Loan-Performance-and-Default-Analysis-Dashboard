# Loan-Performance-and-Default-Analysis-Dashboard

## Project Overview

This project focuses on analyzing loan performance and default patterns using Power BI Desktop and SQL Server. The dashboard was developed to explore borrower demographics, loan distribution, repayment risk, and financial trends through interactive visualizations and DAX calculations. The analysis includes loan amount, default rates, employment type, age groups, credit score categories, education type, and yearly loan trends to support data-driven insights and financial analysis.

## Problem Statement

Financial institutions manage large volumes of loan data, making it challenging to monitor loan distribution, borrower profiles, and default patterns efficiently. This project aims to analyze loan performance and identify trends related to loan purpose, employment type, age groups, credit score categories, and default behavior through an interactive Power BI dashboard.

## Objectives

* Analyze loan distribution across different loan purposes.
* Study borrower demographics including age group, marital status, and education type.
* Compare average income and loan amount across employment categories.
* Measure and track loan default rates by employment type and year.
* Analyze loan trends using YOY and YTD calculations.
* Explore financial risk patterns using credit score categories and decomposition analysis.
* Develop an interactive dashboard for loan performance and default analysis.

* ## Dataset Information

The project uses a loan dataset containing borrower demographic details, financial information, loan amount, repayment status, credit score, employment type, education type, marital status, mortgage details, and loan purpose. The dataset was imported into SQL Server and connected to Power BI Desktop for analysis and dashboard development.

## Tools & Technologies Used

* Power BI Desktop
* SQL Server
* DAX (Data Analysis Expressions)
* Power Query
* Data Profiling
* Data Validation
* Data Visualization

* ## Project Workflow / Steps Follow

1. Imported the loan dataset into SQL Server.
2. Connected SQL Server with Power BI Desktop.
3. Performed data profiling and checked data types using Power Query.
4. Created DAX measures for loan analysis, default rates, YOY and YTD calculations.
5. Validated calculations and measures for accuracy.
6. Built interactive dashboard pages using charts and analytical visuals.
7. Performed loan performance and default analysis using Power BI visualizations.

8. ## Data Preparation & Transformation

- Imported and stored the loan dataset in SQL Server.
- Connected SQL Server with Power BI Desktop.
- Checked and validated data types using Power Query Editor.
- Performed data profiling and data validation for accuracy.
- Created calculated columns and DAX measures for analytical reporting.
- Organized and transformed loan data for dashboard visualization and analysis.

- ## DAX Measures Used

The dashboard uses multiple DAX measures to calculate loan trends, default rates, average income, median loan amount, and year-over-year financial performance.

### Measure Table 1

1. **Average Income by Employment Type**
- Used `CALCULATE`, `AVERAGE`, and `ALLEXCEPT`
- Purpose: Calculate average applicant income while keeping Employment Type filter context.

2. **Average Loan by Age Group**
- Used `AVERAGEX` and `VALUES`
- Purpose: Calculate average loan amount across Age Groups.

3. **Default Rate by Employment Type**
- Used `COUNTROWS`, `FILTER`, `DIVIDE`, `CALCULATE`, and `ALLEXCEPT`
- Purpose: Calculate percentage of default loans for each Employment Type.

4. **Default Rate by Year**
- Used `COUNTROWS`, `FILTER`, `DIVIDE`, `CALCULATE`, and `ALLEXCEPT`
- Purpose: Calculate yearly loan default percentage.

5. **Loan Amount by Purpose**
- Used `SUMX`, `FILTER`, and `ISBLANK`
- Purpose: Calculate total loan amount while excluding blank values.


### Measure Table 2

1. **Average Loan Amount (High Credit)**
- Used `AVERAGEX` and `FILTER`
- Purpose: Calculate average loan amount for High Credit Score applicants.

2. **Loans by Education Type**
- Used `COUNTROWS` and `FILTER`
- Purpose: Count number of valid loan records by education type.

3. **Median by Credit Score Bins**
- Used `MEDIANX`
- Purpose: Calculate median loan amount.

4. **Total Loan (Credit Bins)**
- Used `CALCULATE`, `SUM`, and `ALLEXCEPT`
- Purpose: Calculate total loan amount for Adult age group across Credit Score Bins.

5. **Total Loan (Middle Age Adults)**
- Used `SUMX` and `FILTER`
- Purpose: Calculate total loan amount for Middle Age Adults.


### Measure Table 3

1. **YOY Default Loans Change**
- Used `DIVIDE`, `CALCULATE`, `COUNTROWS`, `FILTER`, `YEAR`, and `MAX`
- Purpose: Calculate year-over-year percentage change in default loans.

2. **YOY Loan Amount Change**
- Used `DIVIDE`, `CALCULATE`, `SUM`, `YEAR`, and `MAX`
- Purpose: Calculate year-over-year percentage change in loan amount.

3. **YTD Loan Amount**
- Used `CALCULATE`, `SUM`, `DATESYTD`, and `ALLEXCEPT`
- Purpose: Calculate year-to-date loan amount by Credit Score Bins and Marital Status.

- ## Calculated Columns & Data Preparation

Data preparation and calculated columns were created to improve analysis and segmentation.

### Calculated Columns Used

1. **Age Groups**
- Created to classify applicants into:
  - Teen
  - Adult
  - Middle Age Adults
  - Senior Citizens
- Used for age-based loan and default analysis.

2. **Credit Score Bins**
- Created to categorize Credit Score into:
  - Low
  - Medium
  - High
  - Very Low
- Used for loan amount and credit risk analysis.

3. **Income Bracket**
- Created to segment applicant income into categories:
  - Low Income
  - Medium Income
  - High Income
- Used in Financial Risk Metrics and Decomposition Tree analysis.

4. **Year**
- Used for yearly trend analysis and YOY calculations.

5. **Loan Date (DD_MM_YYYY)**
- Used as date field for:
  - YTD calculations
  - YOY analysis
  - Year-wise default trends
 
  ### 1. Loan Default & Overview

This dashboard page focuses on overall loan performance and default trends.

**Visualizations Used:**
- Loan Amount by Purpose
- Average Income by Employment Type
- Default Rate (%) by Employment Type
- Average Loan Amount by Age Group
- Default Rate (%) by Year
- <img width="1250" height="703" alt="Image" src="https://github.com/user-attachments/assets/a26a55e0-9425-4260-9eb6-5b2d2c296e76" />

### 2. Applicant Demographic & Financial Profile

This dashboard page focuses on applicant demographics and financial characteristics.

**Visualizations Used:**
- Median Loan Amount by Credit Score Category
- Average Loan Amount (High Credit) by Age Group and Marital Status (Donut Chart)
- Total Loan (Adults) by Credit Score Bins
- Loans (Middle Age Adults) by Mortgage / Dependents
- Number of Loans by Education Type
- <img width="1317" height="735" alt="Image" src="https://github.com/user-attachments/assets/8c8577fd-a860-4670-9e45-b021c498cfe9" />

### 3. Financial Risk Metrics

This dashboard page focuses on loan growth, financial risk, and trend analysis.

**Visualizations Used:**
- YOY Loan Amount Change by Year
- YOY Default Loans Change by Year
- YTD Loan Amount by Credit Score Bins and Marital Status
- Decomposition Tree for Loan Amount Analysis using Income Bracket and Employment Type
- <img width="1317" height="735" alt="Image" src="https://github.com/user-attachments/assets/8c8577fd-a860-4670-9e45-b021c498cfe9" />

## Key Insights / Findings

- Loan amount distribution varies across different loan purposes.
- Average income differs by Employment Type.
- Default Rate (%) changes across Employment Types and Years.
- Average loan amount varies among different Age Groups.
- Credit Score categories show differences in Median and Average Loan Amount.
- Education type shows variation in total number of loans.
- Middle Age Adults contribute significantly to total loan amount analysis.
- YOY Loan Amount and YOY Default Loans show yearly trend fluctuations.
- YTD Loan Amount analysis highlights loan distribution across Credit Score Bins and Marital Status.
- Decomposition Tree analysis provides loan amount breakdown using Income Bracket and Employment Type.

- ## Files Included in Repository

- Power BI Dashboard File (.pbix)
- Loan Dataset File
- Dashboard Screenshots
- README.md Documentation
-
## Conclusion

This project demonstrates the use of SQL Server and Power BI Desktop to analyze loan performance, borrower demographics, and default trends. DAX measures and interactive visualizations were used to study loan distribution, financial risk, and yearly trends, helping transform raw loan data into meaningful analytical insights through an interactive dashboard.
