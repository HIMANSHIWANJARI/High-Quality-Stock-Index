# High-Quality-Stock-Index
## Overview

This project builds a **factor-based equity index** using NSE large and mid-cap stocks.
The index selects financially strong companies using **quality (ROE, Debt)** and **momentum factors**, and evaluates performance against the NIFTY 50 benchmark.

---

## Objective

To construct a **rule-based, investable portfolio** of high-quality companies that aims to deliver **better risk-adjusted returns** than the benchmark.

---

## Methodology

### 1. Data Collection

* Price & Volume: yfinance
* Fundamentals: ROE, Debt-to-Equity dataset
* Universe: NSE Large & Mid-cap stocks

---

### 2. Data Preprocessing

* Handled missing values (NaNs) using forward fill and filtering
* Removed stocks with insufficient data
* Aligned price and fundamental datasets

---

### 3. Filtering Criteria

* ROE ≥ 8%
* Debt-to-Equity ≤ 5
* ADTV ≥ ₹3 Crore

---

### 4. Ranking (Multi-Factor Model)

Stocks are ranked using:

* Profitability → ROE (higher is better)
* Stability → Debt (lower is better)
* Momentum → recent returns

**Composite Score = ROE Rank + Debt Rank + Momentum Rank**

---

### 5. Stock Selection

* Top ~20 stocks selected (range: 15–25)
* Ensures flexibility and quality

---

### 6. Portfolio Construction

* Equal weighting (1/N allocation)
* Reduces concentration risk
* Improves diversification

---

### 7. Rebalancing

* Frequency: Quarterly (Mar, Jun, Sep, Dec)
* Reapply filters and rankings
* Reset weights

---

### 8. Performance Metrics

* Total Return
* Annualized Return
* Volatility
* Sharpe Ratio
* Maximum Drawdown
* Turnover

---

## Key Results

### Performance Comparison vs NIFTY 50

| Metric                          | Your Index  | NIFTY 50    |
| ------------------------------- | ----------- | ----------- |
| Total Return (%)                | **179.20%** | **60.17%**  |
| Annualized Return (%)           | **35.09%**  | **14.91%**  |
| Annualized Volatility (%)       | **19.54%**  | **13.97%**  |
| Sharpe Ratio                    | **1.23**    | **0.57**    |
| Maximum Drawdown (%)            | **-18.12%** | **-17.23%** |
| Avg. Turnover per Rebalance (%) | **35.67%**  | —           |

---

## Interpretation

* The custom index **significantly outperformed** the benchmark in both total and annualized returns
* The **Sharpe ratio is substantially higher**, indicating better risk-adjusted performance
* Volatility is moderately higher due to active stock selection
* Maximum drawdown is comparable, showing controlled downside risk
* Turnover (~35.7%) reflects an actively managed and dynamically rebalanced portfolio

---

## Sensitivity Analysis

Compared:

* Equal Weight vs Market Cap Weight

* Market cap weighting achieved higher returns and Sharpe ratio

* Equal weighting provided better diversification and lower volatility

---

## Advantages

* Data-driven and rule-based approach
* Multi-factor model (quality + momentum)
* Diversified portfolio construction
* Dynamic quarterly rebalancing

---

## Limitations

* Higher turnover (~30–40%) leading to potential transaction costs
* Transaction costs not included in backtesting
* Dependence on data quality
* Momentum factor may underperform in volatile markets

---

## Tech Stack

* Python
* Pandas
* NumPy
* Matplotlib
* yfinance

---

## Conclusion

This project demonstrates how **factor-based investing** can be used to build a **systematic and adaptive portfolio**.
The results indicate that combining quality and momentum factors can potentially generate **alpha over the NIFTY 50**, while maintaining reasonable risk levels.
