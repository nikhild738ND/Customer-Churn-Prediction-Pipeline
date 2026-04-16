# Customer Churn Classification

An end-to-end machine learning project that predicts customer churn using customer demographics, account information, contract type, service usage, and billing behavior.

## Project Summary
Customer churn is a critical business problem because losing existing customers directly impacts recurring revenue and long-term growth. This project builds and evaluates multiple classification models to identify customers at risk of churning and to determine which modeling approach performs best on unseen data.

The workflow covers data understanding, preprocessing, feature engineering, model training, evaluation, and final model selection using a structured machine learning pipeline.

## Business Objective
The goal of this project is to predict whether a customer will churn and to generate interpretable insights that can help a business improve retention strategy, prioritize outreach, and reduce preventable customer loss.

## Dataset
- **Observations:** 7,043
- **Features:** 21
- **Target Variable:** `Churn`
- **Problem Type:** Binary classification
- **Class Distribution:** 73.5% No churn, 26.5% Yes churn

## Modeling Approach
The following models were trained and compared:

- Null Model
- Logistic Regression
- Regularized Logistic Regression (LASSO)
- k-Nearest Neighbors
- Neural Network
- Random Forest
- Boosted C5.0
- Naive Bayes

## Data Preparation
The preprocessing pipeline included:

- Removing `customerID` from model predictors
- Handling missing values in `TotalCharges`
- Converting categorical variables into model-ready features
- Dummy encoding categorical predictors
- Normalizing inputs for models that require scaled features
- Splitting the data into **80% training** and **20% test** sets

## Evaluation Metrics
Models were evaluated using:

- ROC-AUC
- Accuracy
- Precision
- Recall
- F1 Score

ROC-AUC was used as the primary model selection metric.

## Final Model Performance
The best-performing model was **Boosted C5.0**.

### Best Model Metrics
- **ROC-AUC:** 0.841
- **Accuracy:** 0.806
- **Precision:** 0.662
- **Recall:** 0.546
- **F1 Score:** 0.598

## Key Insights
This analysis identified several strong churn-related patterns:

- Customers with **month-to-month contracts** showed the highest churn risk
- Customers with **longer tenure** were significantly less likely to churn
- Customers who churned had **higher monthly charges on average**
- Contract structure, tenure, and billing characteristics were among the most informative churn indicators

These findings suggest that retention efforts should focus on short-term contract customers and customers showing pricing-related churn risk.

## Output
The project produces a prediction output for the holdout test set containing:

- Customer ID
- Predicted churn class
- Predicted probability of churn

This makes the model useful not only for classification, but also for customer risk ranking and prioritization.

## Repository Structure
```text
customer-churn-classification/
├── README.md
├── data/
│   └── customer_churn.csv
├── src/
│   └── customer_churn_modeling.qmd
├── reports/
│   └── customer_churn_report.pdf
└── results/
