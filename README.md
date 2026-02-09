# 📉 Jio Customer Churn Analysis Project

## 📌 Project Objective
Customer retention is critical in the telecom industry. This project analyzes Jio customer data to identify **why** customers leave (churn) and builds a Machine Learning model to **predict** churn before it happens. The goal is to provide actionable insights to reduce the 26.5% churn rate.

## ⚙️ Tech Stack
* **Python** (Pandas, NumPy)
* **Machine Learning** (Scikit-Learn, Imbalanced-Learn/SMOTE)
* **Visualization** (Matplotlib, Seaborn)

## 📊 Key Business Insights (EDA)
My analysis of the customer data revealed four major drivers of churn:
1.  **Contract Type:** Customers on **Month-to-Month contracts** are the highest risk group. Long-term (2-year) contracts have almost zero churn.
2.  **Payment Method:** **"Electronic Check"** users churn at a significantly higher rate than Credit Card or Bank Transfer users.
3.  **Tenure:** The first **12 months** are the "danger zone." If a customer stays past 1 year, they are likely to remain loyal.
4.  **Pricing:** Customers with **higher monthly charges** are more likely to leave, indicating price sensitivity.

## 🧠 Machine Learning Approach
I built and compared models to predict churn, focusing on **Recall** (the ability to catch actual churners) rather than just Accuracy.

### 1. Data Processing
* Cleaned missing values in `TotalCharges`.
* Converted categorical variables using **Label Encoding** and **One-Hot Encoding**.
* Scaled numerical features (`Tenure`, `MonthlyCharges`) for model stability.

### 2. Handling Imbalance (Critical Step)
The dataset was imbalanced (74% Non-Churn vs. 26% Churn), causing standard models to miss potential churners.
* **Solution:** I used **SMOTE (Synthetic Minority Over-sampling Technique)** to balance the training data.
* **Result:** This forced the model to learn the characteristics of churners, significantly improving detection rates.

## 📈 Final Model Results

| Model | Recall (Churners Detected) | Accuracy | Verdict |
| :--- | :--- | :--- | :--- |
| **Logistic Regression (Base)** | 59% | 82% | Misses too many churners. |
| **Random Forest** | 47% | 79% | Poor performance on this data. |
| **Logistic Regression + SMOTE** | **71%** | **76%** | **✅ Best Model** |

**Conclusion:** The SMOTE-enhanced Logistic Regression model is the best choice. It successfully identifies **71% of at-risk customers**, allowing the business to intervene.

## 💡 Strategic Recommendations
Based on the data, the following actions are recommended to reduce churn:
1.  **Contract Push:** Offer incentives for month-to-month users to switch to 1-year or 2-year contracts.
2.  **Payment Update:** Give a discount for switching from Electronic Check to AutoPay (Credit Card).
3.  **Targeted Retention:** Use this model to identify "high-risk" customers and offer them special deals before they cancel the plan.
---
*Project developed by Ansh Rathod*
