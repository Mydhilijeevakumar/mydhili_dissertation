# Predictive Healthcare Logistics Using Explainable AI: An Ethical Machine Learning Framework

## 📌 Project Overview

This project was developed as part of my MSc dissertation in Data Analytics. It presents an end-to-end machine learning framework for predicting ICU capacity risk using publicly available hospital capacity data while integrating Explainable AI (XAI) to improve transparency and support ethical AI deployment in healthcare logistics.

The workflow combines statistical analysis, predictive modelling, ensemble learning, model validation, and SHAP-based explainability to demonstrate how AI can support operational decision-making in healthcare systems.


## 🎯 Research Objectives

The project addresses four research questions:

- Identify the best-performing machine learning model for predicting ICU capacity risk.
- Determine whether prediction performance varies across different hospital groups.
- Explain how black-box machine learning models make predictions using Explainable AI.
- Evaluate the ethical implications of deploying predictive AI in healthcare logistics.


## 📊 Dataset

**Source**

COVID-19 Reported Patient Impact and Hospital Capacity by Facility (RAW)

Published by the U.S. Department of Health and Human Services (HHS)

https://healthdata.gov

The dataset contains weekly hospital-level information including:

- Total hospital beds
- Inpatient beds occupied
- Total ICU beds
- ICU beds occupied
- State
- Collection week


## ⚙️ Project Workflow

### 1. Data Preparation

- Flexible column matching for different dataset versions
- Missing value handling
- Numeric conversion
- Data cleaning
- Canonical column mapping


### 2. Feature Engineering

Two new operational metrics were created:

- ICU Occupancy Rate

```
ICU Occupancy Rate = ICU Beds Used / Total ICU Beds
```

- Bed Occupancy Rate

```
Bed Occupancy Rate = Inpatient Beds Used / Total Beds
```

Target variable:

```
ICU Capacity Risk

1 → ICU Occupancy ≥ 90%

0 → ICU Occupancy < 90%
```

---

### 3. Statistical Analysis

Chi-Square Test of Independence was used to determine whether candidate features were significantly associated with ICU capacity risk.

---

### 4. Machine Learning Models

Seven baseline models were implemented:

- Logistic Regression
- Decision Tree
- Random Forest
- XGBoost
- Gradient Boosting
- Extra Trees
- LightGBM (KNN fallback)

An additional **Stacking Ensemble** model was also developed.

---

### 5. Model Validation

- 70/30 Train-Test Split
- Stratified 5-Fold Cross Validation
- Class imbalance handling
- Performance comparison

Evaluation metrics:

- Accuracy
- Precision
- Recall
- F1 Score
- ROC-AUC

---

### 6. Explainable AI (XAI)

SHAP (SHapley Additive Explanations) was applied to the trained XGBoost model using TreeExplainer to:

- Explain feature importance
- Interpret model predictions
- Improve transparency
- Support ethical AI decision-making

---

## 📈 Results

The highest-performing models were:

| Model | F1 Score |
|--------|---------:|
| LightGBM | 0.9992 |
| Stacking Ensemble | 0.9992 |
| Gradient Boosting | 0.9992 |
| XGBoost | 0.9989 |

SHAP analysis identified:

- ICU Occupancy Rate
- Total ICU Beds
- ICU Beds Used
- Bed Occupancy Rate

as the most influential predictors of ICU capacity risk.

---

## 🛠 Technologies Used

Programming Language

- Python

Libraries

- Pandas
- NumPy
- Scikit-learn
- XGBoost
- LightGBM
- SHAP
- SciPy
- Matplotlib
- Seaborn
- Joblib

Development Environment

- Jupyter Notebook
- Google Colab

---

## 📂 Repository Structure

```
Healthcare-Logistics-AI/
│
├── data/
├── outputs/
│   ├── figures/
│   ├── model_comparison.csv
│   ├── chi_square_results.csv
│   └── cross_validation_results.csv
│
├── models/
│
├── notebooks/
│   └── Dissertation.ipynb
│
├── README.md
└── requirements.txt
```

---

## 🚀 Key Skills Demonstrated

- Data Cleaning
- Feature Engineering
- Statistical Testing
- Predictive Analytics
- Machine Learning
- Ensemble Learning
- Model Evaluation
- Explainable AI (SHAP)
- Healthcare Analytics
- Ethical AI
- Python Programming
- Reproducible Research

---

## 📚 Academic Context

This project was completed as part of an MSc in Data Analytics and investigates how Explainable Artificial Intelligence can improve transparency, fairness, and trust in predictive healthcare logistics while maintaining high predictive performance.

---

## 👤 Author

**Mydhili Jeevakumar**

- LinkedIn: *https://www.linkedin.com/in
/mydhilijeevakumar*
