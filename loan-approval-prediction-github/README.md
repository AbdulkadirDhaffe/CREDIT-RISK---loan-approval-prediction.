# Loan Approval Prediction: A Data Analysis & Machine Learning Project

**Predicting Loan Approval Outcomes Using Python, Statistical Analysis, and Machine Learning**

A supervised machine learning project that explores loan application data, identifies factors associated with loan approval, and evaluates classification models to understand their predictive performance.

**Project Focus:** Data Analysis · Statistical Insights · Machine Learning · Model Evaluation

---

## 1. Project Overview

Financial institutions need reliable ways to assess loan applications while balancing lending opportunities with credit risk. Understanding historical application data can help analysts identify patterns associated with loan approval and rejection.

This project applies a structured data analysis and machine learning workflow to a public loan prediction dataset. It combines exploratory data analysis (EDA), data cleaning, feature preparation, model development, and performance evaluation to investigate how applicant characteristics relate to loan approval outcomes.

The project demonstrates how raw data can be transformed into meaningful analytical findings and evaluated predictive models.

## 2. Business Problem

The central problem is to determine whether applicant and loan-related characteristics can help predict the outcome of a loan application.

The analysis addresses the following questions:

- What patterns distinguish approved and rejected loan applications?
- Which applicant characteristics are associated with loan approval?
- How should missing values and categorical variables be handled before modeling?
- Which classification model performs best across the selected evaluation metrics?
- What are the limitations of using predictive models to support lending decisions?

## 3. Project Objectives

- Explore the structure, quality, and distribution of the dataset.
- Identify missing values and assess relevant data-quality issues.
- Analyze relationships between applicant characteristics and loan approval.
- Prepare numerical and categorical features for machine learning.
- Train and compare multiple classification algorithms.
- Evaluate model performance using appropriate classification metrics.
- Translate analytical results into practical insights while recognizing model limitations.

## 4. Dataset Description

The project uses a public loan prediction dataset originally obtained from Kaggle.

| Attribute | Description |
|---|---|
| Original records | 614 |
| Original columns | 13 |
| Target variable | Loan approval status |
| Positive class | Approved (1) |
| Negative class | Not approved (0) |
| Data types | Numerical and categorical |

The dataset includes applicant and loan-related attributes, such as applicant income, co-applicant income, loan amount, loan term, credit history, property area, and other demographic or application characteristics.

**Data note:** The figures above describe the original dataset before preprocessing. Missing values and other data-quality issues are addressed during the analysis.

## 5. Tools & Technologies

- **Python** — data analysis and machine learning
- **Pandas** — data manipulation and preparation
- **NumPy** — numerical operations
- **Matplotlib & Seaborn** — exploratory data visualization
- **Scikit-learn** — preprocessing, model training, cross-validation, and evaluation
- **Jupyter Notebook** — interactive analysis and documentation

## 6. Project Workflow

### Step 1: Data Loading and Inspection
Loaded the dataset and examined its dimensions, data types, column names, and initial records.

### Step 2: Data Quality Assessment
Investigated missing values and assessed the completeness of relevant variables before preparing the data for modeling.

### Step 3: Exploratory Data Analysis (EDA)
Examined the distribution of loan approval outcomes and explored relationships between approval status and selected applicant characteristics.

### Step 4: Data Preprocessing
Prepared numerical and categorical features using appropriate preprocessing techniques. Missing values were handled within the modeling workflow, and the dataset was divided into training and testing sets using stratification.

### Step 5: Model Development
Developed three classification models:

1. Logistic Regression
2. Decision Tree Classifier
3. K-Nearest Neighbors (KNN)

### Step 6: Model Evaluation
Compared model performance using accuracy, precision, recall, F1-score, and confusion matrices. KNN's value of *k* was selected through stratified cross-validation on the training data.

### Step 7: Interpretation
Reviewed model performance and analytical findings to understand where predictions were reliable and where errors could create risks in a lending context.

## 7. Model Performance

The following results are recorded in the project analysis.

