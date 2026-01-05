# Patient Health Risk Analysis Dashboard

## Project Overview
This interactive Power BI dashboard analyzes a synthetic dataset of **5,191 patients** to identify health risks based on lifestyle, occupation, and medical history.

## Dashboard Preview
![Main Dashboard View](dashboard-main-view.png)
![Tooltip Detail](dashboard-tooltip-detail.png)

### Key Features
* **Risk Stratification:** Categorizes patients into Normal, Moderate High, High, and Critical risk levels.
* **Interactive Tooltips:** Provides deep-dive metrics on demographics, such as identifying that white-collar workers have an average weight of 65.75 kg.
* **KPI Tracking:** Real-time tracking of heart attack history (2.74%), stroke prevalence (1.73%), and specific high-risk cohorts.

## 🛠️ Technical Documentation

### Core DAX Measures
These formulas drive the high-level KPI cards and demographic insights shown in the dashboard:

```dax
// 1. Total Patient Volume
Total Number of patient's diagnosis = COUNTROWS('Patient History')

// 2. High Risk Smokers
High Risk Smokers = 
CALCULATE(
    [Total Number of patient's diagnosis],
    'Patient History'[Smoking] = "Yes",
    'Patient History'[healthRisk] = "high"
)

// 3. Low Exercise High Risk
Low Exercise High Risk = 
CALCULATE(
    [Total Number of patient's diagnosis],
    'Patient History'[Exercise] = "<30",
    'Patient History'[healthRisk] IN {"high", "moderate high"}
)

// 4. Health Prevalence Metrics
percentage of history of heart attack = [history of Heart Attack] / [Total Number of patient's diagnosis]
percentage of history of stroke = [history of Stroke] / [Total Number of patient's diagnosis]
```
## Insights from the Data
* **Heart Health:** 2.74% of the analyzed population has a history of heart attacks.
* **Occupation & Health:** Blue-collar workers in this dataset maintain an average weight of 63.98 kg.
* **Risk Trends:** The largest patient group (over 3,085) currently falls into the 'Normal' health risk category.
