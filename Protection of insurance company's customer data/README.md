# Linear Algebra Project: Protecting Client Personal Data

## Project Overview

This project focuses on developing a method to protect clients' personal data while maintaining the quality of machine learning models. The solution involves using linear algebra concepts to encrypt features without compromising model performance.

## Key Features

- Data encryption through matrix multiplication
- Proof that model quality remains unchanged after transformation
- Implementation using Python's scientific computing libraries
- Comparison of model metrics before and after encryption

## Dataset Description

The dataset contains insurance client information with the following features:

| Feature (Russian) | English Translation | Description |
|-------------------|----------------------|-------------|
| Пол | Gender | Binary gender indicator (0/1) |
| Возраст | Age | Client's age in years |
| Зарплата | Salary | Client's annual salary |
| Члены семьи | Family Members | Number of family members |
| Страховые выплаты | Insurance Claims | Target variable - number of insurance claims |

Dataset characteristics:
- Clean data with no missing values
- Mixed data types (int and float)
- Balanced distribution between genders
- Average client age: 30 years

## Mathematical Foundation

The project demonstrates that multiplying features by an invertible matrix **P** preserves model quality because:

1. Original predictions: a = Xw
2. Encrypted predictions: a₁ = XPw₁
3. Through matrix properties, we prove: a = a₁

This is shown through:
- Matrix inversion properties
- Identity matrix transformations
- Linear regression coefficient calculations

## Implementation Steps

1. Data loading and exploration
2. Train-test split (75%-25%)
3. Baseline model training and evaluation
4. Random invertible matrix generation
5. Feature transformation: X' = XP
6. Model training on transformed data
7. Metric comparison (R² score)

## Results

The R² score remains identical before and after data transformation, proving the method's validity:

- Original data R² score: [value]
- Transformed data R² score: [value]

## Dependencies

- Python 3.9
- NumPy
- pandas
- scikit-learn
- Matplotlib

## Conclusion

This project successfully demonstrates a linear algebra-based approach to protect sensitive client data while maintaining machine learning model performance. The method is particularly valuable for industries handling personal information where data privacy is crucial.
