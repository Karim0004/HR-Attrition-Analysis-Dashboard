# HR Attrition Analysis

an analytical take on IBM's public HR Employee Attrition dataset to create a dashboard best-suitable for assisting in decision-making.

---

## Executive Summary
**[📄 Executive Summary](./Final Documents/HR Attrition Analysis Executive Summary.pdf)**

## Problem Statement

total company attrition stands at 16.12% (237 of 1,470 employees), data on which roles, working conditions or tenure stages , etc. that actually drive that number can be used to assist with retention budget allocation.
HR efforts at retention can risk getting spread across the workforce instead of targeting segments where it will have the most impact.

## Techonlogies Used

| Step | Tools |
|---|---|
| Data preparation & EDA | Python (Pandas, Numpy) |
| Data modeling | Power BI (star schema) |
| Metrics | DAX |
| Dashboard & Visualizations | Power BI

## Approach

1. **EDA & cleaning** in Python — validated data quality (no missing values across 1,470 records), multiple rounds of EDA to uncover trends in data.
3. **Dimensional modeling in Power BI** — built a star schema (`Fact_Employee`, `Dim_Department`, `Dim_JobRole`) with DAX measures for Attrition Rate, Average Tenure, Overtime %, Current/Departed/Total Employees.
4. **Dashboard** — 18 visuals with a main table listing all job roles for interactive exploration by department, role, tenure, and overtime status.
5. **Statistical analysis** — used Z-scores to flag outlier roles and correlation analysis to identify which factors correlate with attrition.


## Dashboard Preview
<img src="Dashboard Preview.png" alt="Dashboard View" width="500">

## Key Findings

- **Sales Representatives are a statistical outlier**: The Sales Representative role is a massive outlier with an attrition rate of nearly 40% (39.76%), it is followed by Laboratory Technicians (23.94%) and Human Resources roles (23.08%) which also experience higher-than-average turnover. On the other hand, senior roles like Research Directors (2.50%) and Managers (4.90%) have the lowest attrition rates. Attrition rate of Sales Representatives is a true statistical outlier with z-score of 2.0.

- **Salary, not satisfaction, is a likey driver in sales rep attrition**: Sales Representatives have a Job Satisfaction of 2.73, almost equalling the total average across all job roles, indicating Job Satisfaction is not a primary driver of high turnover of Sales Representatives.
on the other hand, Average Monthly Salary between job roles experience a strong negative correlation with attrition rate (correlation coefficient of -0.76), with higher salaries seeing lower attrition rates, Sales Representatives have the lowest salary across all job roles, suggesting that Monthly Salary could be a primary driver for the high turnover of Sales Representatives.
- **Overtime almost triples the risk of attrition**: Employees who work overtime (30.53% attrition rate) are 2.9 times more likely to leave compared to those who do not (10.44%).
- **front-loaded attriton**: 29.82% of employees leave within the first 2 years, compared to 10.38% at 10+ years of tenure.
- **Risk rises with frequency of business travel**, Risk of attrition rises consistently with travel frequency, sitting at 24.91% for frequent travelers, 14.96% for rare travelers, and 8.00% for non-travelers.


## Recommendations

- Review monthly salary for Sales Representatives and build a structured promotion path so employees see a career growth path before they enter the 3-5 years tenure group.
- Check the distribution of workload in teams which contribute a lot of overtime hours, and check the possibility of balancing workload with employees who do not contribute overtime hours.
- Review current onboarding process, ensure that new hires have sufficient support and mentorship to get them through the highest risk of attrition window.
- Assess the travel demands of employees who frequently travel and check opportunities for reducing the need to travel for frequent travelers.


## Further Analysis Potential

- Inclusion of a date of attrition and date of join fields can allow for date-based trend analysis, identifying seasonality in attrition, if it exists, and correlating events with spikes in attrition.
- Machine learning predictive classification models to predict attrition based on available features and dscover the features that correlate the most with risk of attrition.

---
