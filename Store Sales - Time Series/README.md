<strong>Store Sales – Time Series Forecasting<br>
Time‑series forecasting project using the Kaggle “Store Sales” dataset</strong>

<br>Project Overview</br>
This project builds a robust sales forecasting system for a multi‑store retail business using the Kaggle Store Sales – Time Series Forecasting dataset. The goal is to predict daily sales and understand the factors that drive revenue across different stores and product families.

Accurate forecasting helps businesses:
Plan stock and inventory
Optimise staffing
Manage cashflow
Prepare for seasonal peaks
Improve operational efficiency

This project demonstrates a full end‑to‑end workflow: data preparation, feature engineering, modelling, evaluation, and dashboarding.

Objectives
- Explore and clean multi‑source retail data
- Engineer meaningful time‑series and external features
- Train forecasting models (Prophet, XGBoost, SARIMA, etc.)
- Evaluate model performance using RMSE, MAE, and MAPE
- Build an interactive dashboard for business users
- Provide actionable insights and recommendations

Dataset Description
The dataset contains daily sales for a grocery retailer in Ecuador, along with rich external data.

Files Used
- train.csv — historical sales per store and product family
- test.csv — future dates for prediction
- stores.csv — store metadata (city, type, cluster)
- oil.csv — daily oil prices (economic indicator)
- holidays_events.csv — national and regional holidays
- transactions.csv — number of daily transactions per store

This combination allows for deep feature engineering and realistic forecasting.

Data Preparation
Key steps in the preprocessing pipeline:
- Convert date to datetime and sort chronologically
- Merge all datasets into a unified time‑series table
- Handle missing values (forward‑fill oil prices, fill transaction gaps)
- Remove or cap extreme outliers
- Aggregate or filter by store and product family
- Create a clean modelling dataset with consistent time indices

Feature Engineering
Feature engineering is critical for improving forecast accuracy.

Date‑based features
- Day of week
- Week of year
- Month, quarter, year
- Weekend indicator

Lag features
- lag_1, lag_7, lag_14, lag_28
- Rolling means: 7‑day, 14‑day, 30‑day

External features
- Oil price
- Holiday type
- Store metadata
- Transactions
- Promotion flags
These features are especially powerful for tree‑based models like XGBoost.

Modelling Approach
- A combination of classical and machine‑learning models were explored.

Baseline Models
- Naïve forecast
- Seasonal naïve
- Moving average

Statistical Models
- SARIMA
- Holt‑Winters (ETS)

Machine Learning Models
- XGBoost Regressor
- LightGBM
- Random Forest

Modern Forecasting Models
- Prophet (handles seasonality and holidays well)
- LSTM / deep learning (optional extension)

Recommended Ensemble
- Prophet + XGBoost
This balances interpretability and accuracy.

Evaluation
Models are evaluated using:
- RMSE (primary metric)
- MAE
- MAPE

Visual diagnostics include:
- Actual vs predicted plots
- Residual analysis
- Seasonality decomposition
- Feature importance charts

Dashboard
An interactive dashboard (Power BI or Streamlit) provides business‑friendly insights.

Dashboard Pages
1. Sales Overview
- Total sales
- Sales by store
- Sales by product family
- Year‑over‑year comparison

2. Forecasting
- 30‑day and 90‑day forecasts
- Confidence intervals
- Store and product selectors

3. Drivers of Sales
- Feature importance
- Promotion impact
- Holiday effects
- Oil price correlation

4. Recommendations
- Stock planning
- Promotion timing
- Staffing suggestions

Repository Structure
store-sales-forecasting/
│
├── data/                # (empty or sample)
├── notebooks/
│   ├── 01_eda.ipynb
│   ├── 02_feature_engineering.ipynb
│   ├── 03_model_training.ipynb
│   ├── 04_forecasting.ipynb
│
├── src/
│   ├── data_prep.py
│   ├── feature_engineering.py
│   ├── models.py
│   ├── utils.py
│
├── dashboard/
│   ├── app.py           # Streamlit app
│
├── results/
│   ├── forecasts.csv
│   ├── plots/
│
└── README.md


Future Enhancements
- Add deep‑learning models (N‑Beats, TFT)
- Deploy the model as an API
- Automate retraining with new data
- Add anomaly detection for unusual sales patterns
- Build a full SME‑ready forecasting micro‑service

 License
This project is for educational and portfolio purposes.
