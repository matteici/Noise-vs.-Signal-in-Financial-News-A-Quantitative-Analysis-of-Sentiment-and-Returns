# Sentiment-Based Stock Return Analysis – README

## Overview

This Jupyter Notebook provides a comprehensive pipeline for analyzing the relationship between news sentiment and stock returns. It covers data ingestion, sentiment extraction, regression analysis, grid search for model optimization, and backtesting of sentiment-driven trading strategies.

## Main Steps

1. **Data Loading & Preprocessing**
    - Loads company metadata and news headlines.
    - Cleans company names and matches headlines to tickers using FlashText.

2. **Sentiment Extraction**
    - Uses VADER to score sentiment for each company mentioned in news headlines.
    - Aggregates sentiment scores by date and ticker.

3. **Stock Price Data**
    - Downloads historical price data for all mentioned tickers using Yahoo Finance.
    - Computes daily returns and rolling volatility.

4. **Regression Analysis**
    - Runs OLS regressions to test the predictive power of sentiment (and compounded sentiment) on future returns.
    - Supports lagging, extreme filtering, and compounding of both sentiment and returns.

5. **Grid Search**
    - Systematically tests combinations of model parameters to find optimal settings.
    - Results are saved and visualized.

6. **Backtesting**
    - Implements multiple sentiment-based trading strategies with volatility-adjusted position sizing.
    - Evaluates performance using metrics like Sharpe ratio, drawdown, and win/loss statistics.

7. **Placebo Tests**
    - Runs placebo experiments by shuffling or shifting sentiment data to validate model robustness.

## Key Files

- `company_data_rework.csv`: Company metadata.
- `news_benzinga.csv`: News headlines.
- `exptest2_27_04_stock_price_data.pkl`, `exptest2_27_04_sentiment_by_ticker.pkl`: Saved intermediate data.
- `eda_outputs/`: Folder for summary statistics and plots.
- `figures_for_overleaf/`: Publication-ready figures.

## Requirements

- Python 3.7+
- Packages: pandas, numpy, scikit-learn, statsmodels, matplotlib, seaborn, flashtext, vaderSentiment, yfinance, joblib, scipy

## Usage

1. **Install dependencies** (handled in the first cell).
2. **Run all cells sequentially** to reproduce the full analysis.
3. **Modify parameters** in grid search or backtest sections to experiment with different strategies.

## Outputs

- Regression summaries and coefficient plots.
- Grid search results for model selection.
- Backtest performance metrics and equity curves.
- Placebo experiment results for robustness checks.

## Notes

- Ensure all required data files are present in the working directory.
- Some cells may take time to execute due to data downloads and model fitting.
- Results can be exported for further analysis or publication.

---
