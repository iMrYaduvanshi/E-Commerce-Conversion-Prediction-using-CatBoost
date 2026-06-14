# E-Commerce Conversion Prediction using CatBoost

## Overview

This project was developed as part of the **Summer Analytics 2026 Mini-Hackathon** organized by the Consulting & Analytics Club, IIT Guwahati. The objective was to predict whether a user would convert based on demographic, behavioral, and campaign-related features.

The competition was evaluated using the **F1 Score**, requiring a balance between precision and recall while identifying converted users.

---

## Dataset

The dataset contains anonymized user-level information, including:

* Age
* Income
* City Tier
* Device Type
* Traffic Source
* Pages Viewed
* Products Viewed
* Time on Site
* Previous Purchases
* Discount Seen
* Browser Version
* Campaign Code

**Target Variable**

* `1` → Converted
* `0` → Not Converted

---

## Approach

### Data Preprocessing

* Missing value handling using median imputation
* Exploratory Data Analysis (EDA)
* Feature importance analysis

### Feature Engineering

Created additional behavioral features:

* **Engagement** = Pages Viewed × Time on Site
* **Interest Ratio** = Products Viewed / (Pages Viewed + 1)
* **Returning Customer** = Indicator based on Previous Purchases

### Model

A **CatBoost Classifier** was used because of its strong performance on structured tabular data and native support for categorical features.

### Optimization

* Evaluated using **F1 Score**
* Applied probability threshold tuning
* Optimal threshold identified: **0.26**

---

## Results

| Model                          | F1 Score |
| ------------------------------ | -------- |
| Logistic Regression (Baseline) | 0.16     |
| CatBoost (Default Threshold)   | 0.42     |
| CatBoost + Threshold Tuning    | 0.55     |

Threshold tuning significantly improved recall and overall F1 performance.

---

## Repository Structure

```text
.
├── notebook.ipynb
├── report.pdf
├── submission.csv
├── train.csv
├── public_test.csv
├── private_test.csv
├── sample_submission.csv
└── README.md
```

---

## Technologies Used

* Python
* Pandas
* NumPy
* Scikit-learn
* CatBoost
* Jupyter Notebook

---

## Key Learnings

* Handling missing values in tabular datasets
* Exploratory Data Analysis (EDA)
* Feature engineering for user behavior modeling
* Working with categorical features using CatBoost
* Optimizing classification models using F1 Score and threshold tuning

---

## Author

**Rituranjan Kumar**
