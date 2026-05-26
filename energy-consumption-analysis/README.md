# Household Energy Consumption Analysis & Forecasting

## Problem Statement
Understanding when and how energy is consumed in a household can help reduce costs, identify inefficiencies, and enable smarter energy management. This project analyses over 4 years of minute-level household electricity data to uncover usage patterns and builds predictive models to forecast future power consumption.

## Dataset
- **Source:** UCI Individual Household Electric Power Consumption dataset
- **Size:** ~2 million minute-level readings (2006–2010)
- **Key features:** Global active power, reactive power, voltage, intensity, sub-metering for kitchen, laundry, and heating/AC

## Approach
1. Loaded and parsed ~2M rows of minute-resolution time series data
2. Cleaned missing values using linear interpolation and forward fill
3. Feature engineered temporal features: year, month, day of week, hour, season
4. **Exploratory Analysis:**
   - Hourly usage patterns by year
   - Seasonal consumption trends (Winter, Spring, Summer, Autumn)
   - Monthly mean, median, and peak power analysis
   - Appliance-level sub-metering breakdown
5. Anomaly detection using Isolation Forest
6. Trained a **Random Forest Regressor** for power consumption forecasting
7. Built and trained a **two-layer LSTM** neural network for sequential time series forecasting (using 60-minute lookback windows)
8. Compared model performance using MAE, RMSE, and R²
9. Generated actionable energy-saving recommendations based on peak demand analysis

## Key Findings
- Peak energy consumption occurs consistently during evening hours across all years
- Winter shows the highest average power usage; Summer the lowest
- Heating/AC (Sub_metering_3) is the most energy-intensive appliance category
- Random Forest achieved strong R² with low relative MAE on the test set
- LSTM captured sequential dependencies in the time series for short-term forecasting

## Business / Household Recommendations
- Shift high-energy appliance usage (laundry, heating) away from identified peak hours to reduce costs
- Monitor heating/AC usage — it accounts for the largest share of consumption
- Seasonal energy budgeting should account for Winter spikes in demand

## Technical Highlights
- Handles a large-scale (~2M row) real-world time series dataset end-to-end
- Implements both classical ML (Random Forest) and deep learning (LSTM) approaches
- Includes appliance-level sub-metering analysis for granular insights

## Tools Used
Python, pandas, numpy, scikit-learn (RandomForestRegressor, IsolationForest, MinMaxScaler), TensorFlow/Keras (LSTM), matplotlib, seaborn, plotly, scipy
