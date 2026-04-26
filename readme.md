# 💰 CreditWise: Multi-Model Loan Approval Prediction


## 📌 Project Overview
CreditWise is a machine learning benchmark project designed to automate credit risk assessment. The project implements and compares three different classification algorithms—**Logistic Regression, K-Nearest Neighbors (KNN), and Gaussian Naive Bayes**—to identify the most reliable model for predicting loan eligibility based on financial indicators like CIBIL score, income, and assets.

## 🚩 The Problem Statement
Manual loan processing is time-consuming and carries the risk of financial loss due to "False Positives" (approving risky loans). This project aims to:
1. **Automate Decisioning:** Provide instant feedback on loan eligibility.
2. **Minimize Risk:** Optimize for high Precision to ensure approved loans are highly likely to be repaid.
3. **Model Benchmarking:** Determine which statistical approach handles financial feature distributions most effectively.

## 📊 Dataset Overview
The project utilizes `loan_approval_data.csv`, a comprehensive dataset containing financial and demographic profiles of loan applicants.

### Data Dictionary
| Feature | Type | Description |
| :--- | :--- | :--- |
| **Applicant_Income** | Numerical | Monthly income of the primary applicant. |
| **Credit_Score** | Numerical | CIBIL rating (300-900). The strongest predictor in our model. |
| **DTI_Ratio** | Numerical | Debt-to-Income ratio, used to assess repayment capacity. |
| **Education_Level** | Categorical | Graduate vs. Not Graduate status. |
| **Loan_Approved** | Binary | **Target Variable:** (Yes/No) indicating the final decision. |

### Data Statistics
* **Total Records:** 994 applications
* **Feature Count:** 20 columns (Financial, Personal, and Employment data)
* **Target Distribution:** Analyzed for class balance to ensure model fairness.

### Key Features:
* **Applicant_Income:** The primary monthly/annual income of the applicant.
* **Credit_Score:** The CIBIL rating (Range: 300-900). This is the most significant predictor.
* **Loan_Amount:** The total credit requested.
* **Loan_Term:** The duration (in months) for repayment.
* **Loan_Approved:** The target variable we are predicting (Yes/No).

## 📊 Performance Comparison
After rigorous testing and data scaling, the models yielded the following results:

| Algorithm | Accuracy | Precision | Recall | F1-Score |
| :--- | :---: | :---: | :---: | :---: |
| **Gaussian Naive Bayes** | **86.0%** | **0.81** | 0.70 | **0.75** |
| Logistic Regression | 82.0% | 0.78 | 0.68 | 0.72 |
| K-Nearest Neighbors | 79.5% | 0.74 | 0.65 | 0.69 |

### **Key Insight:**
**Gaussian Naive Bayes** emerged as the winning model. In banking, the cost of a defaulted loan is much higher than the cost of a missed opportunity. Therefore, we prioritized the **0.81 Precision** of Naive Bayes to ensure a lower rate of risky approvals.

## 🛠️ Technical Workflow
* **Exploratory Data Analysis (EDA):** Visualized feature correlations using Seaborn heatmaps.
* **Preprocessing:** * Handled categorical variables via One-Hot Encoding.
  * Applied `StandardScaler` to normalize features
* **Model Selection:** Evaluated models using Confusion Matrices to analyze Type I and Type II errors.

## 📁 Repository Structure
```text
├── credit_wise.ipynb      # Complete analysis & comparative study
├── loan_approval_data.csv   # Dataset (Income, CIBIL, Assets, etc.)
├── requirements.txt        # Dependency list for environment setup
└── README.md               # Project documentation