# 🏢 HR Attrition Predictor
**Machine Learning · People Analytics · Binary Classification**

> *Turning workforce data into retention strategy — predicting who's likely to leave, and why.*

---

## 📌 Project Overview

Employee turnover is one of the most expensive problems organizations face. Replacing a single trained employee can cost up to **200% of their annual salary** when recruitment, onboarding, and lost productivity are factored in.

This project acts as a strategic analytics partnership with HR — moving beyond gut-feel management toward **data-driven People Analytics**. It answers two critical questions:

- **"Who is likely to leave?"** — via a trained ML classifier
- **"Why are they leaving?"** — via EDA, feature importance, and risk profiling

---

## 📁 Project Structure

hr-attrition-predictor/
├── employee.ipynb              # End-to-end analysis & ML pipeline (start here)
├── hr_raw.csv                  # Raw IBM HR dataset (1,470 employees, 35 features)
├── hr_clean.csv                # Preprocessed & encoded dataset for modelling
├── at_risk_employees.csv       # 139 flagged employees with attrition risk scores
├── rf_attrition_model.pkl      # Trained Random Forest classifier
├── scaler.pkl                  # Fitted StandardScaler for inference
└── HR_Attrition_Report.docx    # Executive summary report (non-technical)


---

## 🎯 Key Objectives

| Phase | Goal | Deliverable |
|-------|------|-------------|
| Week 1 | Data Cleaning & Encoding | `hr_clean.csv` |
| Week 2 | Exploratory Data Analysis | Visualisations + documented hypotheses |
| Week 3 | Model Building & Evaluation | `rf_attrition_model.pkl`, `scaler.pkl` |
| Week 4 | Insights & Reporting | `at_risk_employees.csv`, `HR_Attrition_Report.docx` |

---

## 📊 Dataset

- **Source:** IBM HR Analytics Employee Attrition & Performance (public dataset)
- **Size:** 1,470 employees × 35 features
- **Target variable:** `Attrition` (Yes / No) — overall rate: **~16.1%**

**Key features used:**

| Feature | Type | Description |
|---------|------|-------------|
| `Age` | Numeric | Employee age |
| `MonthlyIncome` | Numeric | Monthly salary |
| `OverTime` | Categorical | Whether employee works overtime |
| `JobSatisfaction` | Ordinal (1–4) | Self-reported satisfaction score |
| `YearsAtCompany` | Numeric | Tenure in years |
| `BusinessTravel` | Nominal | Frequency of travel |
| `MaritalStatus` | Nominal | Single / Married / Divorced |
| `StockOptionLevel` | Ordinal (0–3) | Equity participation level |
| `Department` | Nominal | Sales / R&D / Human Resources |
| `JobRole` | Nominal | 9 distinct roles |

---

## 🔬 Workflow

### 1. Data Preprocessing
- Handled missing values and duplicate records
- **Label Encoding** for ordinal variables (e.g., `JobSatisfaction`, `BusinessTravel`)
- **One-Hot Encoding** for nominal variables (e.g., `Department`, `JobRole`, `EducationField`)
- **StandardScaler** applied to numerical features before model training

### 2. Exploratory Data Analysis

Investigated attrition patterns across key dimensions:

Overtime        → 30.5% attrition (vs 10.4% without overtime)
Sales Reps      → 39.8% attrition — highest of any role
Monthly Income  → Leavers earn ~30% less ($4,787 vs $6,833 avg)
Single staff    → 25.5% attrition vs 10.1% for divorced employees
Frequent travel → 24.9% attrition vs 8.0% for non-travellers
Stock Level 0   → 24.4% attrition vs 9.4% at Level 1


### 3. Predictive Modelling
- **Problem type:** Binary Classification (Attrition: Yes / No)
- **Algorithms trained:** Logistic Regression (baseline) + Random Forest (final model)
- **Evaluation metrics:** Accuracy, Precision, Recall, F1-Score
- **Output:** Per-employee attrition probability (0–100% risk score)

### 4. Risk Profiling & Insight Generation
- Extracted feature importances from the Random Forest model
- Generated a ranked "Watch List" of 139 high-risk employees
- Produced a non-technical executive report for HR leadership

---

## 🔑 Key Findings

### Top 3 Drivers of Attrition

1. **Overtime** — Employees on mandatory overtime leave at **3× the rate** of those who don't
2. **Compensation** — Employees who left earned on average **$2,045/month less** than those who stayed
3. **Job Role** — Sales Representatives churn at nearly **40%** — the highest of any role in the company

### Attrition by Department

| Department | Attrition Rate | Headcount |
|---|---|---|
| Sales | **20.6%** | 446 |
| Human Resources | **19.0%** | 63 |
| Research & Development | **13.8%** | 961 |

### At-Risk Employee Profile
- **139 employees** flagged above risk threshold
- Risk scores range from **88% to 93.5%**
- Concentrated in early-tenure staff (≤ 1 year), Sales, and R&D Laboratory Technicians

---

## 🚀 Getting Started

### Prerequisites

```bash
pip install pandas numpy scikit-learn matplotlib seaborn joblib jupyter
```

### Run the Full Pipeline

```bash
jupyter notebook employee.ipynb
```

The notebook runs sequentially: raw data → EDA → preprocessing → model training → risk scoring → CSV export.

### Load the Trained Model for Inference

```python
import joblib
import pandas as pd

model = joblib.load("rf_attrition_model.pkl")
scaler = joblib.load("scaler.pkl")

# Prepare new employee data (must match hr_clean.csv feature schema)
# employee_df = pd.DataFrame([{ ... }])
# scaled = scaler.transform(employee_df)
# risk_score = model.predict_proba(scaled)[0][1] * 100  # → e.g., 87.3%
```

---

## 📋 HR Recommendations

| Finding | Recommended Action |
|---|---|
| Overtime drives 3× attrition | Audit overtime-heavy teams; introduce comp time or flexible scheduling |
| Sales Reps leave at 40% | Immediate compensation review + structured career path for Sales |
| No stock options → 2.6× churn | Broaden equity participation to Level 0 employees |
| Early-tenure spike | Implement 30/60/90-day structured onboarding check-ins |
| Frequent travel → 25% churn | Review travel load policies; offer remote alternatives where feasible |
| Low job satisfaction (score 1) → 23% churn | Quarterly engagement surveys with manager accountability |

---

## 📄 Deliverables Checklist

- [x] `employee.ipynb` — Annotated analysis notebook with EDA observations
- [x] `rf_attrition_model.pkl` + `scaler.pkl` — Trained model ready for inference
- [x] `at_risk_employees.csv` — Ranked Watch List with risk scores
- [x] `HR_Attrition_Report.docx` — Executive report for HR Director

---

## 🛠 Tech Stack

| Tool | Purpose |
|------|---------|
| `pandas` | Data loading, cleaning, feature engineering |
| `scikit-learn` | Encoding, scaling, model training, evaluation |
| `matplotlib` / `seaborn` | EDA visualisations |
| `joblib` | Model serialisation |
| `Jupyter` | Interactive analysis notebook |

---

## 📝 Dataset Credit

IBM HR Analytics Employee Attrition & Performance — (https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset).

---

*Built as part of a Machine Learning Internship — People Analytics track.*


## Author

   Meghna-K
