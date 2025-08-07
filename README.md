# Simple-Moving-Average-Strategy-on-Stable-vs.-Volatile-Stocks-Using-Rolling-Period-Analysis
# Moving Average Crossover Strategy Analysis

This project analyzes the effectiveness of a moving average (MA) crossover trading strategy using historical stock price data. The goal was to determine whether this strategy could outperform a buy-and-hold approach — especially when applied to stable vs. volatile stocks.

## Objective

To test whether using short and long simple moving average (SMA) crossovers improves compound annual growth rate (CAGR) over a buy-and-hold strategy, and to identify the best performing MA combinations across different stock volatility groups.

---

## Methodology

- **Backtest Framework**: A rolling 5-year window test, overlapping by one year per iteration, across 15 stable and 15 volatile stocks.
- **Strategy Logic**: Enter position when short MA crosses above long MA, and exit when it crosses below.
- **Evaluation Metrics**:
  - Win Rate (% of 5-year periods the strategy beat buy-and-hold)
  - Average CAGR Win % (average CAGR improvement when the strategy won)

---

## Results

- **Stable Stocks**:
  - Strategy only outperformed buy-and-hold in ~15–25% of 5-year periods.
  - Average CAGR improvement was modest (10–18%) in winning periods.
  - Most combinations underperformed passive holding.

- **Volatile Stocks**:
  - Strategy outperformed ~50% of the time on average.
  - CAGR improvements were significantly higher (100–300%, sometimes up to 350%) compared to stable stocks.
  - Short MAs between 10–20 and long MAs between 120–135 were among the best-performing combinations.

- **MA Group Classification**:
  - `Small-Small`: short MA 5–35, long MA 100–210
  - `Small-Big`: short MA 5–35, long MA 215–300
  - `Big-Small`: short MA 40–70, long MA 100–210
  - `Big-Big`: short MA 40–70, long MA 215–300

- **Top Combinations for Volatile Stocks**:
  - (5, 185), (10, 135), (15, 120), (15, 125), (20, 120)

- **Worst-Performing Group**: "Big-Small" combinations consistently underperformed in both stable and volatile groups.

---

## Limitations

- **Sample Size**: Only 15 stocks per group.
- **Historical Bias**: Results are based on past data and may not generalize.
- **No Transaction Costs**: Slippage and fees were not modeled.
- **Overfitting Risk**: Highlighted combinations may perform well in-sample but poorly out-of-sample.
- **Single Rolling Window Size**: 5-year window may not capture different market cycles.

---

## Future Work

- Expand to a broader dataset with sector diversity.
- Test other rolling periods (e.g., 3-year, 10-year).
- Incorporate machine learning.
- Conduct walk-forward or out-of-sample validation.

---

##  Technologies used

- **Python**: pandas, numpy, plotly, matplotlib
- **Data Source**: yfinance API
- **Backtesting**: Custom logic with rolling window analysis


