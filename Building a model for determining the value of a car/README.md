# Used Car Price Prediction

## Project Description

The "Not beaten, not painted" used car sales service is developing an application to help customers estimate the market value of their cars. This project aims to build a model that can accurately determine a car's market value based on technical specifications, features, and prices of other vehicles.

### Customer Requirements:
- Prediction quality
- Model training time
- Model prediction time

## Dataset Overview

The dataset contains 354,369 records with the following features:
- DateCrawled
- Price
- VehicleType
- RegistrationYear
- Gearbox
- Power
- Model
- Kilometer
- RegistrationMonth
- FuelType
- Brand
- Repaired
- DateCreated
- NumberOfPictures
- PostalCode
- LastSeen

Initial analysis revealed:
- Large number of missing values
- Presence of anomalous data (e.g., registration year 1000 or 9999, zero price, zero power)
- Technical characteristics, equipment, and price information

## Data Preprocessing

### Handling Missing Values
- Missing values were filled with either:
  - Most frequent values in their category
  - 'unknown' when data couldn't be reasonably reconstructed

### Anomaly Removal
- Removed records with:
  - Registration year above current year
  - Zero power
  - Zero price
- Eliminated irrelevant data that wouldn't affect model training

### Data Splitting
The cleaned dataset was split into:
- Training set (70%)
- Validation set (15%)
- Test set (15%)

## Model Training

Two models were trained and evaluated:

### 1. Linear Regression
- Faster training time
- Poorer RMSE performance

### 2. LightGBM
- Slower training time
- Superior RMSE performance
- Hyperparameter tuning performed

## Results

| Model          | Training Speed | RMSE Score |
|----------------|----------------|------------|
| LinearRegression | Faster         | Higher     |
| LightGBM        | Slower         | 1620       |

The LightGBM model was selected as the final model due to its significantly better prediction quality, achieving an RMSE of 1620 on the test set.

## Key Findings

1. The dataset required extensive preprocessing due to missing values and anomalies
2. LightGBM outperformed Linear Regression in prediction accuracy despite longer training time
3. The final model meets the customer's requirements for prediction quality while maintaining reasonable training and prediction times

## Libraries Used
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- LightGBM
- CatBoost
- missingno