| Model | Accuracy | Precision | Recall | F1-Score |
|---|---:|---:|---:|---:|
| Logistic Regression | 86.18% | 84.00% | 98.82% | 90.81% |
| Decision Tree | 84.55% | 83.00% | 97.65% | 89.73% |
| K-Nearest Neighbors (k = 21) | 81.30% | 79.25% | 98.82% | 87.96% |
| Approve-All Baseline | 69.11% | 69.11% | 100.00% | 81.73% |

*Note: These are the recorded project results. They should be reproduced against the exact dataset version and current notebook before being treated as independently verified results.*

### Model Interpretation

Logistic Regression achieved the highest recorded accuracy and F1-score among the three trained models. It therefore serves as the strongest candidate in this particular experiment based on the reported metrics.

However, model selection should not rely on accuracy alone. Because the target classes have different frequencies, precision, recall, the confusion matrix, and the consequences of false approvals and false rejections must also be considered.

In particular, the reported recall of 98.82% refers to the **approved class**. It does not mean that the model is equally effective at identifying rejected applications.

## 8. Key Analytical Findings

The exploratory analysis recorded several patterns:

- **Target distribution:** 422 applications were approved and 192 were not approved in the original dataset.
- **Missing data:** 149 missing cells were recorded across seven columns; 134 rows contained at least one missing value.
- **Credit history:** Applicants with a recorded positive credit-history indicator had a substantially higher observed approval rate than those with a negative indicator.
- **Property area:** The observed approval rates differed across semiurban, rural, and urban categories.
- **Applicant finances:** Applicant income and loan amount showed relationships with the approval target in the recorded analysis.

These findings describe associations in the dataset. They do not establish causation, guarantee future outcomes, or demonstrate that any single attribute independently determines a lending decision.

## 9. Limitations & Responsible Use

This project is an educational machine learning exercise, not a validated credit-risk system.

Important limitations include:

- The dataset is relatively small and may not represent current lending populations.
- Missing-value treatment and feature preparation can influence the resulting predictions.
- Performance on a single train/test split may differ from performance on new data.
- High recall for approved applications does not establish strong detection of rejected applications.
- The analysis does not establish fairness, regulatory compliance, or suitability for real lending decisions.
- Additional validation, calibration, fairness assessment, monitoring, and domain expertise would be required before any real-world use.

**Responsible-use principle:** Loan decisions should not be automated or made solely on the basis of this model.

## 10. Repository Structure

```text
loan-approval-prediction/
│
├── loan_approval_prediction.ipynb
├── requirements.txt
├── README.md
├── LICENSE
│
├── data/
│   └── README.md
│
├── docs/
│   └── REVIEW_BEFORE_PUBLISHING.md
│
└── reports/
    └── Loan_Approval_Prediction_Report_REVISED.pdf
```

The dataset itself is not included in the repository. Follow the instructions in `data/README.md` to obtain the appropriate dataset and place it in the expected location.

## 11. How to Run the Project

### Prerequisites

Install Python and Git, then clone or download this repository.

### Installation

Create and activate a virtual environment if desired, then install the project dependencies:

```bash
pip install -r requirements.txt
```

### Dataset Setup

1. Obtain the public loan prediction dataset from the source documented in `data/README.md`.
2. Place the CSV file in the location expected by the notebook.
3. Confirm that the filename and column names match the notebook's requirements.

### Run the Notebook

Launch Jupyter Notebook:

```bash
jupyter notebook
```

Open `loan_approval_prediction.ipynb` and execute the cells in order.

**Important:** The notebook may not run from start to finish until the dataset has been added and the file path, dependencies, and results have been verified.

## 12. Skills Demonstrated

This project demonstrates practical work with:

- Data cleaning and preprocessing
- Exploratory data analysis
- Statistical interpretation of categorical and numerical variables
- Data visualization
- Feature preparation and model pipelines
- Supervised machine learning
- Classification model comparison
- Cross-validation
- Confusion matrix interpretation
- Analytical reporting and responsible interpretation of results

## 13. Author

**Abdulkadir Abdullahi Mohamed**

Data Analytics · Business Intelligence · Statistical Analysis · Machine Learning

This project is part of my ongoing development in data analytics and applied machine learning, with an interest in using data to support evidence-based business and financial decisions.

---

*If you find this project useful, feel free to explore the notebook and review the analysis. Feedback and constructive suggestions are welcome.*
