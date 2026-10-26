# Review before publishing

## Changes made in this revision
- Updated the notebook's opening and explanatory text for a professional portfolio.
- Aligned the report with the notebook's actual model-selection process.
- Clarified that Logistic Regression uses default regularization settings (`max_iter=1000`), Decision Tree depth is set to 4 in advance, and KNN's `k` is selected by 5-fold training-set cross-validation using mean accuracy.
- Corrected the distinction between 149 missing cells and 134 rows with at least one missing value.
- Clarified that the reported precision/recall/F1-score use approved (1) as the positive class.
- Documented the 16 rejected applications that Logistic Regression incorrectly predicts as approved.
- Added an explicit educational-use / responsible-use warning.

## Important remaining verification
The CSV dataset was not attached in this conversation. The notebook has saved outputs from a previous run, but this revision could not rerun the entire analysis against the exact dataset. Before publication:
1. Place the exact `dataset.csv` beside the notebook.
2. Restart the kernel and run every cell from top to bottom.
3. Check that the dataset source/version matches the cited one.
4. Confirm that all recorded metrics and the selected KNN value reproduce.
5. If they differ, update the notebook, report and README together.
6. Remove the original report from `reports/` if you prefer to publish only the revised report.

## Analytical cautions
- The target is historical approval, not actual repayment/default.
- High recall refers to the approved class and should not be mistaken for strong detection of rejected applications.
- Credit history has 50 missing values and is a major predictor; imputation assumptions can materially affect the results.
- Gender and marital status are predictors; any real-world use would require fairness and governance review.
- The dataset is small and should not be used for real lending decisions.
