# Gold Recovery Prediction Model

## Project Overview
This project focuses on developing a machine learning prototype for "Tsifra" company, which creates solutions for efficient industrial operations. The model predicts the gold recovery coefficient from gold-bearing ore using mining and purification parameters. The goal is to optimize production and prevent unprofitable enterprise operations.

## Project Goals
1. **Data Preparation**:
   - Calculate MAE between calculations and feature values
   - Analyze features unavailable in test set
   - Preprocess data (handle missing values, anomalies, etc.)
   
2. **Data Analysis**:
   - Evaluate metal concentration changes at different stages
   - Compare raw material granule size distributions
   - Calculate total metal concentrations at different stages
   
3. **Model Building**:
   - Implement SMAPE metric
   - Train and evaluate model quality
   - Select best model and test it

## Data Description
The data represents various stages of gold processing:
- **Process stages**:
  - Rougher feed (raw material)
  - Rougher additions (flotation reagents)
  - Rougher process (flotation)
  - Primary/secondary cleaning
  - Final output

- **Parameters**:
  - Air amount, fluid levels
  - Feed size, feed rate
  - Concentrations of gold (Au), silver (Ag), lead (Pb)

## Key Findings

### Data Preparation
- Verified correct recovery efficiency calculations (MAE ≈ 0)
- Identified output features missing from test set (historical vs real-time data)
- Handled missing values and analyzed distributions

### Data Analysis
- Gold concentration increases while other metals decrease through stages
- Granule size distributions similar between train/test sets
- Total metal concentration decreases toward final stages

### Model Performance
| Model              | Final SMAPE |
|--------------------|-------------|
| Linear Regression  | 8.79        |
| Decision Tree      | 8.55        |
| Random Forest      | **8.26**    |
| Lasso              | 8.52        |
| ElasticNet         | 8.51        |
| Constant Model     | 8.40        |

**Best Model**: Random Forest (SMAPE 8.26 on training data)

### Test Set Validation
The Random Forest model achieved **SMAPE 7.37** on test data, significantly outperforming the constant model (8.40).

## Conclusion
The Random Forest model was selected as the best performing solution, demonstrating strong predictive capability for gold recovery optimization. The model successfully meets business requirements by providing accurate predictions that can guide production decisions.

## Technologies Used
- Python
- Pandas, NumPy
- Scikit-learn
- Matplotlib, Seaborn
