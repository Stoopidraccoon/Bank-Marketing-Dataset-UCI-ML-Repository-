# Bank-Marketing-Dataset-UCI-ML-Repository-
Bank Marketing Term Deposit Prediction using Power BI (EDA), Logistic Regression, Random Forest, and SHAP for explainability.

**Objective**

Predict whether a bank customer will subscribe to a term deposit as a result of a marketing campaign.

**Dataset**

Source: UCI Machine Learning Repository – Bank Marketing Dataset

Features: Customer demographics, financial status, and marketing campaign details

Target Variable: deposit_yes (1 = Subscribed, 0 = Not Subscribed)

**Exploratory Data Analysis (EDA) – Power BI Dashboard**

To understand customer behavior, a Loan Acceptance Dashboard was built in Power BI.

**Key Observations**

- By Job: Management and blue-collar workers dominate customer groups.

- By Education: Secondary and tertiary education are the most common backgrounds.

- By Marital Status: Married clients form the largest group, followed by singles.

- By Housing Loan: Customers without housing loans show higher acceptance rates.

- By Age: Deposits are most common among customers aged 30–40.

Overall: A significant imbalance exists between customers who said No vs Yes, confirming this as a class imbalance problem.

**Modeling Approach (Python)**

Two models were trained and compared:

- Logistic Regression 

- Random Forest Classifier 

**Preprocessing**
- Encoded categorical features using one-hot encoding

- Dropped low-importance features based on Random Forest feature importance

- Handled class imbalance using class_weight='balanced'

# Model Evaluation

**=== Random Forest Evaluation ===**
Accuracy: **82.84818629646216**

**Confusion Matrix**
 [[948 215]
 [168 902]]

 F1 Score: **82.48742569730224**

**Classification Report**
               precision    recall  f1-score   support

       False       0.85      0.82      0.83      1163
        True       0.81      0.84      0.82      1070

    accuracy                           0.83      2233
   macro avg       0.83      0.83      0.83      2233
weighted avg       0.83      0.83      0.83      2233

**=== Logistic Regression Evaluation ===**
Accuracy: **79.44469323779668**

F1 Score: **77.8153697438376**

**Confusion Matrix**
 [[969 194]
 [265 805]]

**Classification Report**
               precision    recall  f1-score   support

       False       0.79      0.83      0.81      1163
        True       0.81      0.75      0.78      1070

    accuracy                           0.79      2233
   macro avg       0.80      0.79      0.79      2233
weighted avg       0.80      0.79      0.79      2233

**ROC Curve Comparison**

Both models were compared using ROC-AUC:

Random Forest achieved higher AUC compared to Logistic Regression.

ROC curves clearly show Random Forest as the stronger model.

# Explainable AI (SHAP Analysis)
**Global Feature Importance**

- Call Duration: Strongest driver — longer calls increase subscription probability.

- Previous Campaign Success: Strongly positive influence on outcomes.

- Balance: Higher balances slightly increase likelihood of subscription.

- Housing Loan: Having a housing loan decreases probability.

- Recency (pdays): Longer time since last contact reduces effectiveness.

**Local Explanations**

For 5 individual customers, SHAP explained why the model predicted Yes or No.

Example: A customer with long duration and high balance was predicted “Yes.”

Example: A customer with a housing loan and long pdays gap was predicted “No.”

**Business Insights**

- Invest in call duration: Longer, meaningful conversations increase deposit acceptance.

- Leverage past success: Customers who subscribed before are highly likely to subscribe again.

- Target financially stable customers: Higher balances are linked with higher acceptance.

- Re-contact sooner: Avoid long gaps (pdays) to maintain customer interest.

- Segment by loans: Customers with housing loans may be less responsive and need different messaging.
