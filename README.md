Credit Card Fraud Detection Analysis Report

1. Dataset Overview

The dataset was successfully loaded from creditcard.csv, with shape (284807, 31) and no missing values.

Class Distribution:

Non-Fraud (0): 284315

Fraud (1): 492

Fraud Percentage: ~0.1727% — highlighting significant class imbalance.

2. Data Preprocessing

Scaling: Amount and Time features were standardized using StandardScaler, and the original columns were dropped.

Split: Data was split into training (80%) and testing (20%) sets using stratification.

3. Model Training and Evaluation

A. Original Unbalanced Data

Model: Logistic Regression

Results:

Accuracy: ~99.38%

Precision (Fraud): ~0.88

Recall (Fraud): ~0.59

F1-Score (Fraud): ~0.70

Observation: High accuracy but relatively low recall indicates many fraudulent transactions were missed.

B. Random Oversampling

Results:

Accuracy: ~97.24%

Precision (Fraud): ~0.07

Recall (Fraud): ~0.91

F1-Score (Fraud): ~0.14

Observation: Significant improvement in recall at the cost of precision. Many non-fraud transactions misclassified.

C. Random Undersampling

Results:

Accuracy: ~97.65%

Precision (Fraud): ~0.08

Recall (Fraud): ~0.88

F1-Score (Fraud): ~0.15

Observation: Similar to oversampling. Recall improves but precision suffers.

D. SMOTE (Synthetic Minority Over-sampling Technique)

Results:

Accuracy: ~97.62%

Precision (Fraud): ~0.08

Recall (Fraud): ~0.89

F1-Score (Fraud): ~0.15

Observation: SMOTE leads to slightly better recall compared to ROS and RUS.

4. Visualizations

Class Distribution: Visualized using seaborn countplots.

Correlation Matrix: Large heatmap provided insights into relationships between PCA components and target variable.

Confusion Matrices: Plotted for each sampling strategy using seaborn.heatmap to highlight classification errors.

5. Conclusions

The dataset is highly imbalanced, making it challenging for traditional models.

Logistic Regression on the original data had poor recall despite high accuracy.

SMOTE showed the best balance in metrics among resampling methods, particularly increasing recall substantially.

For real-world fraud detection, recall is crucial — better to flag more frauds even if some false positives occur.
