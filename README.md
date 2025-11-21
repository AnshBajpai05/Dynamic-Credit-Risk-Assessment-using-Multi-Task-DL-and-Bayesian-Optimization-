# **Dynamic Credit Risk Probability Estimation – Student Project README**

This project builds a **credit risk probability model** using real-world financial datasets.
It follows a full ML pipeline: **data loading → cleaning → feature engineering → modeling → evaluation → final probability prediction**, all implemented inside the notebook *prob_project_final.ipynb*.

The goal is to **predict the probability that a customer will default**, based on past credit behavior recorded across multiple related datasets.

---

# ⭐ **1. Project Objective**

Many financial institutions maintain multiple records of a customer: loan history, credit card statements, previous applications, bureau data, etc.
The objective of this project is to:

✔ Combine these datasets
✔ Clean & preprocess them
✔ Engineer meaningful features
✔ Build a predictive model
✔ Estimate **default probability** for each applicant

This helps banks decide:

* Whether a loan applicant is risky
* What interest rate to offer
* Whether to approve or reject credit

---

# 📂 **2. Datasets Used (from the Notebook)**

The notebook uses the following datasets(https://www.kaggle.com/competitions/home-credit-default-risk/overview):

| Dataset Name              | File Used                   | Description                              |
| ------------------------- | --------------------------- | ---------------------------------------- |
| **Application Data**      | `application_train.csv`     | Main customer info + target column       |
| **Bureau Data**           | `bureau.csv`                | Credit history from other lenders        |
| **Bureau Balance**        | `bureau_balance.csv`        | Monthly bureau status                    |
| **Previous Applications** | `previous_application.csv`  | Past loan applications                   |
| **POS Cash Balance**      | `POS_CASH_balance.csv`      | Point-of-sale monthly behavior           |
| **Installments Payments** | `installments_payments.csv` | Loan installment details                 |
| **Credit Card Balance**   | `credit_card_balance.csv`   | Transactions & monthly credit card usage |

These are merged or aggregated to create a feature-rich dataset.

---

# 🔧 **3. Preprocessing Steps**

The notebook performs the following cleaning and preparation tasks:

### ✔ Handling Missing Values

* Dropped columns with extremely high missing values
* Imputed remaining missing fields with median/mode

### ✔ Encoding Categorical Variables

* Used **Label Encoding** for binary categories
* Used **One-Hot Encoding** for categorical variables with multiple values

### ✔ Outlier Removal

* Identified unrealistic values (e.g., negative income)
* Removed or capped extreme outliers

### ✔ Feature Engineering

Some examples from the notebook:

* Debt / Income ratio
* Credit utilization ratio
* Number of past loans
* Total days employed
* Average monthly balance from credit card data
* Aggregations from bureau and POS cash datasets

These features help the model learn customer financial behavior more accurately.

---

# 📊 **4. Exploratory Data Analysis (EDA)**

The notebook includes many visualizations, such as:

* Distribution of key financial features
* Histogram of income
* Correlation heatmaps
* Target variable distribution
* Probability plots
* Boxplots comparing defaulters vs non-defaulters

This helps understand:

* Which features influence risk
* How values differ between good vs bad borrowers
* Data skewness and scale differences

---

# 🤖 **5. Modeling Approach**

The notebook builds a **classification model** to predict the probability of default (`TARGET = 1` means default).

### Models used in the notebook:

* **Logistic Regression**
* **Random Forest Classifier**
* **XGBoost / LightGBM**
* **Train-test split**
* **Hyperparameter tuning**

The final model outputs a **auc between 0–1**, which indicates how risky a borrower is.

---

# 📈 **6. Evaluation Metrics**

The notebook evaluates models using:

* **Accuracy**
* **Precision / Recall**
* **F1 Score**
* **ROC Curve**
* **AUC Score**
* **Confusion Matrix**

AUC is the most important metric for credit scoring.

Higher AUC = better separation between risky and safe borrowers.

---

# 🔮 **7. Final Prediction Output**

The final section of the notebook generates:

* Probability of default for each applicant
* Sorted risk table
* Visualization of predicted probabilities

The model can be used to:

* Reject high-risk applicants
* Approve low-risk applicants
* Assign interest rates dynamically

---

# ▶️ **8. How to Run the Project**

### **1. Install Dependencies**

```bash
pip install -r requirements.txt
```

### **2. Open the notebook**

```
prob_project_final.ipynb
```

### **3. Run all cells in order**

This will:

* Load datasets
* Clean and preprocess data
* Train models
* Evaluate performance
* Output probability predictions

---

# 🧪 **9. Results Summary**

Based on the notebook analysis:

* Engineered features significantly improve accuracy
* Trend-based features from credit card & bureau data helped prediction
* The final model achieves **good performance (AUC shown in notebook)**
* Probability outputs are well-calibrated
---

# 🎓 **10. Conclusion**

This project demonstrates how to build a full credit scoring system using machine learning.
It covers all stages of a real data science pipeline:

* Understanding multiple financial datasets
* Cleaning & merging
* Feature engineering
* Interpreting EDA
* Training ML models
* Generating probability-based output

It is fully reproducible using the provided notebook.

