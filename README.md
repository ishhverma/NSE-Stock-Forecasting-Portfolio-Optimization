# 📈 Time Series Forecasting & Portfolio Optimization using NSE Stocks
## Overview
This project applies Time Series Analysis and Quantitative Finance techniques to forecast stock prices and construct optimized investment portfolios using historical stock market data from the National Stock Exchange (NSE) of India.
The analysis was conducted on five major NSE-listed companies from diverse sectors including Banking, Information Technology, Pharmaceuticals, FMCG, and Automobile. Multiple forecasting models were implemented and compared to evaluate their ability to predict future stock prices and support investment decision-making.
In addition to forecasting, the project includes volatility analysis, stationarity testing, return distribution analysis, correlation analysis, and portfolio optimization strategies based on expected returns and risk management principles.

## Project Objectives
The primary objectives of this project are:
* Analyze historical NSE stock price data using Time Series Analysis techniques.
* Identify trends, volatility patterns, and relationships among stocks.
* Test and transform non-stationary financial time series.
* Build forecasting models using ARIMA, Prophet, and Holt-Winters methods.
* Compare model performance using multiple evaluation metrics.
* Predict future stock prices.
* Design portfolio allocation strategies using quantitative methods.
* Evaluate risk-return tradeoffs in portfolio construction.
* Simulate practical investment decision-making using data-driven insights.

## Dataset Description
### Data Source
Yahoo Finance API (yFinance)

### Time Period
January 2021 – May 2026

### Frequency
Daily Stock Data

### Features Used
* Open Price
* High Price
* Low Price
* Close Price
* Trading Volume

## Selected Stocks
| Company                         | Sector                 |
| ------------------------------- | ---------------------- |
| HDFC Bank                       | Banking                |
| Tata Consultancy Services (TCS) | Information Technology |
| Sun Pharmaceutical Industries   | Pharmaceuticals        |
| ITC Limited                     | FMCG                   |
| Eicher Motors                   | Automobile             |
The selected companies represent different sectors of the Indian economy, allowing portfolio diversification and comparative sector analysis.

## Data Preprocessing
Financial time series data often contains trends, noise, and non-stationary behavior. The following preprocessing techniques were applied before model development:

### Data Cleaning
* Removed unnecessary columns
* Handled missing values
* Formatted date index
* Converted data into structured time series format

### Return Calculation
Daily percentage returns were calculated using closing prices to analyze stock performance and risk characteristics.
### Data Splitting
| Dataset         | Period                       |
| --------------- | ---------------------------- |
| Training Data   | January 2021 – December 2025 |
| Validation Data | January 2026 – May 2026      |
The validation period was used to evaluate forecasting performance on unseen data.

## Exploratory Data Analysis (EDA)
Exploratory Data Analysis was performed to understand stock behavior and identify meaningful patterns.

### Historical Price Trend Analysis
Closing prices were visualized to examine long-term growth patterns and sector-specific behavior.
Key observations:
* TCS and Eicher Motors exhibited strong upward trends.
* ITC showed relatively stable price movement.
* Banking and Automobile sectors experienced higher fluctuations during uncertain market periods.

### Rolling Volatility Analysis
A 20-day rolling standard deviation was used to measure short-term volatility.
Key observations:
* Eicher Motors exhibited the highest volatility.
* ITC showed comparatively stable volatility behavior.
* Banking stocks displayed moderate volatility patterns.

### Return Distribution Analysis
Daily returns were analyzed using histograms and descriptive statistics.
The analysis included:
* Mean Return
* Standard Deviation
* Skewness
* Kurtosis
The return distributions showed evidence of fat tails, indicating the presence of extreme market movements.

### Correlation Analysis
Correlation analysis was conducted to understand relationships among stock returns.

Key observations:
* Moderate correlations existed among most stocks.
* Pharma and IT sectors exhibited lower correlations.
* Diversification opportunities were identified across sectors.

## Stationarity Testing
Stationarity is an important assumption for many forecasting models.

### Augmented Dickey-Fuller (ADF) Test
The ADF Test was applied to determine whether stock price series were stationary.

### Results
All stock price series were found to be non-stationary in their original form.
To achieve stationarity, first-order differencing was applied.
After differencing, all series passed the stationarity test and became suitable for forecasting.

