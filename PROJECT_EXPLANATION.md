# 🪻 Project Explanation

## 1. Business problem

Salifort Motors' HR department collected employee data but needed help turning it into actionable insight.

The project asks:

> **What's likely to make an employee leave the company?**

The business motivation is straightforward: employee turnover can create recruitment, interview and onboarding costs, so identifying patterns associated with leaving may help HR investigate retention issues.

---

## 2. Data

The supplied notebook describes a dataset with **14,999 rows and 10 columns**.

| Variable | Meaning |
|---|---|
| `satisfaction_level` | Employee-reported job satisfaction |
| `last_evaluation` | Score from the employee's last performance review |
| `number_project` | Number of projects |
| `average_monthly_hours` | Average monthly working hours |
| `time_spend_company` / `tenure` | Years spent at the company |
| `work_accident` | Whether the employee experienced a workplace accident |
| `left` | Whether the employee left |
| `promotion_last_5years` | Whether the employee was promoted in the previous five years |
| `department` | Employee department |
| `salary` | Employee salary level |

During cleaning, the notebook finds **3,008 duplicate records** and removes them.

---

## 3. Exploratory analysis

The analysis examines:

- Employee turnover rate
- Number of projects
- Monthly working hours
- Satisfaction
- Tenure
- Salary
- Promotions
- Departments
- Correlations between variables

One notable pattern is that employees who left appear in distinct groups, including employees working unusually high hours and employees with lower satisfaction.

The notebook also observes that all employees with seven projects left in the analyzed dataset.

---

## 4. Modeling

### Logistic regression

A binary logistic regression model is used as a baseline because the target variable, `left`, has two outcomes:

- `0` = stayed
- `1` = left

The notebook reports approximately 83% accuracy for the logistic regression test result.

### Tree-based models

The project then explores:

- Decision tree
- Random forest

The tree-based models perform strongly on this dataset.

---

## 5. Feature engineering

The notebook raises an important modeling concern: **data leakage**.

Some variables may contain information that would not realistically be available at the moment HR wants to identify employees who may leave.

A new binary feature, `overworked`, is introduced while `satisfaction_level` and detailed monthly-hour information are removed from the feature-engineered modeling round.

The feature-engineered random forest becomes the final model discussed in the notebook.

---

## 6. Final model result

The supplied notebook reports the following test-set results for the feature-engineered random forest:

- **AUC:** 93.8%
- **Precision:** 87.0%
- **Recall:** 90.4%
- **F1:** 88.7%
- **Accuracy:** 96.2%

The notebook describes the model as stable and well-performing on the supplied test set.

---

## 7. Important interpretation

Feature importance is not the same thing as causation.

The strongest features identified by the supplied tree-based analysis are:

- `last_evaluation`
- `number_project`
- `tenure`
- `overworked`

These features are useful for prediction in this dataset, but the analysis alone does not prove that changing any one of them would directly cause an employee to stay.

---

## 8. HR recommendations

The supplied project recommends investigating:

1. Project-load limits
2. Four-year-tenure dissatisfaction
3. Long-hours expectations and compensation
4. Overtime and time-off communication
5. Work culture at company and team levels
6. How evaluation and rewards relate to workload

---

## 9. Ethical considerations

An employee-retention model should be treated as a **decision-support tool**, not an automatic reason to penalize or monitor employees.

Before real-world deployment, HR should consider:

- Privacy
- Fairness across departments and employee groups
- Transparency
- Whether the features are appropriate to use
- False positives and false negatives
- Human review
- Data leakage
- Whether predictions could unintentionally create a self-fulfilling cycle

The model should be used to investigate organizational conditions rather than to label individual employees as certain to leave.
