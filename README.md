# Customer Churn Prediction

## Project Overview
This project predicts customer churn for a telecom company. Customer churn refers to when a customer stops using the company's services. Predicting churn helps businesses take proactive measures to retain customers, optimize marketing, and improve revenue.

## Dataset
- Contains ~7,000 customer records with demographics, account info, and service usage.
- Key features:
  - `gender`, `SeniorCitizen`, `Partner`, `Dependents`
  - `tenure`, `MonthlyCharges`, `TotalCharges`
  - Service usage: `PhoneService`, `InternetService`, `OnlineSecurity`, `TechSupport`
  - Contract & payment: `Contract`, `PaperlessBilling`, `PaymentMethod`
- Target: `Churn` (Yes/No)
- Source: [Kaggle Telco Customer Churn Dataset](https://www.kaggle.com/datasets/blastchar/telco-customer-churn)

## Methodology
1. **Data Cleaning**
   - Dropped irrelevant columns (`customerID`)
   - Converted `TotalCharges` to numeric and filled missing values
2. **Encoding**
   - Label encoding for binary categorical features
   - One-hot encoding for multi-class categorical features
3. **Handling Imbalance**
   - Used `RandomOverSampler` to balance the target variable
4. **Modeling**
   - Random Forest Classifier (`entropy`)
   - Train/test split: 75/25 with stratification
   - 10-fold cross-validation
5. **Evaluation**
   - Metrics: Accuracy, ROC-AUC, Confusion Matrix, Precision, Recall, F1-score
   - Visualizations: Correlation heatmap, ROC curve, Feature importance

## Results
- **Train Accuracy:** ~87%
- **Test Accuracy:** ~88%
- **ROC-AUC:** 0.89
- Top features: contract type, tenure, monthly charges

## Insights
- Customers with **short tenure** and **month-to-month contracts** are more likely to churn.
- Higher monthly charges and lack of services (Tech Support, Online Security) increase churn risk.

## Tools & Libraries
- Python: `pandas`, `numpy`, `matplotlib`, `seaborn`
- Machine Learning: `scikit-learn`, `imblearn`
- Visualization: Matplotlib, Seaborn

