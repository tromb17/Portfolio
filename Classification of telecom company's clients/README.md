# Telecom Customer Classification Project

## Project Description
This project analyzes customer behavior data from the mobile operator "Megaline" to build a classification system that recommends optimal tariff plans ("Smart" or "Ultra") for users still on legacy plans. The goal is to create a model with accuracy exceeding 0.75.

## Key Features
- Comparative analysis of three machine learning models:
  - Decision Tree
  - Random Forest
  - Logistic Regression
- Hyperparameter tuning for optimal performance
- Model validation and testing
- Sanity check using a dummy classifier

## Data
The dataset contains information about customer usage patterns:
- `calls`: Number of calls
- `minutes`: Total call duration
- `messages`: Number of SMS sent
- `mb_used`: Data consumption in MB
- `is_ultra`: Binary indicator of Ultra tariff usage (target variable)

## Methodology
1. **Data Exploration**:
   - Basic statistics and correlations
   - Class distribution analysis (30.6% Ultra users)

2. **Data Splitting**:
   - Training set (70%)
   - Validation set (15%)
   - Test set (15%)

3. **Model Development**:
   - Decision Tree: Achieved 80.7% accuracy (max_depth=5)
   - Random Forest: Best performance with 82.4% accuracy (n_estimators=8, max_depth=5)
   - Logistic Regression: Lower accuracy at 70.5%

4. **Testing**:
   - Final Random Forest model achieved 81.4% accuracy on test data
   - Outperformed dummy classifier baseline (69.4%)

## Results
The Random Forest model demonstrated the best performance with:
- 82.4% accuracy on validation set
- 81.4% accuracy on test set
- Significant improvement over baseline

## Technologies Used
- Python
- Pandas
- NumPy
- Matplotlib/Seaborn
- Scikit-learn (Decision Tree, Random Forest, Logistic Regression)
