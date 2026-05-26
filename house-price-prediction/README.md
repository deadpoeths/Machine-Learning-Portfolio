# House Price Prediction using Linear & Multivariable Regression

## Problem Statement
A real estate agency wants a data-driven way to estimate property prices. This project compares a simple single-variable model (size only) against a multivariable model that factors in property type and location — to determine which approach better supports accurate valuations.

## Dataset
- **Source:** Real Estate Agency dataset
- **Key features:** Property size (sqm), property type, location, price (USD)

## Approach
1. Exploratory data analysis — summary statistics, missing value checks
2. Encoded categorical variables (PropertyType, Location) using one-hot encoding
3. Built a **single-variable regression** model using only size (sqm) as a predictor
4. Built a **multivariable regression** model using all available features
5. Evaluated both models using RMSE and R² score
6. Visualized feature coefficients to understand which factors drive price most
7. Compared models to determine the better approach for valuation

## Key Findings
- The multivariable model outperformed the single-variable model, achieving a higher R² score
- Property type and location added meaningful predictive value beyond size alone
- Feature coefficient analysis revealed which locations and property types command price premiums
- The multivariable model provides a more reliable framework for property valuation

## Business Recommendations
- Use the multivariable model as a baseline valuation tool for new listings
- Location and property type should be primary filters when advising clients on pricing strategy
- Further improvements could include neighbourhood-level features or recent transaction data

## Tools Used
Python, pandas, numpy, scikit-learn (LinearRegression, train_test_split, metrics), matplotlib, seaborn, plotly
