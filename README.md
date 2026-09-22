# Walmart Sales Forecasting Using Machine Learning

## 📌 Project Overview

This project focuses on forecasting Walmart weekly sales using
historical sales data and machine learning techniques.

The goal is to analyze historical sales patterns, engineer
time-based features, and build regression models capable of
predicting future weekly sales.

The project also explores seasonality and evaluates models using
time-aware validation techniques.

---

## 📊 Dataset

The project uses the Walmart Sales Forecast dataset available on Kaggle.

The dataset contains more than 420,000 historical sales records
with the following main features:

- Store
- Department
- Date
- Weekly Sales
- Holiday indicator

For the forecasting analysis, weekly sales were aggregated by date
to analyze the overall sales trend over time.

---

## 🛠 Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- XGBoost
- Statsmodels
- Google Colab

---

## 🔍 Project Workflow

### 1. Data Exploration

The dataset was inspected for:

- Dataset size
- Data types
- Missing values
- Date range
- Weekly sales patterns

### 2. Time-Based Feature Engineering

Several features were created from the historical sales data:

- Year
- Month
- Week of year
- Lag 1
- Lag 2
- Lag 4
- Lag 52
- 4-week rolling average

Lag features allow the models to use previous sales observations
when forecasting future sales.

### 3. Time Series Analysis

Weekly sales were visualized over time to identify trends,
seasonal patterns, and unusual sales peaks.

Seasonal decomposition was also applied using a 52-week seasonal
period to separate the time series into:

- Trend
- Seasonality
- Residual components

### 4. Machine Learning Models

Two regression models were explored:

#### Random Forest Regressor

Random Forest was used as the main baseline machine learning model
for predicting weekly sales.

#### XGBoost Regressor

XGBoost was implemented as an additional forecasting model and
evaluated using time-aware validation.

---

## ⏳ Time-Aware Validation

Because this is a time-series forecasting problem, random train-test
splitting was avoided.

Instead, historical observations were used for training and later
observations were used for testing.

TimeSeriesSplit was also applied to evaluate model performance across
multiple chronological validation periods.

This helps prevent future information from leaking into the training data.

---

## 📈 Model Evaluation

The models were evaluated using:

- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- R² Score
- MAE as a percentage of average weekly sales

Actual and predicted sales were also plotted over time to visually
evaluate forecasting performance.

One baseline Random Forest experiment achieved:

- MAE: approximately 1.29 million
- RMSE: approximately 1.57 million
- R²: 0.21
- MAE: approximately 2.77% of average weekly sales

The XGBoost experiment demonstrated that a more complex model does
not necessarily guarantee better forecasting performance, highlighting
the importance of time-aware evaluation.

---

## 📉 Seasonal Analysis

Seasonal decomposition revealed a strong yearly seasonal pattern,
including significant sales peaks during specific periods of the year.

This supported the use of yearly lag features such as Lag 52.

---

## 💡 Key Takeaways

- Historical sales contain strong seasonal patterns.
- Lag features are useful for time-series forecasting.
- Rolling averages provide information about recent sales trends.
- Time-aware validation is essential for avoiding data leakage.
- More complex models do not automatically produce better forecasts.
- Model performance can vary significantly across different time periods.

---

## 🚀 Future Improvements

Future versions of this project could include:

- Store-level forecasting
- Department-level forecasting
- Additional holiday and economic features
- Hyperparameter optimization
- More advanced forecasting models
- Comparison with statistical forecasting approaches

---

## 👤 Shrouk

Your Name

Data Analytics / Machine Learning Portfolio Project
