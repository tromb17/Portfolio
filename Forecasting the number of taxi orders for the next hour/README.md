# Taxi Order Forecasting

## Project Description

The company "Clear Taxi" has collected historical data on taxi orders at airports. To attract more drivers during peak demand periods, it is necessary to forecast the number of taxi orders for the next hour. The goal is to build a predictive model for this task. The RMSE metric on the test set should not exceed 48.

## Data Analysis

### Data Overview
- The dataset contains 4416 rows of hourly taxi order data.
- The average number of orders per hour is 84, with a median of 78.

### Key Observations
- **Trend Analysis**: The data shows an increasing trend in the number of orders over time.
- **Seasonality**: 
  - Orders peak around midnight.
  - Orders decrease significantly by 6 AM, likely due to the availability of public transport.

### Data Preprocessing
- The data was resampled to 1-hour intervals.
- Additional features were created for model training.
- The dataset was split into training (80%), validation (10%), and test (10%) sets.

## Model Training and Evaluation

### Models Tested
1. **LinearRegression**
2. **RandomForestRegressor**
3. **CatBoost**
4. **LightGBM**

### Results on Validation Set
| Model                  | RMSE  |
|------------------------|-------|
| LinearRegression       | 29.01 |
| RandomForestRegressor  | 29.82 |
| CatBoost               | 30.36 |
| LightGBM               | 29.42 |

### Best Model
- **LinearRegression** performed the best on the validation set and was selected for final testing.
- **Test Set RMSE**: 39.29, which meets the project requirement (RMSE ≤ 48).

## Conclusion
The project successfully developed a predictive model for forecasting hourly taxi orders. The LinearRegression model achieved the best performance, with an RMSE of 39.29 on the test set, fulfilling the project's objective. The analysis also revealed key trends and seasonal patterns in the data, which can be leveraged for further optimization.
