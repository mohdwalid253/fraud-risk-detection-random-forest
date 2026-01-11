# Fraud Risk Detection using Random Forest

This project focuses on identifying **risky taxpayers** using a **Random Forest classification model**. Individuals with **taxable income ≤ 30,000** are labeled as **Risky**, while others are labeled as **Good**.  

Since the dataset is **imbalanced**, traditional accuracy-based models perform poorly in detecting risky cases. To address this, **SMOTE (Synthetic Minority Over-sampling Technique)** is applied to improve recall for the minority (Risky) class.

---

## 📑 Table of Contents
- [📌 Problem Statement](#problem-statement)
- [📂 Dataset Description](#dataset-description)
- [🎯 Objective](#objective)
- [🔄 Project Workflow](#project-workflow)
- [🔍 Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
- [🤖 Model Building](#model-building)
- [⚖️ Handling Class Imbalance](#handling-class-imbalance)
- [🧪 Model Evaluation](#model-evaluation)
- [📊 Results Summary](#results-summary)
- [⭐ Feature Importance](#feature-importance)
- [✅ Conclusion](#conclusion)
- [🛠️ Technologies Used](#technologies-used)
- [📂 Repository Structure](#repository-structure)
- [👨‍💻 Authors and Contact](#-authors-and-contact)

---

## 📌 Problem Statement

To build a machine learning model that classifies individuals as **Risky** or **Good** based on demographic and income-related attributes, with special emphasis on identifying risky cases.

---

## 📂 Dataset Description

The dataset contains the following features:

| Feature | Description |
|------|------------|
| Undergrad | Whether the individual is an undergraduate |
| Marital_Status | Marital status of the individual |
| Taxable_Income | Annual taxable income |
| City_Population | Population of the city |
| Work_Experience | Years of work experience |
| Urban | Whether the individual lives in an urban area |

**Target Variable (Created):**
- `Risky` → Taxable Income ≤ 30,000  
- `Good` → Taxable Income > 30,000  

---

## 🎯 Objective

- Perform proper **EDA and data preprocessing**
- Build a **Random Forest classification model**
- Handle **class imbalance** effectively
- Evaluate model performance using **recall-focused metrics**
- Submit the **HTML version of the notebook**

---

## 🔄 Project Workflow

1. Data Cleaning and Preprocessing  
2. Target Variable Creation  
3. Exploratory Data Analysis (EDA)  
4. Categorical Encoding  
5. Train-Test Split  
6. Base Random Forest Model  
7. Threshold Tuning  
8. SMOTE + Random Forest (Final Model)  
9. Model Evaluation and Comparison  
10. Feature Importance Analysis  

---

## 🔍 Exploratory Data Analysis (EDA)

- Analyzed distribution of **Risky vs Good** classes
- Examined categorical variables against the target
- Used boxplots for numerical feature comparison
- Identified **significant class imbalance**, motivating the use of SMOTE

---

## 🤖 Model Building

- Algorithm used: **Random Forest Classifier**
- Reason:
  - Handles non-linearity well
  - Robust to noise
  - Provides feature importance
  - Performs well with mixed data types

---

## ⚖️ Handling Class Imbalance

The dataset is highly imbalanced, with fewer **Risky** observations.

### Solution Applied:
- **SMOTE (Synthetic Minority Over-sampling Technique)**  
- Applied **only on training data** to avoid data leakage

SMOTE generates synthetic minority samples, allowing the model to better learn risky patterns.

---

## 🧪 Model Evaluation

Evaluation metrics used:
- Precision
- Recall
- F1-score
- Confusion Matrix

### Why Accuracy Is Not Prioritized
In fraud detection:
- Missing a risky case (false negative) is costly
- Higher recall for Risky class is preferred
- Lower accuracy is an acceptable trade-off

---

## 📊 Results Summary

| Model | Accuracy | Risky Recall | Risky F1-score |
|-----|--------|-------------|---------------|
| Base Random Forest | ~76% | ~6% | ~0.10 |
| Threshold Tuned RF | ~55% | ~10% | ~0.08 |
| **SMOTE + Random Forest (Final)** | **~52%** | **~29%** | **~0.20** |

✔ Significant improvement in detecting risky cases  
✔ Model behavior aligns with real-world fraud detection goals  

---

## ⭐ Feature Importance

- Work Experience
- City Population
- Marital Status  

These features contributed most to the final predictions, as observed from the Random Forest feature importance analysis.

---

## ✅ Conclusion

Although the final model achieves a lower overall accuracy, it significantly improves the recall for the risky class. Since fraud detection prioritizes identifying risky cases over maximizing accuracy, the **SMOTE + Random Forest model is considered suitable and effective** for this problem.

---

## 🛠️ Technologies Used

- Python
- NumPy
- Pandas
- Matplotlib
- Seaborn
- Scikit-learn
- Imbalanced-learn (SMOTE)

---

## [📂 Repository Structure](#repository-structure)

```
fraud-risk-detection-random-forest/
│
├── data/
│   └── Fraud_check.csv
│
├── notebooks/
│   └── Fraud_Check_RF.ipynb
│
├── reports/
│   └── Fraud_Check_RF.html
│
├── README.md
└── requirements.txt
```

---

## 👨‍💻 Author & Contact
**Author:** Mohd Walid Ansari  
**Email:** [walidmohd2532001@gmail.com](mailto:walidmohd2532001@gmail.com)  
**GitHub:** [mohdwalid253](https://github.com/mohdwalid253)   
**LinkedIn:** [Mohd Walid Ansari](https://www.linkedin.com/in/mohdwalidansari/)