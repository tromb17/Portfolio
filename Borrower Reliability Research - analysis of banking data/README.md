# Borrower Reliability Analysis

This project analyzes borrower reliability based on various factors such as family status, income level, loan purpose, and number of children. The goal is to identify patterns that influence timely loan repayment.

## Project Structure

The analysis is conducted in a Jupyter notebook (`Project1.ipynb`) containing:

1. **Data Preprocessing**
   - Loading and initial exploration of the dataset
   - Handling missing values (filled with median values for respective categories)
   - Removing anomalies (e.g., negative values in 'children' column)
   - Eliminating duplicates
   - Categorizing data (income levels and loan purposes)

2. **Data Analysis**
   - Relationship between number of children and loan repayment
   - Impact of family status on repayment reliability
   - Influence of income level on timely payments
   - Effect of loan purpose on repayment behavior

3. **Visualizations**
   - Bar plots comparing repayment rates across different categories
   - Data tables showing key metrics

## Key Findings

### Dependencies Identified:

1. **Number of Children**  
   - Borrowers with no children have the highest repayment rate (7.54%)
   - Repayment becomes more challenging with more children (9.23% for 1 child, 9.45% for 2 children)

2. **Family Status**  
   - Widowed individuals have the lowest default rate (6.62%)
   - Married borrowers show good repayment (7.56%)
   - Single/unmarried borrowers have the highest risk (9.76%)

3. **Income Level**  
   - Higher income generally correlates with better repayment
   - The most reliable income bracket: 50,000-200,000 RUB

4. **Loan Purpose**  
   - Most reliable purposes: real estate operations and weddings
   - Highest risk purpose: car purchases

### Borrower Profiles:

**"Reliable" Borrower:**
- No children
- Widowed
- Income: 50,000-200,000 RUB
- Loan purpose: real estate operations

**"Risky" Borrower:**
- 2 children
- Single or in civil partnership
- Income: 30,000-50,000 RUB
- Loan purpose: car purchase

## Technical Notes

- Missing values were handled by filling with median values for respective categories
- Anomalous values (like negative numbers of children) were removed
- Data was categorized for clearer analysis:
  - Income levels grouped into categories (A-E)
  - Loan purposes consolidated into broader categories
- Visualizations created using Seaborn and Matplotlib

## Conclusions

The analysis revealed several important patterns:
- Family situation significantly impacts repayment reliability
- Income level serves as a good predictor of creditworthiness
- Loan purpose can indicate repayment risk
- Data quality is crucial - sufficient sample sizes are needed for reliable conclusions

For accurate analysis:
- Ensure equal sample sizes across compared categories
- Use appropriate methods for handling missing data (median for quantitative variables)
- Visualizations provide clearer insights than raw numbers
