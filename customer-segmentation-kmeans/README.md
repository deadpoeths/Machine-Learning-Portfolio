# Customer Segmentation using K-Means Clustering

## Problem Statement
A retail company wants to better understand its customer base to run targeted marketing campaigns. Rather than treating all customers the same, the goal is to identify distinct segments based on purchasing behaviour so each group can be engaged with the right strategy.

## Dataset
- **Source:** Retail transactions dataset
- **Key features:** Order value, order quantity, profit margin, discount %, shipping cost, total spend per customer

## Approach
1. Data cleaning — removed currency symbols, parsed dates, converted types
2. Outlier handling — IQR capping to reduce skew from extreme values
3. Feature engineering — aggregated order-level data to customer-level (total spend, avg order value, order frequency, etc.)
4. Log-transformed skewed monetary features to improve clustering quality
5. Standardized all features using StandardScaler
6. Used Elbow Method + Silhouette Score to determine the optimal number of clusters (K)
7. Applied K-Means clustering and visualized results using PCA (2D projection)
8. Profiled each cluster and mapped findings to marketing recommendations

## Key Findings
- Identified distinct customer segments with meaningfully different spending patterns, discount sensitivity, and order frequency
- High-value customers (top spend + high profit margin) were identified for VIP retention programs
- Price-sensitive segments showed above-average discount usage — best targeted with timed promotions rather than blanket discounts
- PCA visualization confirmed clear cluster separation, validating the segmentation

## Business Recommendations
- **High-value segment:** Prioritize loyalty programs, personalized offers, and early access to new products
- **Mid-tier segment:** Drive upsells through bundled offers at checkout
- **Price-sensitive segment:** Use targeted discount campaigns; avoid always-on discounts that erode margins

## Tools Used
Python, pandas, numpy, scikit-learn (KMeans, PCA, StandardScaler, silhouette_score), matplotlib, seaborn
