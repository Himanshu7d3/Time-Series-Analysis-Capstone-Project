# Time-Series-Analysis-Capstone-Project
# 📈 Predictive Modelling & Risk-Optimized Portfolio Allocation 

**Time Series Analysis 2026 Capstone Project**

This repository contains the Jupyter Notebook and methodology used to construct a data-driven, risk-optimized ₹10,00,000 virtual portfolio on the StockGro platform. By leveraging historical daily stock data from the National Stock Exchange (NSE), this project implements a comprehensive machine learning pipeline that bridges theoretical data science forecasting with practical portfolio management.

***

## 🎯 Project Objective

To develop an object-oriented forecasting architecture utilizing statistical and deep learning models to predict stock prices, evaluate underlying risk, and execute a mathematically optimized capital allocation strategy in a live virtual market environment.

## 🛠️ Tech Stack & Methodology

* **Data Sourcing:** `yfinance` API (Daily 'Close' prices from Jan 1, 2021 – Dec 31, 2025).
* **Preprocessing:** Forward-fill for missing data handling; Augmented Dickey-Fuller (ADF) tests for stationarity.
* **Forecasting Architecture:**
    * **SARIMA:** Captures strict seasonal trends on a 5-day weekly trading cycle.
    * **Prophet:** Identifies overarching macroeconomic trends and structural shifts.
    * **LSTM:** Deep learning neural network mapped to complex, non-linear market patterns and volatility shocks.
* **Volatility Modeling:** GARCH(1,1) deployed to predict future volatility states and combat "volatility clustering" alongside 30-Day Rolling Standard Deviations.
* **Evaluation Metrics:** Root Mean Squared Error (RMSE), Mean Absolute Percentage Error (MAPE), Directional Accuracy, and 95% Confidence Interval spreads.

## 📊 Stock Universe (Diversification Strategy)

To mitigate sector-specific risk, the portfolio comprises five unique large-cap stocks:
* **TCS (IT):** Defensive anchor with historical stability and low variance.
* **SBIN (Banking):** Financial backbone, highly liquid but sensitive to macro changes.
* **M&M (Auto):** Momentum play capturing traditional auto and emerging EV sectors.
* **HAL (Defense):** High-growth, high-volatility asset driven by government contracts.
* **TITAN (Consumer Durables):** Cyclical asset capturing seasonal consumer spending.

## ⚖️ Portfolio Allocation Strategy

Capital was distributed using a highly structured **Inverse Volatility Risk Parity strategy**. 
1. **Primary Risk Layer:** Target weights were assigned inversely proportional to a hybrid historical/predictive volatility score, heavily penalizing volatile stocks while rewarding stable assets.
2. **Secondary Risk Layer (Model Uncertainty):** For each stock, the pipeline calculated the "Model Risk" percentage based on the spread between the 95% Upper and Lower Confidence Intervals. The algorithm automatically trusted the model (SARIMA, Prophet, or LSTM) that produced the tightest, most highly constrained confidence band.

## 🚀 Results & Forward Testing

The master trading dashboard generated whole-number share allocations that were executed on the StockGro platform. 

To evaluate efficacy, a 48-hour forward testing window was analyzed against unseen, real-world NSE market data:
* **Top Performer:** TCS closely adhered to the SARIMA projected trendline with an exceptionally low error margin of just **0.99%**.
* **Overall:** The predictive models demonstrated strong overarching directional accuracy, and the Minimum Variance allocation successfully insulated the broader portfolio from significant downside risk. Unpredictable stochastic macroeconomic shocks primarily drove minor deviations (e.g., SBIN at 2.95% error).

## 🔮 Future Improvements

Future iterations of this pipeline aim to incorporate:
* **Multivariate Models (SARIMAX/LSTMs):** Integrating alternative data like financial news sentiment and macroeconomic indicators to improve shock responsiveness.
* **Higher-Frequency Training:** Shifting to hourly or 15-minute intervals to better capture intra-day price swings.
* **Ensemble Forecasting:** Averaging predictions across all three methodologies to smooth isolated algorithmic biases.

## 📂 Repository Contents

* `time-series-forecasting.ipynb`: The complete Python pipeline (Data Fetching ➔ Preprocessing ➔ Modeling ➔ Forecasting ➔ Portfolio Construction).
* `Time_Series_Project_Report.pdf`: Comprehensive documentation of the methodology, math, and StockGro execution results.