# Diabetes Prediction using Logistic Regression

## Problem Statement
Early detection of diabetes can significantly improve patient outcomes. This project builds a binary classification model to predict whether a patient is diabetic based on medical diagnostic measurements, and evaluates the impact of different regularization strategies and train-test splits on model performance.

## Dataset
- **Source:** Pima Indians Diabetes dataset
- **Size:** 768 patients, 8 medical features
- **Key features:** Glucose, BMI, Age, Blood Pressure, Insulin, Skin Thickness, Pregnancies, Diabetes Pedigree Function
- **Target:** Outcome (0 = No Diabetes, 1 = Diabetes)

## Approach
1. Exploratory data analysis — class balance check, correlation heatmap
2. Feature scaling using StandardScaler
3. Trained Logistic Regression models across multiple train-test splits (80/20, 75/25, 70/30)
4. Compared L1 (Lasso) vs L2 (Ridge) regularization for each split
5. Selected best model configuration based on F1 score and generalization
6. Evaluated final model using confusion matrix, precision, recall, F1, and accuracy
7. Interpreted feature coefficients to identify the strongest predictors of diabetes

## Key Findings
- Glucose and BMI are the strongest positive predictors of diabetes
- Age and Blood Pressure contribute moderately to predictions
- L2 regularization generalized better than L1 on this dataset
- Model accuracy remained stable at approximately 75–80% across all train-test splits, indicating robust performance
- Recall for diabetic cases is a critical metric in healthcare — the model was evaluated with this in mind

## Business / Clinical Recommendations
- Glucose screening and BMI monitoring should be prioritized in early diabetes risk assessment
- The model can serve as a preliminary screening tool to flag high-risk patients for further clinical evaluation
- Future improvements: handle zero values in Insulin and SkinThickness (likely missing data), and explore ensemble models (Random Forest, XGBoost) for improved recall

## Tools Used
Python, pandas, numpy, scikit-learn (LogisticRegression, StandardScaler, confusion_matrix, classification_report), matplotlib, seaborn
