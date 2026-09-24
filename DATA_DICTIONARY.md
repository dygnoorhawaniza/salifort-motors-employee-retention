# 🍓 Data Dictionary

The dataset described in the supplied notebook contains these fields:

| Column | Type / role | Description |
|---|---|---|
| `satisfaction_level` | Numeric feature | Employee-reported job satisfaction, on a 0–1 scale |
| `last_evaluation` | Numeric feature | Last performance evaluation score, on a 0–1 scale |
| `number_project` | Numeric feature | Number of projects the employee contributes to |
| `average_monthly_hours` | Numeric feature | Average hours worked per month |
| `time_spend_company` / `tenure` | Numeric feature | Number of years spent at the company |
| `work_accident` | Binary feature | Whether the employee experienced a work accident |
| `left` | Target | Whether the employee left the company |
| `promotion_last_5years` | Binary feature | Whether the employee received a promotion in the previous five years |
| `department` | Categorical feature | Employee department |
| `salary` | Ordinal categorical feature | Employee salary category |

### Cleaning notes

The notebook standardizes column names, checks missing values, checks duplicates and investigates outliers.

- Missing values: none reported.
- Duplicate rows: 3,008 identified.
- The notebook investigates outliers in tenure.

### Source

The notebook references the HR Analytics and Job Prediction dataset on Kaggle:

https://www.kaggle.com/datasets/mfaisalqureshi/hr-analytics-and-job-prediction
