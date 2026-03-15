# Key Insights and Conclusion

## Introduction
This document outlines the analytical journey of predicting credit card approval outcomes. By systematically processing applicant demographic and financial records, we developed a robust classification framework to evaluate credit risk and identify the core drivers of application success.

## Section 1: Data Cleaning and Integration
**Explanation:**
Raw financial and demographic data often contains inconsistencies, missing values, and unintuitive formats. Data cleaning is the essential first step to establish a reliable, mathematically sound foundation required for machine learning algorithms to function without bias.

**Performed Inside:**
* **Target Definition:** We merged `application_record.csv` and `credit_record.csv` using the unique client ID to create a definitive `Status` column (Accepted/Rejected). This integration revealed a significant class imbalance in the dataset (402,100 rejected vs. 36,457 accepted).
* **Missing Value Handling:** We addressed over 134,000 missing values in the `OCCUPATION_TYPE` column. Pensioners were logically recategorized as 'Retired', and applicants with a positive number of days employed were labeled 'Unemployed'. 
* **MCAR Validation:** We conducted an acceptance rate comparison to evaluate the remaining missing data. The acceptance rate was 8.8% for missing occupations versus 8.2% for known occupations. This confirmed the data was Missing Completely at Random (MCAR), allowing for safe removal.
* **Feature Transformation:** We converted negative, backwards-counted temporal variables (`DAYS_BIRTH`, `DAYS_EMPLOYED`) into absolute, continuous features (`AGE`, `YEARS_EMPLOYED`).

**Key Takeaway:** Strategic imputation and the transformation of raw temporal data into clean, continuous variables are critical preprocessing steps that directly enhance model interpretability and reliability.

## Section 2: Exploratory Data Analysis (Visualisation)
**Explanation:**
Visualisation bridges the gap between raw numbers and actionable intelligence. It allows us to intuitively compare the demographic profiles of accepted clients against those who were rejected to spot underlying behavioral trends.

**Performed Inside:**
* **Binning Continuous Variables:** We grouped continuous features like `YEARS_EMPLOYED` into distinct categorical buckets (e.g., 0-3, 4-6, 7-9 years) to analyze career tenure trends.
* **Comparative Plotting:** We generated side-by-side bar charts and pie charts to map the proportional distributions of our target variable across these different demographics.
* **Profile Mapping:** We visualized various categorical features (such as income type and education level) to map out the typical characteristics of an approved applicant versus a rejected one.

**Key Takeaway:**
Visual exploratory analysis effectively uncovers demographic fault lines, showing precisely which employment and income brackets historically favor credit approval.

## Section 3: Correlation Analysis
**Explanation:**
While visualizations show general trends, correlation analysis mathematically quantifies the strength and direction of relationships between individual features and the final credit approval status.

**Performed Inside:**
* **Matrix Computation:** We calculated a comprehensive correlation matrix against the binary `Status` target to assess feature relationships.
* **Ranked Visualization:** We plotted a sorted correlation bar chart to rank features from the strongest positive correlation to the strongest negative correlation.
* **Risk Identification:** We isolated the specific traits that mathematically act as approval drivers (positive correlation) versus the primary risk factors leading to rejection (negative correlation).

**Key Takeaway:**
Statistical correlation validates visual assumptions and serves as a necessary diagnostic step to identify feature redundancy and the strongest mathematical predictors of credit risk.

## Section 4: Machine Learning Models
**Explanation:**
The final phase transitions from historical analysis to predictive foresight. By training algorithms on the structured data, we create automated systems capable of accurately evaluating new credit card applications.

**Performed Inside:**
* **Baseline Modeling:** We deployed Logistic Regression to establish a baseline performance metric for linear relationships within the applicant data.
* **Ensemble Modeling:** We implemented a Random Forest classifier to capture complex, non-linear interactions between financial and demographic variables.
* **Feature Importance Extraction:** We leveraged the Random Forest algorithm to evaluate and isolate the top 20 most influential variables driving the model's decision-making process.

**Key Takeaway:**
Advanced ensemble methods, specifically Random Forest, significantly outperform baseline models by successfully navigating the complex, non-linear realities of financial background data, resulting in highly accurate credit risk assessments.

## Conclusion
The systematic approach—from rigorous data cleaning and visual exploration to correlation diagnostics and ensemble modeling—provides a comprehensive framework for credit risk assessment. The extraction of top feature importances ensures the model remains interpretable and highly actionable for making automated financial decisions.
