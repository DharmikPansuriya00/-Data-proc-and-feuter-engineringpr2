# 🏥 Patient Health Data Cleaning & Preprocessing Project

## 📌 Overview

This project focuses on **data cleaning and preprocessing** of a patient health dataset.
The main objective is to handle:

* Missing values
* Outliers
* Data inconsistencies

The final dataset is prepared for **machine learning and data analysis tasks**.

---

## 📂 Dataset Features

| Column         | Description                 |
| -------------- | --------------------------- |
| patient_id     | Unique patient identifier   |
| age            | Age of patient              |
| gender         | Male / Female               |
| region         | North / South / East / West |
| bmi            | Body Mass Index             |
| blood_pressure | Systolic BP (mmHg)          |
| cholesterol    | Cholesterol level (mg/dL)   |
| glucose        | Glucose level (mg/dL)       |
| disease_risk   | Target (0 = Low, 1 = High)  |

---

# 🧹 Part A: Handling Missing Values

## 🔍 Missing Value Analysis

* Identified missing values using `.isnull()`
* Calculated percentage per column

## 🛠️ Imputation Techniques Used

### 1. Simple Imputer (Numerical)

* BMI → Median (robust to outliers)

### 2. Simple Imputer (Categorical)

* Region → Most frequent value

### 3. Most Frequent Imputation

* Gender → Mode

### 4. Missing Indicator + Random Sampling

* Created indicator columns (e.g., `bmi_missing`)
* Filled using random sampling

### 5. KNN Imputer

* Used nearest neighbors for multivariate imputation

### 6. MICE (Iterative Imputer) ✅

* Applied on numerical features
* Most effective method

---

# 📊 Part B: Handling Outliers

## 🔎 Detection Methods

### 1. Z-Score Method

* Applied on: Cholesterol, Glucose
* Threshold: ±3

### 2. IQR Method

* Applied on: BMI

### 3. Percentile Method

* Used 1st–99th percentile capping

---

## ⚙️ Winsorization (Final Method) ✅

* Applied on: Glucose
* Limits: 5%–95%

✔ Keeps dataset size unchanged
✔ Reduces extreme values

---

## 📈 Before vs After Comparison

| Metric   | Before               | After                |
| -------- | -------------------- | -------------------- |
| Outliers | Present ❌            | Controlled ✅         |
| Std Dev  | High                 | Reduced ✅            |
| Mean     | Skewed               | Stable ✅             |
| Rows     | Changed (if removed) | Same (winsorization) |

---

# 📌 Part C: Final Clean Dataset

## ✅ Final Steps Performed

* Missing values → handled using **MICE + Mode**
* Outliers → handled using **Winsorization**
* Dataset → fully cleaned

---

## 📊 Final Dataset Status

| Aspect         | Status       |
| -------------- | ------------ |
| Missing Values | Removed ✅    |
| Outliers       | Controlled ✅ |
| Data Quality   | Improved ✅   |
| ML Ready       | Yes 🚀       |

---

# 🧠 Key Insights

## 🔹 Best Imputation Strategy

👉 **MICE (Iterative Imputer)**

* Uses relationships between variables
* Most accurate approach

---

## 🔹 Best Outlier Method

👉 **Winsorization**

* Preserves data
* Reduces extreme values

---

## 🔹 Improvements Achieved

* Clean and complete dataset
* Reduced noise and variance
* Improved statistical stability
* Ready for ML models

---

# 🚀 How to Run

```bash
pip install pandas numpy scikit-learn scipy
```

```python
python your_script.py
```

---

# 📁 Project Structure

```
📦 patient-health-project
 ┣ 📜 dataset.csv
 ┣ 📜 preprocessing.py
 ┣ 📜 README.md
```

---

# 🎯 Conclusion

This project demonstrates a complete **data preprocessing pipeline**, including:

* Advanced imputation (MICE)
* Outlier handling (Z-score, IQR, Winsorization)
* Data validation and comparison

👉 The final dataset is **clean, reliable, and ready for machine learning applications**.

---

# 💡 Interview Answer

> "I used MICE for handling missing values and Winsorization for outlier treatment to ensure both accuracy and data integrity."

---
