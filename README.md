# Market Efficiency Analysis

## Overview

This project empirically examines **weak-form market efficiency** by testing whether historical market returns exhibit statistically significant serial dependence.

The analysis uses daily **Nifty 50** market data and applies:

* Lag-1 autocorrelation
* Autocorrelation Function (ACF)
* Ljung–Box test

The analysis is implemented in **Python** and is designed to use publicly available market data retrieved through Yahoo Finance.

## Research Question

> Do historical Nifty 50 returns exhibit statistically significant serial dependence?

Under weak-form market efficiency, past price and return information should not provide systematic predictive information about future returns.

## Methodology

### 1. Market Data

* **Market:** Nifty 50
* **Ticker:** `^NSEI`
* **Frequency:** Daily
* **Data source:** Yahoo Finance
* **Observation window:** Five years of available data when the notebook is executed

### 2. Return Calculation

Daily percentage returns are calculated from adjusted closing prices:

`Return_t = (Price_t / Price_(t-1) - 1) × 100`

### 3. Lag-1 Autocorrelation

The first-order autocorrelation measures the linear relationship between a return and its immediately preceding return.

A value close to zero suggests limited first-order serial dependence.

### 4. Ljung–Box Test

The Ljung–Box test evaluates whether autocorrelations across the first 10 lags are jointly different from zero.

**Null hypothesis:** The tested autocorrelations are jointly zero.

A p-value above 0.05 indicates insufficient evidence to reject the null hypothesis.

## Key Results

In the analysed sample:

* **Lag-1 autocorrelation:** approximately **−0.0206**
* **Ljung–Box p-value, lag 10:** approximately **0.426**
* **Ljung–Box p-value, lag 1:** approximately **0.469**

The results do not provide statistically significant evidence of serial correlation at conventional significance levels.

## Interpretation

The findings are consistent with the absence of statistically significant serial dependence in the analysed sample.

Within the limitations of the selected data and testing framework, the results therefore **do not provide evidence against weak-form market efficiency**.

These results should not be interpreted as proof that markets are perfectly efficient. They indicate that the specific tests applied do not detect statistically significant serial dependence in the sample.

## Reproducibility

The analysis is contained in:

`notebooks/emh_serial_correlation.ipynb`

The notebook downloads market data when executed, meaning that numerical results may change as new observations become available.

No proprietary or confidential market dataset is required.

## Tools & Skills

**Python**

* `pandas`
* `yfinance`
* `matplotlib`
* `statsmodels`

**Finance & Econometrics**

* Market efficiency
* Time-series analysis
* Return analysis
* Autocorrelation
* Ljung–Box testing
* Statistical hypothesis testing
* Quantitative financial research

## Project Structure

```text
market-efficiency-analysis/
│
├── README.md
│
├── data/
│   └── README.md
│
└── notebooks/
    └── emh_serial_correlation.ipynb
```

## Author

**Dr. Pratibha Saini**

PhD Economics & Finance

Finance | Econometrics | Quantitative Research | AI × Finance
