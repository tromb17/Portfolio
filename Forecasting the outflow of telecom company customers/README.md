# Telecom Customer Churn Prediction Project

## Project Description

The telecom operator aims to predict customer churn. If a user is identified as likely to leave, they will be offered promotional codes and special conditions. The operator's team has collected personal data about some customers, including information about their tariffs and contracts.

### Services Provided by the Operator
- **Fixed-line telephone service**: Possible to connect multiple lines simultaneously.
- **Internet**: Two types of connections:
  - DSL (Digital Subscriber Line) via telephone line.
  - Fiber optic cable.
- Additional services:
  - Internet security: Antivirus (DeviceProtection) and unsafe website blocking (OnlineSecurity).
  - Dedicated technical support line (TechSupport).
  - Cloud file storage for data backup (OnlineBackup).
  - Streaming TV (StreamingTV) and movie catalog (StreamingMovies).

Customers can pay monthly or sign contracts for 1–2 years. Various payment methods and electronic receipts are available.

## Data Analysis

### DataFrames Overview
The project uses four DataFrames:
1. **Contract**: Contains contract details (start/end dates, type, billing, payment method, charges).
2. **Internet**: Includes internet service details (service type, security, backup, etc.).
3. **Personal**: Holds personal customer data (gender, age, dependents, etc.).
4. **Phone**: Contains phone service details (multiple lines, etc.).

### Key Findings
- **Contract DataFrame**: 
  - Columns like `TotalCharges` and `BeginDate` require type conversion (to float and datetime, respectively).
  - Monthly charges are most frequently in the range of 18–35.
- **Internet DataFrame**: 
  - Some services were unused, leading to fewer entries in certain columns.
- **Personal and Phone DataFrames**: 
  - Contain demographic and service usage details.

## Data Preprocessing
1. **Handling Data Types**:
   - Converted `TotalCharges` to float.
   - Changed `BeginDate` to datetime.
2. **Target Feature**:
   - Created a column indicating whether a customer is still active or has churned.
3. **New Feature**:
   - Added "customer lifetime duration."
4. **Time-Based Features**:
   - Removed time-related columns.
5. **Merging DataFrames**:
   - Combined tables using the `customerID` column.
6. **Missing Values**:
   - Filled missing values with `'not_used'` after merging.
7. **Train-Test Split**:
   - Split the data into training and test sets.

## Model Selection and Training
### Models Used
1. **Logistic Regression**
2. **Random Forest Classifier**
3. **CatBoost Classifier**

### Pipeline Steps
1. **Feature Scaling and Encoding**:
   - Applied scaling and one-hot encoding to prepare features.
2. **Hyperparameter Tuning**:
   - Used `GridSearchCV` to optimize hyperparameters.
3. **Model Evaluation**:
   - Evaluated models using the `roc_auc` metric on the training set.

### Results
- **Best Model**: CatBoostClassifier achieved the highest ROC_AUC score of **0.906** on the training set.
- **Test Set Performance**: ROC_AUC of **0.896**, meeting the project requirements.

### Final Model
- **Model**: `CatBoostClassifier()`
- **Hyperparameters**:
  - `depth = 3`
  - `iterations = 200`
  - `learning_rate = 1.0`
- **Features Used**:
  - `['Type', 'PaperlessBilling', 'PaymentMethod', 'InternetService', 'OnlineSecurity', 'OnlineBackup', 'DeviceProtection', 'TechSupport', 'StreamingTV', 'StreamingMovies', 'gender', 'SeniorCitizen', 'Partner', 'Dependents', 'MultipleLines', 'duration', 'MonthlyCharges']`

## Conclusion
The project successfully preprocessed the data, trained multiple models, and selected the best-performing one (CatBoostClassifier) to predict customer churn. The model's performance on the test set (ROC_AUC = 0.896) demonstrates its effectiveness in identifying potential churners, enabling targeted retention strategies.
