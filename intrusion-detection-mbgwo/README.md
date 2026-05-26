# Intrusion Detection System using MBGWO Feature Selection

## Problem Statement
Network intrusion detection systems (IDS) deal with high-dimensional data where not all features contribute equally to detecting attacks. This project implements a Modified Binary Grey Wolf Optimizer (MBGWO) — a nature-inspired metaheuristic algorithm — to intelligently select the most relevant features, reducing model complexity while maintaining or improving classification performance.

## Dataset
- **Source:** NF-ToN-IoT dataset (network traffic data for IoT intrusion detection)
- **Key features:** Network flow statistics (packet counts, byte rates, flags, protocols, etc.)
- **Target:** Attack type classification (multi-class)

## Approach
1. Data loading with intelligent sampling (4% of full dataset for computational efficiency)
2. Preprocessing — dropped constant columns, handled missing values, encoded categorical features, standardized with StandardScaler
3. Implemented **MBGWO** from scratch:
   - Population-based search with alpha, beta, and delta wolf positions
   - Sigmoid-based binarization to select/deselect features
   - Fitness function balancing F1 score vs number of selected features
   - Early stopping for efficiency
4. Used Random Forest as the fitness evaluator during feature selection
5. Trained final classifiers (SVM and Random Forest) on the MBGWO-selected feature subset
6. Evaluated using accuracy, precision, recall, F1 score, and confusion matrix
7. Built a Streamlit interface for interactive use

## Key Findings
- MBGWO successfully reduced the feature space while preserving classification performance
- The selected feature subset achieved competitive F1 scores compared to using all features
- Random Forest outperformed SVM on this dataset in terms of multi-class classification
- The fitness function's alpha weighting (balancing accuracy vs feature count) proved effective in finding compact, high-performing feature subsets

## Technical Highlights
- Custom implementation of a metaheuristic optimization algorithm (MBGWO)
- Balances model accuracy with computational efficiency through feature reduction
- Includes a Streamlit web interface for end-to-end pipeline interaction

## Tools Used
Python, pandas, numpy, scikit-learn (SVM, RandomForestClassifier, PCA, LabelEncoder), joblib, Streamlit, matplotlib
