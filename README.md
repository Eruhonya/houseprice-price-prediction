# House Prices Prediction

## Overview

This project focuses on predicting residential property sale prices using the Ames Housing dataset. The objective is to develop a robust machine learning pipeline capable of accurately estimating house prices while maintaining strong generalization performance on unseen data.

---

## Business Problem

Accurate property valuation is essential for buyers, sellers, real estate agencies, and financial institutions. Incorrect pricing may lead to financial losses, delayed transactions, or poor investment decisions.

The goal of this project is to build a predictive model that estimates house sale prices based on property characteristics such as location, size, quality, age, and structural attributes.

---

## Dataset

**Dataset:** Ames Housing Dataset

* 1,460 residential properties
* 79 explanatory features
* Target variable: `SalePrice`

Features include:

* Property size
* Living area
* Construction year
* Neighborhood
* Basement characteristics
* Garage information
* Exterior quality
* Overall property condition

---

## Data Preprocessing

A complete end-to-end preprocessing pipeline was developed using Scikit-Learn and Feature-engine.

### Missing Value Handling

* LotFrontage imputed using neighborhood-level median values
* Numerical variables imputed with zero
* Categorical variables imputed with a dedicated "None" category

### Feature Engineering

* YearBuilt discretization
* GrLivArea equal-frequency binning
* Rare category consolidation

### Outlier Treatment

Winsorization applied to:

* LotArea
* GrLivArea
* TotalBsmtSF
* 1stFlrSF

### Feature Transformation

* One-Hot Encoding
* Yeo-Johnson Power Transformation
* Standard Scaling

### Feature Selection

* Constant feature removal
* Correlation-based feature elimination

---

## Machine Learning Pipeline

Raw Data

→ Missing Value Imputation

→ Feature Engineering

→ Outlier Treatment

→ Rare Category Encoding

→ One-Hot Encoding

→ Yeo-Johnson Transformation

→ Feature Selection

→ Feature Scaling

→ Linear Regression

→ Sale Price Prediction

---

## Model

**Algorithm:** Linear Regression

The model was trained using a fully reproducible preprocessing pipeline to avoid data leakage and ensure consistent transformations across training and testing datasets.

---

## Results

| Metric | Training Set | Test Set |
| ------ | ------------ | -------- |
| R²     | 0.9317       | 0.9207   |
| MAE    | 12,246       | 13,434   |
| RMSE   | 17,111       | 20,388   |

### Interpretation

* The model explains more than 92% of the variance in house prices on unseen data.
* Minimal performance degradation between training and test sets indicates strong generalization.
* No significant signs of overfitting were observed.

---

## Technologies Used

* Python
* Pandas
* NumPy
* Scikit-Learn
* Feature-engine
* Matplotlib
* Seaborn

---

## Key Takeaways

* Built a production-style machine learning pipeline.
* Implemented advanced preprocessing techniques.
* Performed feature engineering and feature selection.
* Achieved strong predictive performance with Linear Regression.
* Developed a fully reproducible workflow suitable for further experimentation and model comparison.

---

## Future Improvements

* Ridge Regression
* Lasso Regression
* Random Forest Regressor
* XGBoost
* Hyperparameter Optimization
* Cross-Validation Benchmarking
