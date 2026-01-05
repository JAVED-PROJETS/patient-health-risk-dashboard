# Patient Health Risk Analysis Dashboard

## Project Overview
This interactive Power BI dashboard analyzes medical data from over 5,000 patients to identify health risks based on lifestyle, occupation, and medical history.

## Dashboard Preview
![Main Dashboard View](dashboard-main-view.png)

## Interactive Tooltips and Deep Dives
![Tooltip Detail](dashboard-tooltip-detail.png)

### Key Features
* **Risk Stratification:** Categorizes patients into Normal, Moderate High, High, and Critical risk levels.
* **Interactive Tooltips:** Provides deep-dive metrics on specific demographics, such as weight averages by occupation.
* **KPI Tracking:** Real-time tracking of heart attack history, stroke prevalence, and high-risk habits.

## Technical Skills Demonstrated
* **DAX:** Created custom measures for health risk categorization and KPI tracking.
* **Data Modeling:** Structured patient data for efficient filtering by Age Group, Race, and Occupation.
* **Data Visualization:** Used Area Charts, Bar Charts, and KPI cards to tell a data-driven story.

## Insights from the Data
* **Heart Health:** 2.74% of the analyzed population has a history of heart attacks.
* **Occupation & Health:** Blue-collar workers in this dataset maintain an average weight of 63.98 kg.
* **Risk Trends:** The largest patient group (over 3,000) currently falls into the 'Normal' health risk category.
* # Patient Health Risk Analysis Dashboard

## Project Overview
This interactive Power BI dashboard analyzes a synthetic dataset of 5,191 patients from the Swayam platform to identify health risks based on lifestyle, occupation, and medical history.

## Dashboard Preview
![Main Dashboard View](dashboard-main-view.png)
![Tooltip Detail](dashboard-tooltip-detail.png)

### Key Features
* **Risk Stratification:** Categorizes patients into Normal, Moderate High, High, and Critical risk levels.
* **Interactive Tooltips:** Provides deep-dive metrics on specific demographics, such as weight averages by occupation.
* **KPI Tracking:** Real-time tracking of heart attack history (2.74%), stroke prevalence (1.73%), and high-risk habits.

## 🛠️ Technical Documentation

### Core DAX Measures
These are the actual formulas used to calculate the insights shown in the dashboard:

**1. Total Patient Volume:**
```dax
Total Number of patient's diagnosis = COUNTROWS('Patient History')
High Risk Smokers = 
CALCULATE(
    [Total Number of patient's diagnosis],
    'Patient History'[Smoking] = "Yes",
    'Patient History'[healthRisk] = "high"
)
Low Exercise High Risk = 
CALCULATE(
    [Total Number of patient's diagnosis],
    'Patient History'[Exercise] = "<30",
    'Patient History'[healthRisk] IN {"high", "moderate high"}
)
percentage of history of heart attack = [history of Heart Attack] / [Total Number of patient's diagnosis]
percentage of history of stroke = [history of Stroke] / [Total Number of patient's diagnosis]