## Forecasting Models
Three forecasting models were implemented and compared.
### 1. ARIMA Model
ARIMA (AutoRegressive Integrated Moving Average) combines:
* Autoregressive Components
* Differencing
* Moving Average Components
Model Configuration:
ARIMA(1,1,1)
Key Characteristics:
* Suitable for stationary series
* Effective for short-term forecasting
* Requires preprocessing through differencing

### 2. Prophet Model
Prophet is a forecasting framework developed for handling trend and seasonal patterns.
Key Characteristics:
* Handles trend changes effectively
* Robust to missing values
* Provides strong directional forecasting performance
Performance observations indicated superior forecasting results for TCS and several other stocks.

### 3. Holt-Winters Exponential Smoothing
The Holt-Winters model captures:
* Level
* Trend
* Seasonal Components
Key Characteristics:
* Effective for smooth trend forecasting
* Performs well on relatively stable time series
* Produces interpretable forecasts
The model achieved lower prediction errors for HDFC Bank and Eicher Motors.

## Model Evaluation
The forecasting models were evaluated using the following metrics:

### RMSE (Root Mean Squared Error)
Measures the magnitude of prediction errors.

### MAPE (Mean Absolute Percentage Error)
Measures forecasting accuracy as a percentage.

### Directional Accuracy
Measures the ability of a model to correctly predict the direction of future price movement.

## Model Comparison
### Key Findings
* Prophet achieved superior directional forecasting accuracy.
* Holt-Winters produced lower forecasting errors for several stocks.
* ARIMA demonstrated stable forecasting behavior after stationarity transformation.
* Model performance varied significantly across sectors and stocks.

### Best Performing Models

| Stock         | Best Model   |
| ------------- | ------------ |
| HDFC Bank     | Holt-Winters |
| TCS           | Prophet      |
| Sun Pharma    | Prophet      |
| ITC           | Prophet      |
| Eicher Motors | Holt-Winters |

The results highlight the importance of comparing multiple forecasting approaches rather than relying on a single model.

## Portfolio Optimization
A virtual investment capital of ₹10,00,000 was allocated using multiple portfolio construction techniques.

### Forecast-Based Allocation
Portfolio weights were assigned based on forecasted future returns.
Stocks with higher expected returns received larger allocations.

Key Outcome:
* HDFC Bank received the highest allocation.
* ITC received the second-highest allocation.
* Stocks with negative expected returns were assigned lower weights.

### Volatility-Based Allocation
Portfolio weights were assigned inversely proportional to stock volatility.

Objective:
Minimize overall portfolio risk.

Key Outcome:
* ITC received the largest allocation due to lower volatility.
* High-volatility stocks received smaller allocations.

### Correlation-Based Diversification Strategy
Portfolio weights were assigned inversely proportional to average stock correlations.

Objective:
Improve diversification and reduce concentration risk.

Key Outcome:
* Sun Pharma and TCS received larger allocations.
* Portfolio diversification improved through lower inter-stock correlations.

## Key Insights
* Financial market data exhibits strong non-stationary behavior.
* First-order differencing successfully achieved stationarity.
* Prophet delivered superior directional forecasting performance.
* Holt-Winters generated lower prediction errors for stable stocks.
* Eicher Motors exhibited the highest volatility among selected companies.
* ITC demonstrated relatively stable return characteristics.
* Diversified portfolio construction reduced concentration risk.
* Correlation-based allocation improved portfolio efficiency.

## Technologies Used
### Programming Language
* Python

### Libraries
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Statsmodels
* Prophet
* Scikit-Learn
* yFinance

### Concepts Applied
* Time Series Analysis
* Statistical Forecasting
* Quantitative Finance
* Portfolio Optimization
* Risk Management
* Financial Analytics

## Repository Structure
```text
NSE-Stock-Forecasting-Portfolio-Optimization/
│
├── data/
├── notebooks/
├── reports/
├── images/
├── requirements.txt
├── README.md
└── LICENSE
```

## Author
**Ishu Verma**
Aspiring Data Scientist | Financial Analytics Enthusiast | Machine Learning Practitioner

### Skills Demonstrated
* Time Series Forecasting
* Quantitative Finance
* Portfolio Optimization
* Statistical Modeling
* Data Analysis
* Machine Learning
* Python Programming
* Financial Risk Analysis

## Conclusion
This project demonstrates the practical application of Time Series Analysis and Quantitative Finance techniques for forecasting stock prices and constructing optimized investment portfolios. By integrating statistical forecasting models, risk analysis, and portfolio allocation strategies, the study provides a comprehensive framework for data-driven investment decision-making and financial analytics.
