# Bank Fraud Detection - Final Project 

##  Overview

This project focuses on detecting fraudulent transactions in a bank dataset using various machine learning algorithms. We explored the dataset through detailed exploratory data analysis, applied statistical tests to understand key patterns, and trained multiple classification models to predict fraud effectively.

##  Problem Statement

**Objective:** Build a predictive model to enhance fraudulent bank transactions detection and identify key indicators associated with fraud.

---

##  Dataset

The dataset includes transaction records with the following features:
- `TransactionID`
- `TransactionDate`, `TransactionAmount`
- `TransactionType`, `TransactionWeekday`, `TransactionHour`
- `MerchantID`, `MerchantLocation`
- `CustomerID`, `Age`, `balance`
- `FraudLabel` (1 = Fraud, 0 = Not Fraud)

---

##  Exploratory Data Analysis

- Analyzed fraud distribution across time of day, transaction types, weekdays, customer age, and account balance.
- Significant insights:
  - Fraud is more likely on Wednesdays.
  - Early morning transactions show higher fraud rates.
  - Smaller transaction amounts are more susceptible to fraud.

##  Statistical Testing

- **Chi-Square Test:** Tested categorical variables (e.g., `TransactionType`, `MerchantLocation`) for association with fraud.
- **T-Test:** Compared numeric variables (e.g., `TransactionAmount`, `Age`) between fraud and non-fraud groups.

---

##  Modeling Workflow

1. **Preprocessing:**
   - Converted time variables
   - Created dummy variables
   - Normalized numeric features
   - Applied **SMOTE** for class imbalance

2. **Cross-Validation:**
   - 10-fold CV on 80/20 training/testing split

3. **Models Used:**
   - Logistic Regression
   - XGBoost ✅
   - LightGBM

4. **Evaluation Metrics:**
   - Accuracy, **ROC AUC**, **Sensitivity**, Specificity, PPV, NPV

---

##  Best Model: XGBoost

| Metric         | XGBoost Score |
|----------------|----------------|
| ROC AUC        | High (~0.86)   |
| Sensitivity    | Strong         |

- **Final evaluation**: XGBoost outperformed others on cross-validation and test data.
- **Confusion matrix** and **ROC curve** confirm robustness.

---

##  Feature Importance (from XGBoost)

Most influential features:
- `Age`
- `TransactionAmount`
- `TransactionType - Withdrawls`

These provide valuable signals for fraud detection and model explainability.

---

##  Tech Stack

- **Language**: R
- **Packages**: `tidymodels`, `xgboost`, `lightgbm`, `themis`, `ggplot2`, `corrplot`, `ranger`, `kknn`, `parsnip`, `recipes`, `broom`, and more.

---
