# pair-trading_mean-reversion
- Pair trading of stock, seeking for high correlated pairs with stationary time series(spread or ratio), standardised the spread or ratio and test for it's normality. Based on the +-1 std to create long/short signals of the pairs.
### Steps Overview:
- Build up Data Frame of Stock Data
- Create Correlation Heatmap
- Set up parameters for stationarity testing, and create a function
  - parameters include: Adj Closed Price of asset_a and asset b, sprad of asset_a and asset_b, and ratio of them
  - Function generates the p-value of the parameters under ADF Test 
- Create for-loop function to feed the stock data, concatenating p-value results of the combination of single asset with the rest in one dataframe, then look for high correlation pair with stationary nature
- Once confirmed the pair
  - set up parameters: the pair's ratio, the ratio's Z-score, the short-term rolling mean of the ratio, and the long-term rolling mean, the long term rolling std, and the rolling Z-score
- Conduct Normality Test of the ratio_zscore
- Start the visualization for review and marking the trading signals
