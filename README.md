# Explainable Insurance Purchase Prediction

This project addresses the prediction of health insurance ownership using demographic and socio-economic data. The primary goal is not only to achieve strong predictive performance, but also to ensure interpretability, with a clear focus on understanding why the model produces specific predictions.

## Project overview

The analysis follows a structured and transparent workflow:

- Exploratory data analysis to examine variable distributions, relationships, and data quality issues  
- Explicit preprocessing steps informed by observations from the exploratory analysis  
- Training and comparison of multiple model families, including logistic regression, decision trees, random forests, and gradient boosting  
- Selection of XGBoost as the primary model based on predictive performance  
- Post-hoc explainability using SHAP to provide both global and local explanations of model predictions  

The explainability analysis connects model behaviour back to patterns observed during exploratory analysis, supporting the use of the model as a decision-support tool rather than a black-box predictor.

## Models

The following models are included in the analysis:

- Logistic Regression (baseline linear model)  
- Decision Tree (shallow, interpretable by design)  
- Random Forest (non-linear ensemble model)  
- XGBoost (gradient-boosted trees, selected as the primary model)  

Models are evaluated using ROC-AUC, with XGBoost achieving the strongest performance on the test set.

## Explainability

Model interpretability is addressed using SHAP:

- Global explanations identify the most influential features across the dataset  
- Local explanations illustrate how individual feature values contribute to specific predictions  

Feature attributions are used to analyse model behaviour and should not be interpreted causally.

## Technologies

- Python  
- pandas, NumPy  
- scikit-learn  
- XGBoost  
- SHAP  
- matplotlib, seaborn  

## Notes

- The dataset used in this project is not included in the repository  
- All results are based on observational data and are intended for analytical and decision-support purposes  
