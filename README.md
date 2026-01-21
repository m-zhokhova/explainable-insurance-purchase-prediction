# Explainable Insurance Purchase Prediction  
**Model Comparison + SHAP Explainability**

## Overview

This project predicts whether a customer holds health insurance using demographic and socio-economic features.
The goal is not only predictive performance, but also **clear, model-grounded explanations** of what drives predictions.

---

## Dataset

- **Rows / columns:** 72,458 × 15  
- **Target:** `health_ins` (binary insurance ownership)  
- **Missingness:** 6 variables contain missing values (handled in preprocessing)

Core feature categories used in the notebook include:
- demographics (age, sex)
- employment status
- income
- marital status / family and household proxies
- location (state)

---

## Methodology

The analysis is structured as follows:

1. **Exploratory Data Analysis**
   - Data cleaning and preprocessing  
   - Distribution analysis and correlations  

2. **Predictive Modeling**
   - Logistic Regression (baseline)  
   - Decision Tree  
   - Random Forest  
   - XGBoost  
   - Model comparison using ROC-AUC  

3. **Explainability**
   - SHAP-based global explanations  
   - SHAP-based local explanations (single-customer breakdown)  
   - Interpretation of dominant drivers  

---

## Modeling Results

### ROC-AUC Comparison (Test Set)

| Model                | ROC-AUC |
|---------------------|--------:|
| **XGBoost**          | **0.8204** |
| Random Forest        | 0.8119 |
| Logistic Regression  | 0.7878 |
| Decision Tree        | 0.7638 |

**Selection:** XGBoost is the best-performing model by ROC-AUC and is used for explainability.

---

## Results — Interpretation

- Tree ensembles outperform the linear baseline, indicating meaningful non-linear structure in the feature space.
- The decision tree underperforms (lower ROC-AUC), consistent with high variance / weaker generalization.
- Random forest is strong, but XGBoost performs best overall.

Practical reading:
This task is predictable to a useful degree (ROC-AUC ≈ 0.82), but not “perfect” — which is expected for real purchase behavior.

---

## Explainability (SHAP)

This project treats explainability as a first-class outcome.

### Global explainability
- SHAP summary plots highlight which features consistently drive predictions across the dataset.
- The strongest drivers are dominated by socio-economic signals (income/employment proxies) and demographics.

### Local explainability
- SHAP force/waterfall plots show, for a single customer, which features push the prediction toward:
  - insurance ownership  
  - no insurance  

This makes the final model auditable at the individual level.

---

## Key Findings

- Best model: **XGBoost (ROC-AUC = 0.8204)**  
- Tree ensembles outperform logistic regression → non-linear effects matter.
- SHAP explanations provide both:
  - global feature influence
  - local per-customer reasoning

---

## Limitations

- The notebook focuses on ROC-AUC; it does not report calibration or threshold-optimized business metrics.
- Socio-economic variables can encode bias; explanations reflect correlations, not causation.
- No geographic/policy context (insurance rules vary by region and time).

---

## Future Work

- Add calibration (reliability curve / Brier score) and threshold tuning.
- Add fairness diagnostics (group metrics).
- Compare against a simple rule-based baseline.
- Package explainability outputs into a lightweight report/dashboard.

---

