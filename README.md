# COVID 19 and Its Effect on the Job Market

**Course:** MSc Business Analytics, Royal Holloway, University of London
**Module:** MN5813
**Module Tutor:** Alex Reppel
**Candidate Number:** 2502850

---

## Note for the Module Tutor

This repository was created to submit the Python assignment for MN5813 and is shared here for assessment purposes only.

---

## Overview

This assignment looks at the global spread of COVID 19 (confirmed cases, deaths, recoveries and testing) and, alongside that, at employee attrition data, to explore how the pandemic period relates to shifts in the workplace. The two datasets are cleaned and analysed independently, then brought together through summary statistics and visualisations to compare patterns across countries and across company departments.

## Objectives

1. Compare COVID 19 cases against deaths across countries
2. Calculate the attrition rate per department in the HR dataset
3. Build a correlation matrix of COVID 19 indicators

## Generative AI Declaration

Generative AI (the free version of ChatGPT, https://chatgpt.com/) was used at points in this assignment to help debug and refine code. All AI assisted code was reviewed and adapted, and combined with material from the module's own coursework, before being included here.

---

## Datasets

### 1. COVID 19 Global Statistics Dataset
`COVID-19 Global Statistics Dataset.csv`

Country level COVID 19 statistics covering 239 countries and territories across 14 columns: Total Cases, New Cases, Total Deaths, New Deaths, Total Recovered, New Recovered, Active Cases, Serious/Critical, Total Cases per 1M population, Deaths per 1M population, Total Tests, Tests per 1M population, and Population.

Most numeric columns were originally stored as text, with commas as thousand separators, so they needed to be converted to numeric types before they could be analysed.

### 2. IBM HR Employee Attrition Dataset
`WA_Fn-UseC_-HR-Employee-Attrition.csv`

A widely used HR analytics dataset holding 1,470 employee records across 35 attributes, including demographics, job role, department, satisfaction scores, compensation, working years, and whether the employee left the company (Attrition).

Three constant, non-informative columns (EmployeeCount, Over18, StandardHours) were removed during cleaning, and text columns were standardised to lowercase with whitespace stripped.

---

## Methodology

The notebook follows this sequence:

1. **Import libraries:** pandas, matplotlib, seaborn
2. **Load the raw datasets:** the COVID 19 CSV and the HR CSV
3. **Inspect structure:** `.info()` on both datasets to check column types and missing values
4. **Clean the COVID 19 data:** strip commas from numeric columns and convert them to numeric type, then fill missing values with zero
5. **Clean the HR data:** drop the three redundant constant columns, then standardise categorical text columns
6. **Aggregate COVID 19 data by country:** sum Total Cases, Total Deaths and Population, then derive Cases per Million and Deaths per Million
7. **Illustrative economic indicator:** a simple hypothetical score combining Cases per Million and Deaths per Million, included to demonstrate how the COVID 19 summary could be combined with real external economic data if it were available. This indicator is a placeholder built from the existing columns, not a real economic dataset.
8. **Visualise COVID 19 data:** a scatter plot of Cases per Million against Deaths per Million by country, coloured by the illustrative economic indicator and sized by population
9. **Aggregate HR data by department:** calculate the normalised attrition rate (proportion of yes/no) for each department
10. **Visualise HR data:** a stacked bar chart of attrition rate by department
11. **Correlation analysis:** a correlation matrix across the numeric COVID 19 indicators (Total Cases, New Cases, Total Deaths, New Deaths, Total Recovered, New Recovered, Active Cases, Serious/Critical, Cases per 1M, Deaths per 1M, Total Tests, Tests per 1M, Population), visualised as a heatmap
12. **Export:** both cleaned datasets are saved out for reuse

## Sample Results

After cleaning, the COVID 19 dataset covers 239 countries. Ranked by total confirmed cases, the top five are the United States (about 111.4 million), India (about 45.0 million), France (about 40.1 million), Germany (about 38.8 million) and Brazil (about 38.4 million).

The cleaned HR dataset retains all 1,470 employee records across 32 columns once the three constant fields are removed.

## Visualisations

The notebook produces three charts, viewable inline when the notebook is opened on GitHub or in Jupyter:

1. Scatter plot: COVID 19 Cases per Million vs Deaths per Million by country
2. Stacked bar chart: Attrition rate by department
3. Heatmap: Correlation matrix of COVID 19 numeric features

---

## Repository Structure

| File | Description |
|---|---|
| `5813 (1).ipynb` | Main analysis notebook containing all code, commentary and visualisations |
| `COVID-19 Global Statistics Dataset.csv` | Raw COVID 19 dataset |
| `WA_Fn-UseC_-HR-Employee-Attrition.csv` | Raw HR attrition dataset |
| `cleaned_covid_data.xls` | Cleaned COVID 19 dataset exported from the notebook |
| `cleaned_hr_data.xls` | Cleaned HR dataset exported from the notebook |
| `README.md` | This file |

## Tools and Libraries

- Python 3
- pandas
- matplotlib
- seaborn
- Jupyter Notebook

## How to Run

1. Clone or download this repository
2. Keep both raw CSV files in the same folder as the notebook
3. Open `5813 (1).ipynb` in Jupyter Notebook or JupyterLab
4. Run the cells from top to bottom

---

**Author:** Ali Sial (Candidate Number 2502850)
