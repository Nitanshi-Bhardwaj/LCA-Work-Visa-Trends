# LCA Visa Applications – Exploratory Analysis (2019–2024)

This repository contains an exploratory data analysis of U.S. Labor Condition Application (LCA) disclosures for H-1B and related work visas from FY 2019–2024.  
The project focuses on understanding **where**, **for which occupations**, and **at what wage levels** LCAs are filed and certified.

---

## Goals & Research Questions

The analysis is organized around the following questions:

1. **Geography**
   - Which states and metros account for the largest shares of **certified** applications?
   - How do certification rates for key occupations (e.g., Software Developers) vary by state?

2. **Wages by SOC**
   - How are wage offers distributed across major SOC occupations?
   - How do wages differ by pay unit (hourly vs yearly) and across states?

3. **Time Patterns**
   - How do accepted vs rejected LCAs evolve from 2019–2024?
   - What explains the spike in applications around FY 2021?

4. **Employer & Occupational Patterns**
   - How concentrated are filings among a small set of employers or occupations?
   - How do job titles, wage levels, and outcomes connect (e.g., via alluvial plots)?

5. **Process & Prediction**
   - Which factors (SOC group, location, wage level, full-time status) are most predictive of certification?
   - What does a simple decision-tree model reveal about the structure of approvals?

---

## Data

- **Source:** Public LCA disclosure data released by the U.S. Department of Labor (OFLC).  
- **Coverage:** FY **2019–2024**, using quarterly files (Q1–Q4 where applicable).
- **Key variables used:**
  - `CASE_STATUS`, `RECEIVED_DATE`, `DECISION_DATE`
  - `SOC_CODE`, `SOC_TITLE`, `JOB_TITLE`
  - `EMPLOYER_NAME`, `EMPLOYER_STATE`, `EMPLOYER_CITY`
  - `WORKSITE_STATE`, `WORKSITE_CITY`
  - `WAGE_RATE_OF_PAY_FROM`, `WAGE_RATE_OF_PAY_TO`, `WAGE_UNIT_OF_PAY`
  - `PREVAILING_WAGE`, `PW_UNIT_OF_PAY`, `PW_WAGE_LEVEL`
  - `FULL_TIME_POSITION`

A light data-quality check is performed (missingness by variable, basic filtering of empty strings and NAs).  
For several visualizations, outliers in wage distributions are removed using an IQR rule.

