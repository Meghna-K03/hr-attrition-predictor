# 🏢 HR Attrition Predictor

Machine Learning · People Analytics · Classification Project

Predicting employee attrition using machine learning and turning workforce data into meaningful HR insights.


 ## Overview

Employee attrition is a major challenge for organizations because losing experienced employees affects productivity, hiring costs, and team stability.

This project uses Machine Learning and People Analytics to identify employees who are more likely to leave the company and understand the factors contributing to attrition. Along with prediction, the project also focuses on extracting business insights that can help HR teams make better retention decisions.

The model analyzes employee-related factors such as overtime, income, job role, travel frequency, job satisfaction, and years at the company to predict attrition risk.

## Project Structure :

```
hr-attrition-predictor/
├── employee.ipynb
├── hr_raw.csv
├── hr_clean.csv
├── at_risk_employees.csv
├── rf_attrition_model.pkl
├── scaler.pkl
└── HR_Attrition_Report.docx
```


## Dataset

IBM HR Analytics Employee Attrition & Performance Dataset(https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset)
1,470 employee records
35 features
Target variable: Attrition (Yes / No)

## Some important features used in the project:

 Age
 Monthly Income
 Overtime
 Job Satisfaction
 Years at Company
 Business Travel
 Marital Status
 Department
 Job Role
 Stock Option Level



## Project Workflow:
 
 Data Preprocessing
 Removed duplicates and handled missing values
 Applied Label Encoding and One-Hot Encoding
 Standardized numerical features using StandardScaler
 Exploratory Data Analysis

Performed analysis to understand attrition patterns across different employee groups.

## Some key observations:

  Employees working overtime showed significantly higher attrition
  Sales Representatives had the highest attrition rate
  Employees with lower salaries were more likely to leave
  Frequent business travel increased attrition risk
  Employees with low stock option levels had higher churn
  Model Building

Built and evaluated multiple classification models:

Logistic Regression
Random Forest Classifier

The Random Forest model performed best and was selected as the final model.

Risk Analysis

Generated attrition risk scores for employees and identified high-risk employee groups based on model predictions.

## Key Insights :

- Overtime was one of the strongest indicators of attrition
- Employees with lower monthly income were more likely to leave
- Sales department showed higher attrition compared to other departments
- Early-tenure employees were at greater risk of leaving
- Frequent travelers showed higher churn patterns

## How to Run
Install Dependencies
``` bash
pip install pandas numpy scikit-learn matplotlib seaborn joblib jupyter
```
Run the Notebook
jupyter notebook employee.ipynb

## Tech Stack
|Tool	|Purpose|
|--------|-------|
|pandas |	Data cleaning and analysis|
|scikit-learn	|Preprocessing and model building|
|matplotlib / seaborn|	Data visualization|
|joblib	|Model saving/loading|
|Jupyter Notebook	|Development environment|

## Output Files
rf_attrition_model.pkl → Trained Random Forest model
scaler.pkl → Saved scaler object
at_risk_employees.csv → Employees flagged with high attrition risk
HR_Attrition_Report.docx → Summary report with findings and recommendations


## Business Impact

This project demonstrates how Machine Learning can support HR teams by:

Identifying employees at risk of leaving
Understanding major attrition drivers
Supporting data-driven retention strategies
Helping organizations reduce employee turnover costs

## Dataset Credit

IBM HR Analytics Employee Attrition & Performance Dataset from Kaggle(https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset)


## Author

Meghna-K

Machine Learning internship project.
