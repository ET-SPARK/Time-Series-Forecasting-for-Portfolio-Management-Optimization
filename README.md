# Time Series Forecasting for Portfolio Management Optimization.

## Project Overview

This project aims to enhance portfolio management strategies by applying time series forecasting to historical financial data. The goal is to analyze and forecast the behavior of key assets to optimize portfolio performance, manage risks, and provide data-driven investment recommendations. This project is undertaken for GMF Investments, a financial advisory firm that leverages technology for personalized portfolio management.

The analysis focuses on three key assets:

*   **Tesla (TSLA):** A high-growth, high-risk stock.
*   **Vanguard Total Bond Market ETF (BND):** A stable, low-risk bond ETF.
*   **S&P 500 ETF (SPY):** A diversified, moderate-risk ETF representing the broader US market.

The project utilizes historical financial data from July 1, 2015, to July 31, 2025, sourced from Yahoo Finance.

## File Structure

```
├── data
│   ├── BND.csv
│   ├── SPY.csv
│   └── TSLA.csv
├── notebooks
│   ├── 01_exploratory_data_analysis.ipynb
│   └── 02_model_development.ipynb
├── scripts
│   └── fetch_data.py
├── src
│   ├── data_preprocessing.py
│   ├── modeling.py
│   └── visualization.py
├── .gitignore
├── main.py
├── README.md
└── requirements.txt
```

*   **`data/`**: Stores the raw and processed data.
*   **`notebooks/`**: Contains Jupyter notebooks for exploratory data analysis and model development.
*   **`scripts/`**: Includes Python scripts for tasks like data fetching.
*   **`src/`**: Contains the main source code for data preprocessing, modeling, and visualization.
*   **`requirements.txt`**: Lists the project's Python dependencies.
*   **`main.py`**: The main script to run the project.

## Setup and Installation

1.  **Clone the repository:**

    ```bash
    git clone https://github.com/ET-SPARK/Time-Series-Forecasting-for-Portfolio-Management-Optimization.git
    cd Time-Series-Forecasting-for-Portfolio-Management-Optimization
    ```

2.  **Create and activate a virtual environment:**

    ```bash
    python3 -m venv venv
    source venv/bin/activate
    ```

3.  **Install the required dependencies:**

    ```bash
    pip install -r requirements.txt
    ```

4.  **Fetch the data:**

    ```bash
    python scripts/fetch_data.py
    ```

## Task 1: Data Preprocessing and Exploration

In the first phase of the project, I performed data preprocessing and exploratory data analysis (EDA) in the `notebooks/01_exploratory_data_analysis.ipynb` notebook. The key steps included:

*   **Data Loading and Cleaning:** Loaded the historical data for TSLA, BND, and SPY, and ensured the data was clean and ready for analysis.
*   **Exploratory Data Analysis (EDA):**
    *   Visualized the closing prices over time to understand the long-term trends of the assets.
    *   Calculated and plotted the daily percentage change to observe and compare the volatility of the assets.
    *   Analyzed the volatility of TSLA's stock in more detail using rolling means and standard deviations.
*   **Stationarity Testing:**
    *   Conducted the Augmented Dickey-Fuller (ADF) test to check for stationarity in the time series data. The results showed that the closing prices are non-stationary, while the daily returns are stationary.
*   **Risk Assessment:**
    *   Calculated the Value at Risk (VaR) to quantify the potential for loss in the value of TSLA stock.
    *   Calculated the Sharpe Ratio to assess the risk-adjusted return of TSLA.

## Task 2: Develop Time Series Forecasting Models

In this task, I developed and compared two different time series forecasting models to predict Tesla's future stock prices:

*   **ARIMA Model:** A classical statistical model (AutoRegressive Integrated Moving Average). I used `auto_arima` to find the optimal model parameters (p, d, q).
*   **LSTM Model:** A deep learning model (Long Short-Term Memory), which is well-suited for sequence prediction problems.

The models were trained on historical data up to the end of 2023 and tested on data from 2024 onwards. The performance of the models was evaluated using Mean Absolute Error (MAE), Root Mean Squared Error (RMSE), and Mean Absolute Percentage Error (MAPE).

## Task 3: Forecast Future Market Trends

Using the trained ARIMA model, I generated a 12-month forecast of Tesla's stock price. This task involved:

*   **Generating the Forecast:** Forecasting future prices with confidence intervals to represent the range of uncertainty.
*   **Visualizing the Forecast:** Plotting the forecasted prices alongside the historical data.
*   **Analyzing the Results:** Interpreting the forecast to identify long-term trends, assess volatility and risk, and identify potential market opportunities.

## Task 4: Optimize Portfolio Based on Forecast

This task focused on constructing an optimal portfolio using the principles of Modern Portfolio Theory (MPT). The key steps were:

*   **Calculating Expected Returns:** Using the ARIMA forecast for TSLA's expected return and historical averages for BND and SPY.
*   **Computing the Covariance Matrix:** Based on the historical daily returns of all three assets.
*   **Generating the Efficient Frontier:** Running a Monte Carlo simulation to find the set of optimal portfolios.
*   **Identifying Key Portfolios:** Identifying and plotting the Maximum Sharpe Ratio Portfolio and the Minimum Volatility Portfolio.
*   **Recommending an Optimal Portfolio:** Providing a recommendation based on the analysis of the Efficient Frontier.

## Task 5: Strategy Backtesting

In the final task, I backtested the performance of the optimized portfolio strategy against a benchmark. This involved:

*   **Defining a Backtesting Period:** Using the last year of the dataset.
*   **Defining a Benchmark:** A simple 60% SPY / 40% BND portfolio.
*   **Simulating the Strategy:** Simulating the performance of the optimized portfolio over the backtesting period.
*   **Analyzing Performance:** Plotting the cumulative returns of the strategy and the benchmark, and calculating their total returns and Sharpe ratios.
*   **Drawing Conclusions:** Summarizing the backtest results to assess the viability of the model-driven investment strategy.
