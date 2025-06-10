# 📄 About the Dataset

**Description:**  
This dataset contains credit card transactions made by **European cardholders in 2013**. It includes over **284,807 anonymized records**, specifically prepared to support the development of **fraud detection** algorithms. All sensitive information has been transformed or removed to ensure **user privacy** and **ethical compliance**.

---

### 🔑 Key Features

- **`V1` – `V28`**: Numerical features generated through **Principal Component Analysis (PCA)**  
- **`Amount`**: The transaction amount in currency units  
- **`Time`**: Seconds elapsed since the first transaction in the dataset  
- **`Class`**: Target label  
  - `0` → Legitimate transaction  
  - `1` → Fraudulent transaction  

---

### 🔍 What is PCA?

**Principal Component Analysis (PCA)** is a dimensionality reduction technique that:
- Projects high-dimensional data onto new axes (called **principal components**)
- Captures the **directions of maximum variance**
- Produces **uncorrelated**, privacy-safe features

In this dataset:
- `V1` captures the most variance  
- `V2` captures the second most  
- ...up to `V28`, which captures the least  

This transformation retains the **most critical data patterns** while anonymizing original attributes like merchant, location, or device.

---
## 🧠 Initial Data Insights

- The dataset contains **no missing values**, so imputation is unnecessary.  
- Only `Amount` and `Time` are **not PCA-transformed**; the remaining features (`V1`–`V28`) are numerical principal components derived from **PCA**, each representing transformed variance directions.
- The **average transaction amount** is approximately **88 units** (currency unspecified).
- The dataset is **highly imbalanced**:
  - ✅ **99.83%** are **legitimate transactions**
  - ⚠️ Only **0.17%** are labeled as **fraudulent**

> ⚠️ Because of this imbalance, traditional metrics like accuracy can be misleading. We'll focus on **precision, recall**, and **AUC-PR** to evaluate model performance.

---


### 📦 Data Source

This dataset was collected from real-world credit card transactions and prepared for public research by anonymizing all sensitive fields in accordance with **privacy laws** and **ethical guidelines**.
> 📚 **Citation**:  
> Andrea Dal Pozzolo, Olivier Caelen, Reid A. Johnson, Gianluca Bontempi. *Calibrating Probability with Undersampling for Unbalanced Classification*. In Symposium on Computational Intelligence and Data Mining (CIDM), 2015.  
> [Kaggle Dataset - Credit Card Fraud Detection](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)

---

## 🎯 Project Objective

Build a machine learning model to classify credit card transactions as **fraudulent (`1`)** or **legitimate (`0`)**, using historical data to accurately detect suspicious activity with high recall and minimal false positives.

---

> 💡 If running locally outside Colab, install KaggleHub using:
```bash
pip install kagglehub
