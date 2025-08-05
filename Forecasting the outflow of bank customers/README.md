# Customer Churn Prediction for Beta-Bank

## Project Description
This project focuses on predicting customer churn for **Beta-Bank**. The bank has noticed a gradual but significant loss of customers each month. Marketing analysts have determined that retaining existing customers is more cost-effective than acquiring new ones.  

**Goal**: Build a machine learning model that predicts whether a customer will leave the bank soon, using historical data on customer behavior and contract terminations.  

**Primary Evaluation Metric**: F1-score, with a target of at least **0.59**.

---

## Dataset Overview
The dataset contains the following features:  

| Feature          | Description |
|------------------|-------------|
| RowNumber        | Row index. |
| CustomerId       | Unique customer identifier. |
| Surname          | Customer's last name. |
| CreditScore      | Credit score of the customer. |
| Geography        | Customer's country. |
| Gender           | Customer's gender. |
| Age              | Customer's age. |
| Tenure           | Number of years the customer has been with the bank. |
| Balance          | Account balance. |
| NumOfProducts    | Number of bank products used by the customer. |
| HasCrCard        | Whether the customer has a credit card (1 = yes, 0 = no). |
| IsActiveMember   | Whether the customer is an active member (1 = yes, 0 = no). |
| EstimatedSalary  | Estimated salary of the customer. |
| Exited           | Whether the customer left the bank (1 = yes, 0 = no). |

### Key Observations:
- The dataset has **10,000 entries**.
- The **Tenure** column contains missing values (about **9%**).
- The target variable **Exited** is imbalanced, with only **20%** of customers having churned.

---

## Data Preprocessing
1. **Handling Missing Values**:  
   - Missing values in the **Tenure** column were filled with the median value.  

2. **Feature Engineering**:  
   - Dropped irrelevant columns: `RowNumber`, `CustomerId`, `Surname`.  
   - One-hot encoded categorical variables (`Geography` and `Gender`).  

3. **Train-Validation-Test Split**:  
   - Split into **70% training**, **15% validation**, and **15% test** sets.  

4. **Scaling**:  
   - Features were standardized using `StandardScaler`.  

---

## Model Training and Evaluation
Three models were trained and evaluated:  

| Model               | F1-Score | ROC-AUC |
|---------------------|----------|---------|
| Logistic Regression | 0.25     | 0.77    |
| Decision Tree       | 0.52     | 0.70    |
| Random Forest       | **0.58** | **0.85** |

### Addressing Class Imbalance
To improve performance on the imbalanced dataset, the following techniques were applied:  
- **Class Weight Adjustment**: Used `class_weight='balanced'` in the models.  

**Results After Balancing**:  

| Model               | F1-Score | ROC-AUC |
|---------------------|----------|---------|
| Logistic Regression | 0.50     | 0.77    |
| Decision Tree       | 0.53     | 0.70    |
| Random Forest       | **0.63** | **0.86** |

---

## Results
The **best-performing model** was the **Random Forest with balanced class weights**, achieving:  
- **F1-score: 0.63**  
- **ROC-AUC: 0.86**  
