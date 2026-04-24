# HOUSE_PRICE
# 🏠 House Price Prediction

## Problem Statement
Predict the sale price of residential homes in Ames, Iowa 
based on structural and contextual features. Helps buyers, 
sellers, and real estate agencies make data-driven pricing decisions.

## Dataset
- **Source:** Kaggle — House Prices: Advanced Regression Techniques
- **Size:** ~1,400 rows, 80+ features
- **Target:** SalePrice (USD)

## Approach
- Null handling: Median imputation for LotFrontage (~18% missing)
- Outlier treatment on SalePrice using IQR method
- Identified and encoded MSSubClass as categorical (commonly 
  mistaken as numeric)
- One-hot encoding for SaleCondition
- Feature scaling using StandardScaler
- Feature importance analysis using RandomForestRegressor
- Re-trained model on top features for comparison

## Results
| Model | R² | RMSE |
|---|---|---|
| Linear Regression | ~0.78 | ~28,000 |
| Lasso Regression | ~0.78 | ~28,000 |
| Ridge Regression | ~0.78 | ~28,000 |
| **Random Forest** | **0.805** | **~23,670** |

## Key Findings
- Random Forest outperformed all linear models confirming 
  non-linear relationships between features and SalePrice
- Overall quality, living area, and garage size were the 
  top predictors of sale price
- MSSubClass (dwelling type) is a categorical feature 
  disguised as numeric — a common real-world data pitfall

## Libraries Used
Python, Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn
