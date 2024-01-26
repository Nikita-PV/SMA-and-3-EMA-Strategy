# SMA-and-3-EMA-Strategy
MA -- moving average  
SMA -- simple moving average  
EMA -- exponential moving average
## SMA Strategy
* "**traditional**" SMA:
Calculate moving averages of prices with different window sizes (denote «short» and «long» sizes 𝑠 and 𝑙 respectively, where 𝑠 < 𝑙). Thus, we get two new time series $(𝑀𝐴)_i^s$ and $(𝑀𝐴)_i^l$, 𝑖 = 1,..., 𝑛−1. When the short MA crosses and rises above the long one, it is a signal to buy stocks (long position). Opposite situation is a signal to sell stocks (short position). So trading actions take place only in the moments of intersection, change of time-series’ positions relative to each other.
* "**upgraded**" SMA:
Papailias F., Thomakos D. D., in their paper 'An Improved Moving Average Technical Trading Rule,' suggest the following modification: in order to remain in the market (not selling owned stocks), the current price should be greater than or equal to the entry price (the price at which we last bought stocks).

## Triple MA Crossover Strategy
Triple MA employs three moving averages with lengths T1 < T2 < T3 to help filter false signals:
* Enter a long position if MA(T1) > MA(T2) > MA(T3).
* Exit the long position if MA(T1) < MA(T2).
With the parameter 'mode', you can choose which moving average to use: EMA or SMA.

## Combined Strategy
The strategies above were combined by the following rule: if the current volatility deviates from the average by more than 2 standard deviations, then use the triple EMA crossover for the next 30 days.  

## Data Filtering
To filter returns, ARMA-GARCH was used.

## Backtest Metrics
For backtesting, metrics such as Value at Risk (VaR), Expected Shortfall (ES), Sharpe ratio, 
Rachev ratio, market beta, maximum drawdown, and cumulative returns were used.
