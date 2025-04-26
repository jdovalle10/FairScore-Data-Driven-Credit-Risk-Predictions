# Fair Score - Data Drive Credit Risk Predictions

![Python](https://img.shields.io/badge/Python-3.9%2B-blue.svg)
![Machine Learning](https://img.shields.io/badge/Machine%20Learning-Gradient%20Boosting-brightgreen)
![Scikit-learn](https://img.shields.io/badge/Scikit--Learn-Modeling%20%26%20Pipelines-orange)
![Data Science](https://img.shields.io/badge/Data%20Science-EDA%20%7C%20Feature%20Engineering-lightgrey)
![Status](https://img.shields.io/badge/Status-Completed-success)

---

## Table of Contents
- [Problem Statement](#problem-statement)
- [Data Exploration](#data-exploration)
- [Data Preparation](#data-preparation)
- [Modeling, Evaluation, and Model Selection](#modeling-evaluation-and-model-selection)
- [Model Fine-Tuning and Test Evaluation](#model-fine-tuning-and-test-evaluation)
- [Conclusion](#conclusion)

---

## Problem Statement
Credit organizations often face significant inefficiencies when relying on manual processes to assess client risk. Traditional risk evaluations require the exhaustive review of financial histories, demographic details, and loan characteristics — a process that is both time-consuming and susceptible to human error and bias. These manual assessments not only delay loan approvals but also lead to inconsistencies and suboptimal decision-making, ultimately increasing operational costs, reducing competitiveness, and missing opportunities for timely loan disbursement.

This project aims to address these challenges by developing a machine learning model capable of predicting client risk scores based on demographic, financial, and economic factors. By integrating this predictive model into the loan approval workflow, loan officers can make faster, data-driven, and fairer decisions. High-risk applicants can be flagged for additional scrutiny or receive adjusted loan terms, helping credit organizations balance portfolio growth with effective risk management while simultaneously enhancing customer satisfaction.

## Data Exploration
The exploratory data analysis (EDA) phase focused on building a comprehensive understanding of the dataset through:
- **Data Profiling:** Examination of missing values, descriptive statistics, and feature correlations.
- **Multicollinearity Assessment:** Highly correlated features were identified and dropped to prevent redundancy and instability in the modeling phase.
- **Feature Behavior Analysis:** Key features were visually explored to evaluate their relationship with the target variable (Risk Score). Preliminary analysis indicated that several categorical features showed limited predictive value.

## Data Preparation
Data preparation involved three key stages:
1. **Feature Engineering:** New features were derived based on domain understanding to enrich the dataset. A correlation analysis was conducted to assess the relevance of these new variables.
2. **Preliminary Feature Selection:** A Random Forest model (using default parameters) was trained to evaluate feature importance, guiding the selection of the most impactful predictors.
3. **Preprocessing Pipelines:** Full preprocessing pipelines were developed, incorporating:
   - Derived feature generation
   - Logarithmic transformations for skewed features
   - Kernel similarity transformation for experience-related features
   - One-hot encoding for categorical variables
   - Standardization of continuous variables

The final output of this step was a robust, ready-to-train dataset, ensuring consistency throughout the modeling process.

## Modeling, Evaluation, and Model Selection
A variety of regression models were initially evaluated using 10-Fold Cross-Validation on the training set, all tested with default hyperparameters. Among the models tested, **Gradient Boosting Regression** demonstrated the best performance with a mean MSE (Mean Squared Error) of **9.16**, outperforming alternative approaches.

## Model Fine-Tuning and Test Evaluation
To further enhance performance, a **Grid Search** was conducted over two hyperparameters:
- Number of estimators (`n_estimators`)
- Learning rate (`learning_rate`)

The tuning process identified the best model configuration:
- `n_estimators = 300`
- `learning_rate = 0.1`

This optimized Gradient Boosting model was then evaluated on the unseen test set, confirming reliable performance with a 95% confidence interval for the MSE ranging between **8.41** and **9.45**.

## Conclusion
The final Gradient Boosting model with optimized hyperparameters provides a highly effective solution for predicting client risk scores. The most influential features contributing to accurate predictions were:
- **Disposable Income**
- **Net Worth**
- **Debt-to-Income Ratio**

By implementing this model, credit organizations can automate risk scoring, significantly improving decision-making speed, reducing biases inherent in manual evaluations, lowering operational costs, and enhancing customer experience through faster loan approvals. This project demonstrates the potential of data-driven approaches to transform traditional financial risk management practices.
