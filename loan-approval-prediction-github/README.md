# Loan Approval Prediction

**Applied Data Analytics & Machine Learning Project**  
**Author:** Abdulkadir Abdullahi Mohamed  
**Institution:** Dhambaal Institute — Batch BDA01  
**Project date:** 26 September 2026

## Overview

This project analyzes historical home-loan application decisions and compares three binary classification models: Logistic Regression, Decision Tree, and K-Nearest Neighbours (KNN). The workflow includes data quality checks, exploratory data analysis, training-only preprocessing pipelines, model evaluation, and discussion of limitations.

> **Educational use only.** The target represents historical approval decisions, not actual repayment/default. This project is not a validated credit-risk system and must not be used to automate real lending decisions.

## Business question

Can applicant characteristics help predict whether a home-loan application was historically approved?

- **Target:** `loan_status` (`1` = approved, `0` = rejected)
- **Dataset:** 614 applications and 13 columns before cleaning
- **Models:** Logistic Regression, Decision Tree, KNN
- **Evaluation:** Accuracy, precision, recall, F1-score, confusion matrices
- **Best recorded overall result:** Logistic Regression at 86.18% accuracy on the held-out test split

## Statistical analysis and workflow

1. Inspect dimensions, data types, target distribution, and missing values.
2. Clean structural issues by removing the ID field, standardizing `dependents` (`3+` to `3`), and encoding the target.
3. Use frequency counts, crosstabs, approval proportions, distribution plots, and correlation analysis for EDA.
4. Engineer `total_income` as applicant income plus co-applicant income.
5. Split the data into training (491) and test (123) sets using stratification.
6. Impute missing numeric values, impute and encode categorical features, and scale inputs for Logistic Regression/KNN within pipelines.
7. Train Logistic Regression, Decision Tree, and KNN.
8. Select KNN's `k` by 5-fold stratified cross-validation on the training set using mean accuracy.
9. Evaluate on the held-out test set and document class-specific errors.

## Results recorded in the notebook

| Model | Accuracy | Precision | Recall | F1-score |
|---|---:|---:|---:|---:|
| Logistic Regression | 86.18% | 84.00% | 98.82% | 90.81% |
| Decision Tree | 84.55% | 83.00% | 97.65% | 89.73% |
| KNN (`k=21`) | 81.30% | 79.25% | 98.82% | 87.96% |
| Baseline: approve all | 69.11% | 69.11% | 100.00% | 81.73% |

**Metric note:** Precision, recall and F1-score above use approved (`1`) as the positive class. Logistic Regression identified 22 of 38 rejected applications and incorrectly predicted approval for 16 of them. High recall for the approved class does not mean strong detection of rejected applications.

## EDA highlights

- Approval rate: 79.6% for applicants with `credit_history = 1`, compared with 7.9% for `credit_history = 0` (missing values excluded from this crosstab).
- Observed approval rate: semiurban 76.8%, urban 65.8%, rural 61.5%.
- Applicant-income distributions overlap substantially between approved and rejected groups.
- `credit_history` has the strongest observed correlation with the target among the numeric variables shown (about 0.56).
- The Decision Tree assigns approximately 0.7448 feature importance to `credit_history`.

## Methodology transparency

- Logistic Regression uses `max_iter=1000` with default regularization settings.
- Decision Tree uses `max_depth=4`, specified in advance; this value was not selected by cross-validation.
- KNN evaluates odd values of `k` from 1 to 29 using 5-fold stratified cross-validation on the training set and selects by mean accuracy.
- Preprocessing is inside pipelines to prevent the test set and cross-validation validation folds from influencing imputation, encoding or scaling.

## Dataset

The notebook expects a CSV named `dataset.csv` in the same directory. The dataset was not included in the uploaded materials for this revision, so it is intentionally excluded from the repository. See [`data/README.md`](data/README.md). The submitted materials cite Kaggle mirrors; verify the exact CSV version and usage terms before running or sharing it.

## Run locally

```bash
python -m pip install -r requirements.txt
jupyter notebook
```

Place `dataset.csv` next to `loan_approval_prediction.ipynb`, then run all cells from top to bottom. `scikit-learn >= 1.2` is required for the `OneHotEncoder(sparse_output=False)` argument.

## Repository structure

```text
loan-approval-prediction/
├── loan_approval_prediction.ipynb
├── README.md
├── requirements.txt
├── LICENSE
├── .gitignore
├── data/
│   └── README.md
├── docs/
│   └── REVIEW_BEFORE_PUBLISHING.md
└── reports/
    ├── Loan_Approval_Prediction_Report_REVISED.pdf
    └── original_course_report.pdf
```

## Author

**Abdulkadir Abdullahi Mohamed**  
Applied Data Analytics & Machine Learning — Dhambaal Institute, Batch BDA01
