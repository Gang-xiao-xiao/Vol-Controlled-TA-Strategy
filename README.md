# Vol-Controlled-TA-Strategy
This project implements and evaluates a rule-based quantitative trading strategy using Python. It combines moving averages, volatility bands (via GARCH), dynamic position sizing, and risk management tools like cooldown periods and stop-loss.
📌 Overview

We use historical price data of SPY ETF to simulate a trading strategy under different enhancements and evaluate it using standard financial metrics.

📂 Project Structure

Module	Description
get_data()	Download SPY data using yfinance
calculate_returns()	Compute daily returns
adjust_dynamic_channel()	Generate dynamic trading bands using GARCH volatility
backtest_strategy_with_cooldown()	Core strategy using fixed thresholds and cooldown period
backtest_strategy_with_trend_filter()	Add trend filter with short and long MAs
backtest_strategy_with_stop_loss()	Add stop-loss condition (e.g., sell if price drops 10%)
backtest_with_dynamic_position()	Adjust position size based on volatility
backtest_with_optimized_volatility()	Test different smoothing factors for position sizing
calculate_metrics()	Compute Max Drawdown, Annualized Return, Sharpe Ratio
calculate_benchmark_metrics()	Evaluate buy-and-hold baseline
visualize_signals()	Show buy/sell signals on price chart
visualize_signals_with_trend()	Show strategy with MAs and dynamic channels
🔍 Features

✅ Rolling mean + dynamic volatility bands as entry/exit signals
✅ Cooldown mechanism to limit over-trading
✅ Trend confirmation using MA crossovers
✅ Stop-loss handling to cap downside risk
✅ Volatility-adjusted position sizing (like risk parity)
✅ Strategy performance benchmarking vs Buy-and-Hold
✅ Parameter tuning for GARCH-based position scaling
✅ Visualizations for price, signals, and risk exposure
📊 Metrics Used

Max Drawdown
Annualized Return
Sharpe Ratio
🚀 How to Run

Install dependencies:
pip install yfinance matplotlib pandas arch
Run the notebook step by step (1051_project3.ipynb)
📈 Sample Result

| Strategy                | Final Value | Sharpe Ratio | Max Drawdown |
| ----------------------- | ----------- | ------------ | ------------ |
| Cooldown Only           | \$10,500    | 0.95         | -12.5%       |
| + Trend Filter          | \$11,200    | 1.05         | -10.1%       |
| + Stop-Loss             | \$10,900    | 1.00         | -9.3%        |
| + Dynamic Position Size | \$11,800    | 1.20         | -8.5%        |


Include more ETFs and test across different asset classes
Perform walk-forward validation
Integrate machine learning models for regime detection
Deploy as a live dashboard or backtest engine
