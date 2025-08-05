# Oil Well Location Selection Analysis

## Project Overview
This project focuses on selecting the optimal region for oil well development based on geological data. The goal is to analyze three potential regions and determine which one offers the highest profitability while minimizing risks. The analysis involves machine learning models to predict oil reserves and evaluate the economic viability of each region.

## Key Steps

### 1. Data Preparation
- **Datasets Used**: Three datasets (`geo_data_0.csv`, `geo_data_1.csv`, `geo_data_2.csv`) containing geological features and oil reserve volumes for 100,000 wells each.
- **Data Exploration**: 
  - Checked for missing values and duplicates (minor duplicates found but retained).
  - Analyzed statistical properties (mean, standard deviation, min/max values) of each dataset.

### 2. Model Training and Evaluation
- **Linear Regression Models**: Trained on each dataset to predict oil reserves.
- **Performance Metrics**: 
  - **RMSE**: Calculated for each model to evaluate prediction accuracy.
  - **Average Predicted Reserves**: Compared with actual averages to validate model performance.

### 3. Profitability Analysis
- **Threshold Calculation**: Determined the minimum oil reserve volume (111 barrels) required for a well to be profitable.
- **Region Comparison**:
  - Calculated the percentage of wells in each region exceeding the threshold.
  - Evaluated the total profit for the top 200 wells in each region.

### 4. Risk Assessment
- **Bootstrap Method**: Used to estimate the confidence intervals and risks of losses for each region.
- **Key Findings**:
  - **Region 1**: Highest potential profit but moderate risk (5.9% chance of losses).
  - **Region 2**: Balanced profit and lowest risk (1.0% chance of losses).
  - **Region 3**: Moderate profit but higher risk (6.3% chance of losses).

## Results
- **Recommended Region**: **Region 2** offers the best balance of profitability and low risk, with an average profit of 0.52 billion RUB and only a 1.0% chance of losses.
- **Runner-up**: Region 1 has higher potential profit but comes with a higher risk of losses.

## Tools and Libraries
- **Python Libraries**: `pandas`, `numpy`, `matplotlib`, `scikit-learn`, `tqdm`.
- **Machine Learning**: Linear Regression, RMSE evaluation, Bootstrap for risk analysis.
