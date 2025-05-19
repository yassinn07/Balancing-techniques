# Credit Card Fraud Detection

A comprehensive analysis of credit card fraud using Logistic Regression, with a focus on handling imbalanced datasets.

---

## 📊 Dataset Overview

- **Source:** `creditcard.csv`
- **Shape:** `(284807, 31)`
- **Missing Values:** None

### Class Distribution

- **Non-Fraud (0):** 284,315
- **Fraud (1):** 492
- **Fraud Percentage:** ~0.1727%

⚠️ **Note:** The dataset is highly imbalanced.

---

## 🔧 Data Preprocessing

- **Scaling:** `Amount` and `Time` features were standardized using `StandardScaler`.
- **Dropped:** Original `Amount` and `Time` columns.
- **Train/Test Split:** 80/20 with stratification to preserve class ratios.

---

## 🧠 Model Training & Evaluation

### A. Logistic Regression on Original Data

- **Accuracy:** ~99.38%
- **Precision (Fraud):** ~0.88
- **Recall (Fraud):** ~0.59
- **F1-Score (Fraud):** ~0.70

📌 High accuracy, but poor recall. Many fraudulent transactions were not detected.

---

### B. Random Oversampling

- **Accuracy:** ~97.24%
- **Precision (Fraud):** ~0.07
- **Recall (Fraud):** ~0.91
- **F1-Score (Fraud):** ~0.14

📌 Better recall but significantly worse precision. Many false positives.

---

### C. Random Undersampling

- **Accuracy:** ~97.65%
- **Precision (Fraud):** ~0.08
- **Recall (Fraud):** ~0.88
- **F1-Score (Fraud):** ~0.15

📌 Similar to oversampling in trade-offs.

---

### D. SMOTE (Synthetic Minority Over-sampling Technique)

- **Accuracy:** ~97.62%
- **Precision (Fraud):** ~0.08
- **Recall (Fraud):** ~0.89
- **F1-Score (Fraud):** ~0.15

📌 SMOTE provides the best balance in recall without major drops in other metrics.

---

## 📈 Visualizations

- **Class Distribution:** Plotted using Seaborn's `countplot`.
- **Correlation Matrix:** Heatmap to analyze PCA components vs. target.
- **Confusion Matrices:** Plotted for each sampling method to visualize model performance.

---

## ✅ Conclusions

- The extreme class imbalance poses challenges for conventional models.
- **Recall** is more critical than precision in fraud detection.
- **SMOTE** yielded the most balanced improvement in detecting fraudulent transactions.

---
