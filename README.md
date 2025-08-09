# Time Series Forecasting for Portfolio Management Optimization

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
