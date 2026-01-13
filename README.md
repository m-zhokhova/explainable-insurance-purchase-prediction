# Explainable Insurance Purchase Prediction

This project studies the prediction of health insurance ownership using demographic and socio-economic data. The focus is on building a reliable predictive model while keeping the reasoning behind its predictions transparent and interpretable.

Notebook can be found here: 
https://github.com/m-zhokhova/explainable-insurance-purchase-prediction/blob/main/notebooks/01_anchor_explainable_insurance.ipynb

## Overview

The workflow consists of:

- Exploratory data analysis to understand distributions, relationships, and data quality  
- Preprocessing steps motivated by findings from the exploratory analysis  
- Training and comparison of several model types, including logistic regression, decision trees, random forests, and gradient boosting  
- Selection of XGBoost as the primary model based on test-set performance  
- Post-hoc explainability using SHAP for global and individual-level explanations  

The aim is to link model behaviour back to observable patterns in the data, rather than treating the model as a black box.

## Models

The following models are included:

- Logistic Regression as a baseline  
- A shallow Decision Tree for interpretability  
- Random Forest as a non-linear ensemble model  
- XGBoost as the primary model  

Models are evaluated using ROC-AUC. XGBoost achieves the highest score on the test set.

## Explainability

Model explanations are produced using SHAP:

- Global explanations highlight the most influential features  
- Local explanations show how feature values affect individual predictions  

Feature attributions describe model behaviour and should not be interpreted causally.

## Technologies

- Python  
- pandas, NumPy  
- scikit-learn  
- XGBoost  
- SHAP  
- matplotlib, seaborn  
