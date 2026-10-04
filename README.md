# Home-Loan-Default
Machine learning project to home loan default risk using customer financial and credit information, with feature engineering and LightGBM Classification.
🏠 Home Loan Default Prediction

📌 Project Overview

This project focuses on predicting whether a customer is likely to default on a home loan using customer financial, demographic, credit history, and previous loan-related information.

The project uses Machine Learning classification techniques to identify customers who are at higher risk of default.

The dataset contains information from multiple sources, including current customer applications, previous applications, credit bureau records, installment payments, and credit card balances.

---

🎯 Objective

The main objective of this project is to build a machine learning model that can predict home loan default risk.

The model can help financial institutions:

- Identify customers who may be at higher risk of default.
- Assess credit risk before approving loans.
- Make more informed lending decisions.
- Reduce potential financial losses.
- Improve the overall loan approval process.

---

🗂️ Dataset

The project uses multiple datasets containing information about customers and their credit history.

The main datasets are:

application_train
bureau
bureau_balance
previous_application
installments_payments
POS_CASH_balance
credit_card_balance

Main Application Dataset

The "application_train" dataset contains information about the current loan applicants.

The target variable is:

"TARGET"

TARGET| Meaning
0| Customer did not default
1| Customer defaulted

The dataset contains a relatively small proportion of defaulters, making this an imbalanced classification problem.

---

📊 Dataset Split

A stratified 70/15/15 split was used:

Dataset| Rows
Training| 215,257
Validation| 46,127
Test| 46,127

The target default rate was approximately 8.07%.

Stratification was used to maintain a similar proportion of defaulters and non-defaulters across the datasets.

---

🔍 Exploratory Data Analysis

Exploratory Data Analysis was performed to understand customer characteristics and identify important patterns related to loan default.

The analysis included:

- Dataset dimensions
- Data types
- Missing-value analysis
- Target distribution
- Numerical feature analysis
- Categorical feature analysis
- Correlation analysis
- Credit history analysis
- Employment and demographic information

---

🧹 Data Preprocessing

Several preprocessing steps were performed before model development.

These included:

- Handling missing values
- Examining categorical variables
- Encoding categorical features
- Removing or handling problematic values
- Combining information from related datasets
- Creating useful financial and demographic features
- Stratified train/validation/test splitting

---

⚙️ Feature Engineering

Additional features were created to improve the model's ability to understand customer financial profiles.

Examples include:

Age

The "DAYS_BIRTH" variable was converted into an easier-to-understand age-related feature:

AGE_YEARS

Employment Duration

Employment-related information was transformed into:

EMPLOYED_YEARS

DAYS_EMPLOYED

A special sentinel value, "365243", was identified and handled appropriately because it represents an anomalous/missing employment duration rather than a realistic number of days employed.

---

🏦 Additional Credit Information

The model was improved by incorporating information from other financial datasets.

These included:

- Bureau data
- Previous application data
- Installment payment data
- POS Cash balance data
- Credit card balance data

Combining these sources provided a more complete view of the customer's credit and repayment history.

---

🤖 Machine Learning Model

LightGBM

LightGBM was used as the primary classification algorithm because it performs well on large tabular datasets and can efficiently handle many features.

The model was trained using class-imbalance handling.

The training data contained substantially fewer defaulters than non-defaulters, so "scale_pos_weight" was used to give greater importance to the minority class.

The approximate value used was:

scale_pos_weight = 11.39

---

📈 Model P
