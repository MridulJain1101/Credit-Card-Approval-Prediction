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

## Analysis Approach & Methodology
The analysis was conducted in a structured, step-by-step pipeline, transitioning from raw data processing to predictive modeling:

### 1. Data Cleaning & Imputation
Missing values within the `OCCUPATION_TYPE` column required targeted handling. Pensioners lacking occupation data were categorized as "Retired," while applicants reporting positive days employed were labeled "Unemployed." Remaining missing values were determined to be Missing Completely at Random (MCAR) and were dropped to maintain dataset integrity.

### 2. Feature Engineering
Unintuitive, negatively counted date columns (`DAYS_BIRTH` and `DAYS_EMPLOYED`) were transformed into absolute, continuous numeric variables (`AGE` and `YEARS_EMPLOYED`). This enhanced model interpretability and properly formatted the dataset for machine learning algorithms.

### 3. Data Integration & Target Variable Creation
After engineering the features, the application records and credit records were combined using the shared client `ID`. This integration allowed us to evaluate the credit history and create a new binary `Status` column, indicating whether an applicant was ultimately selected or rejected. The merged dataset revealed a significant class imbalance, with **402,100 applicants rejected** and **36,457 applicants accepted**.

### 4. Exploratory Data Analysis & Visualizations
To understand the demographic and financial profiles of the applicants, we conducted extensive visual analysis. We visualized several features (such as categorized years of employment, age groups, and income types) using side-by-side bar charts and pie charts. This helped us identify the specific characteristics, behaviors, and trends of people who are more likely to get accepted versus those who get rejected.

### 5. Correlation Analysis
Before modeling, we performed a thorough correlation analysis and visualization. This step was crucial for identifying multicollinearity among the independent variables and understanding the underlying statistical relationships between the demographic features and the new `Status` target variable.

### 6. Predictive Modeling
Finally, we utilized the pre-processed and structured data to train classification algorithms. We performed **Logistic Regression** and **Random Forest** modeling to evaluate and compare the predictive accuracy of our framework. This allowed us to determine the most effective approach for predicting credit card approvals and capturing the complex relationships within the data.

## Conclusions
The analysis revealed that transforming raw temporal data into structured features (like exact Age and Years of Employment) significantly improved the interpretability of applicant profiles. The comparative modeling approach demonstrated that advanced ensemble methods like Random Forest are highly capable of capturing the complex, non-linear relationships present in financial background data, ultimately providing strong predictive accuracy for credit risk assessment. Finally, the result is that the applicants with a Higher amount of incoe, Age and More number of years employed, had a higher chance of getting the credit card than others. Top main features were - Total Income, Age, Employed Years, Number of Family members and if the applicant owns a car or not. This analysis could be used by an applicant or any credit card approval company to refer while applying or assigning the card.

## Tools and Techniques
* **Language:** Python
* **Data Manipulation & Cleaning:** Pandas, NumPy, DateTime
* **Data Visualization:** Matplotlib, Seaborn
* **Machine Learning & Modeling:** Scikit-Learn (Logistic Regression, Random Forest)
* **Environment:** Google Colab

