# Predicting High-Value Physician Payments using Machine Learning

## Project Overview
This project was completed as part of my Master’s coursework in Machine Learning / Artificial Intelligence and Business Analytics at the University of South Florida. The goal was to predict whether a physician is likely to receive a high-value industry payment, defined as a payment greater than $10,000, using CMS Open Payments data.

The project focuses on a real-world compliance problem where missing a high-risk case can be more costly than generating extra false positives. Because of this, recall was prioritized as the main evaluation metric.

## Business Problem
Healthcare manufacturers and pharmaceutical companies report financial payments made to physicians through the CMS Open Payments program. Large payments may require additional compliance review because they can raise transparency and conflict-of-interest concerns.

This project builds a supervised machine learning model to help identify high-value payment cases earlier and support compliance teams with risk-based monitoring.

## Dataset
- Source: CMS Open Payments General Payments data, 2023
- Target variable: `High_Payment`
  - `1` if `Total_Amount_of_Payment_USDollars > 10000`
  - `0` otherwise

## Features Used
- Physician specialty
- Recipient state
- Nature of payment or transfer of value
- Total payment amount used to derive the target variable

## Methods Used
- Data cleaning and preprocessing
- One-hot encoding for categorical variables
- Train/test split with stratification
- SMOTE for handling severe class imbalance
- Model comparison across multiple supervised classifiers
- Model evaluation using recall, precision, F1-score, ROC-AUC, confusion matrix, ROC curve, and precision-recall curve

## Models Tested
- Logistic Regression
- Decision Tree
- Random Forest
- XGBoost
- Support Vector Machine
- Multi-Layer Perceptron

## Key Result
XGBoost achieved the strongest recall-focused performance, identifying all true high-value payment cases in the test data. This made it the best fit for the compliance-focused objective, where reducing false negatives is more important than maximizing overall accuracy.

## Why Recall Was Prioritized
In this use case, a false negative means a high-value payment case is not flagged for review. That could create compliance, regulatory, or reputational risk. Therefore, the project prioritized recall even if it increased false positives, because flagged cases can still be reviewed manually by compliance teams.

## Tools and Libraries
- Python
- pandas
- numpy
- scikit-learn
- imbalanced-learn
- XGBoost
- matplotlib
- seaborn
- Jupyter Notebook / Google Colab

## Project Files
- `ISM6251_Final_Merged_Optimized.ipynb` — main notebook containing preprocessing, modeling, evaluation, and recommendations
- `README.md` — project summary and documentation
- `requirements.txt` — Python dependencies

## What I Learned
This project helped me understand how to approach machine learning problems where the business objective matters more than a single accuracy score. I learned how to work with highly imbalanced data, select the right evaluation metric, compare models, and explain technical results in a business-friendly way.

## Future Improvements
- Add multiple years of CMS Open Payments data
- Include physician-level historical features
- Tune classification thresholds to balance recall and precision
- Build a dashboard for compliance review teams
- Add model explainability using SHAP or feature importance analysis
