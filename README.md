# Credit Card Approval Prediction

## About the Project
This project involves the development of a predictive machine learning model to determine credit card approval outcomes. By comprehensively analyzing applicant demographic data, employment history, and financial records, the project aims to uncover key factors that influence credit risk. The end goal is to provide a robust classification framework that can accurately predict whether a prospective applicant will be approved or rejected.

## Team Members
* [Mridul Jain](https://github.com/MridulJain1101) (20250784)
* [Arunachalaeswar Chandran](https://github.com/arunnn9088) (20250179)
* [Kezia Wibowo](https://github.com/kezia-ch) (20240232)
* [Emiliano Gallardo Manrique](https://github.com/EmilianoGallardoM) (20250385)

## About the Dataset
The data utilized for this project is the [Credit Card Approval Prediction dataset](https://www.kaggle.com/datasets/rikdifos/credit-card-approval-prediction) sourced from Kaggle. 
The dataset consists of two primary files:
* `application_record.csv`: Contains demographic and background information of the applicants (e.g., income, family status, education, housing type).
* `credit_record.csv`: Contains the monthly balance and credit history status for the clients. 
The two datasets are linked using a shared, unique client `ID`.

## Analysis Approach
The initial focus was on establishing a clean, unified dataset suitable for machine learning. 
1. **Data Integration**: The application and credit records were merged using the client `ID` to create a unified target variable (`Status`) indicating approval or rejection.
2. **Data Cleaning & Imputation**: Missing values within the `OCCUPATION_TYPE` column required targeted handling. Pensioners lacking occupation data were categorized as "Retired," while applicants reporting positive days employed were labeled "Unemployed." Remaining missing values were determined to be Missing Completely at Random (MCAR) and were dropped to maintain dataset integrity.
3. **Feature Engineering**: Unintuitive, negatively counted date columns (`DAYS_BIRTH` and `DAYS_EMPLOYED`) were transformed into absolute, continuous numeric variables (`AGE` and `YEARS_EMPLOYED`) to enhance model interpretability. 

## Methodology
The structured data underwent Exploratory Data Analysis (EDA) to identify underlying distributions and correlations. Continuous variables like `YEARS_EMPLOYED` were categorized into discrete bins (e.g., 0-3, 4-6, 7-9 years) to visualize acceptance demographics using side-by-side bar charts and pie charts. 

Following EDA, the pre-processed demographic and financial features were fed into classification algorithms. Specifically, **Logistic Regression** and **Random Forest** models were trained and evaluated to identify the most accurate predictor of credit card approval, allowing for a comparison between linear and ensemble tree-based modeling techniques.

## Conclusions
The analysis revealed that transforming raw temporal data into structured features (like exact Age and Years of Employment) significantly improved the interpretability of applicant profiles. The comparative modeling approach demonstrated that advanced ensemble methods like Random Forest are highly capable of capturing the complex, non-linear relationships present in financial background data, ultimately providing strong predictive accuracy for credit risk assessment.

## Tools and Techniques
* **Language:** Python
* **Data Manipulation & Cleaning:** Pandas, NumPy
* **Data Visualization:** Matplotlib, Seaborn
* **Machine Learning & Modeling:** Scikit-Learn (Logistic Regression, Random Forest)
* **Environment:** Jupyter Notebook
