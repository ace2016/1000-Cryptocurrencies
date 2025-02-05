# 1000-Cryptocurrencies
Analyzing 1000 Cryptocurrencies: Insights from Historical Trading Data

The dataset can be downloaded from this link: [1000 Cryptocurrencies by Dr Aare](https://drive.google.com/file/d/1Nb4UARMDHD0Idsoe4Vypxw_a61imUAfN/view?usp=sharing)

I performed some EDA process and discovered some missing values and outliers. The missing values were handled using FFill/BFill, volume was replaced with '0', any other data missing after this was removed. Outliers were left untouched due to the spikes that happens in the crypto market but were well noted.

[QUESTIONS](https://oaorogun.co.uk/analyzing-1000-cryptocurrencies-insights-from-historical-trading-data/) can be assessed via the link

1. Price Trends Over Time – Show price movements of major cryptocurrencies. Identify long-term upward or downward trends for major cryptocurrencies like Bitcoin and Ethereum.

**Key Insights from price trends**
1. Bitcoin and Ethereum dominate the market in terms of price growth.
2. Logarithmic scaling is necessary to visualize the wide price range effectively.
3. Cryptocurrency prices are highly volatile, with major peaks and corrections.
4. USDT remains stable, while XRP shows fluctuations but at a lower price.

2. Volatility Analysis – Calculate daily percentage changes to determine the most volatile assets. Also, identifying highly volatile cryptos using 30 days volatility flunctuations, helping investors assess risk.

* Most Volatile Cryptos
	* Daily Returns (Short-Term): BASE27789-USD, AKITA-USD, BABYPEPE31752-USD.
	* Rolling Volatility (Long-Term): SHRUB-USD, ZKL-USD, INF-USD.
* Least Volatile Cryptos
	* AIDOGE-USD, BABYDOGE-USD (short-term), ZUKI-USD (long-term).
* Short-term traders should focus on daily percentage changes, while long-term investors should monitor rolling volatility.
* Combining both metrics helps create a balanced investment strategy, avoiding excessive risk while still capturing profitable opportunities.

3. Trading Volume Patterns – Analyze how trading volumes fluctuate over time and across different assets (Major Cryptocurrencies)

**Bitcoin (BTC-USD)**
* Bitcoin’s trading volume exhibits periodic spikes, especially around bull runs and corrections.
* A massive spike (around 2021) suggests a liquidity surge—possibly due to institutional adoption or panic-driven selling.

**Ethereum (ETH-USD)**
* ETH trading volume follows BTC’s trends but at a lower scale.
* Likely influenced by DeFi and NFT activity, as Ethereum is the foundation for these markets.
* Steady activity even post-2022 suggests it remains a critical crypto asset.

**Litecoin (LTC-USD)**
* LTC has significantly lower volume than BTC and ETH.
* Its trend closely mirrors BTC, but with much lower engagement, indicating its secondary role in the market.

**Tether (USDT-USD)**
* USDT dominates trading volume, often surpassing BTC.
* This suggests that stablecoins are the primary liquidity providers in crypto, as traders move in and out of assets using USDT.
* Volume remains consistently high, proving its importance in crypto exchanges.

**Ripple (XRP-USD)**
* XRP has modest but consistent trading volume.
* The lack of sharp spikes suggests it is less speculative and more utility-driven (e.g., for cross-border transactions).

**Predictions Based on Volume Trends**
* High and volatile volume suggests ongoing market speculation.
* If BTC and ETH trading volumes increase alongside prices, it could indicate another bull cycle.
* If stablecoins like USDT maintain dominance, it means traders are sitting in cash, waiting for market direction.

4. Correlation Analysis
**Understanding the Heatmap**

* Correlation Values (Range: -1 to 1)
	* 1.0 (Red) → Perfect positive correlation (Both move together).
	* 0.5 to 0.9 (Light red/grayish) → Strong positive correlation.
	* 0.0 to 0.4 (Blue shades) → Weak or no correlation.
	* -1.0 (Dark blue, if present) → Perfect negative correlation (Move in opposite directions).

* Diagonal Values (All 1.0)
	* Each cryptocurrency is perfectly correlated with itself (hence, 1.0 on the diagonal).

**Observations**
**Bitcoin (BTC-USD)**
* High correlation (Above 0.6) with:
	* LTC-USD (Litecoin)
	* DASH-USD (Dash)
	* XLM-USD (Stellar)
	* LSK-USD (Lisk)
	
	These are assets that often follow BTC’s price movements due to market trends and investor sentiment.

* Moderate correlation (~0.5) with:

	* LINK-USD (Chainlink)
	* XMR-USD (Monero)
	* POWR-USD (Power Ledger)
		
	These might be influenced by Bitcoin but also follow their own trends.

* Weak correlation (~0.3 or less) with:

	* ANT-USD (Aragon)
	* PXC-USD (Phoenixcoin)
	* AVT-USD (Aventus)

	These assets seem to have independent price movements.

**Litecoin (LTC-USD)**
* Highest correlation with BTC-USD (~0.69)
* Strongly correlated with DASH-USD (~0.64)
	* Litecoin often mirrors Bitcoin’s movements but with different volatility.
	* Dash, being a peer-to-peer payment coin, follows a similar path.

* USDT (Stablecoins) Correlation
	* Stablecoins (like USDT) aren’t included here, but if they were, they would show low correlation with volatile assets.

**IMPLICATIONS**
1. Diversification Strategy:
	* If you're holding multiple highly correlated assets, you’re not truly diversified.
	* For real diversification, you should include weakly or negatively correlated assets.
2. Market Sentiment Indicator:
	* Strong correlations suggest a highly interdependent crypto market.
	* A sudden drop in correlation between BTC and altcoins may indicate an upcoming shift in market trends.
3. Trading Strategy:
	* High-correlation pairs can be used for hedging strategies.
	* Low-correlation pairs are good for pair trading (long one, short the other).

5. Top Gainers & Losers – Find the best and worst-performing cryptos over different periods.

1-day, 7-day, 30-day

* AIDOGE-USD was a consistent gainer over the period, alongside AKITA-USD

6 Price Predictions using Machine Learning and deep learning

Considering major cryptocurrencies such as (['BTC-USD', 'ETH-USD', 'USDT-USD', 'XRP-USD', 'LTC-USD'])

ARIMA (AutoRegressive Integrated Moving Average) – Best for time series forecasting when data is stationary.
Since the P-value is greater than >0.05 then we cannot use ARIMA
LSTM (Long Short-Term Memory Neural Network) – A deep learning approach that captures long-term dependencies in sequential data was adopted alongside a Temporal Fusion Transformer for comparison.

Also, developed a personal function to predict the prices based on previous generation using a rolling forecast of 30 days.

The following evaluation metrics were generated;

|Metric | BTC-USD (Bitcoin) | ETH-USD (Ethereum) | USDT-USD (Tether) | XRP-USD (XRP) | LTC-USD (Litecoin) |
| ---- | --- | ---- | ---- | ---- | ---- |
| LSTM - MAE |1974.20 |	99.31 |	0.00 | 0.11 | 2.98 |
| LSTM - RMSE |	2838.73 | 135.95 |	0.00 |	0.25 |	4.52 |
| LSTM - MAPE |	3.78% |	3.43% |	0.04% |	7.59% |	3.53% |
| LSTM - R² | 0.9852 | 0.9609 | 0.2676 | 0.8588 | 0.9157 |
|Transformer - MAE | 37048.15 |	1550.40	| 0.00 | 0.31 | 13.45 |
|Transformer - RMSE | 43802.10 | 1695.96 | 0.00 | 0.74 | 18.45 |
|Transformer - MAPE | 66.94% | 52.79% | 0.12% | 19.01% | 14.75% |
|Transformer - R² |	-2.5136 | -5.0870 | -4.0466	| -0.2075 |	-0.4012 |


Insights:

1️. LSTM consistently outperforms the Transformer model across all cryptocurrencies.
2️. Transformers perform exceptionally poorly on Bitcoin (BTC-USD) and Ethereum (ETH-USD), likely due to improper hyperparameter tuning or lack of enough data (maybe if model is trained constantly with live data) for attention-based models.
3️. Stablecoins (USDT-USD) show near-perfect results with both models, likely due to their low volatility.
4️. For XRP & Litecoin, LSTM still provides significantly better R² and lower errors.
5️. R² Scores for Transformer models are all negative, meaning they perform worse than a naive model that just predicts the mean.

The function for the rolling average performed similarly to the transformer.


_Summary_

The LSTM is production-ready, while the Transformer and Rolling Forecast require significant reworking. 
The evaluation metrics definitely changes with constant training and if the hyperparameters are tweaked. But using Opuna and finding the best parameters slows down my PC. 

**However**, there is a second implementation of the rolling forecast which I have very much indicated where I have tuned the hyperparameters to some extent.

_This project can be pushed further through the following below_
* Get live data for Sentiment Analysis – Combining with external data (news, tweets) for sentiment-driven analysis.
* Anomaly Detection – Identify unusual price spikes or crashes.
* Risk vs. Reward – Measure risk-adjusted returns using Sharpe ratio, VaR.
* Support & Resistance Levels – Identify key price points where buying/selling is strong.
* RSI & Momentum Indicators – Use technical indicators to signal overbought/oversold assets.
* Diversification Opportunities – Identify stable coins or cryptos with low correlation.

I would release more updates as I can, but anyone is free to collaborate on the project and add updates to my codebase. Especially in improving my function "improved_rolling_forecast_v2".

The code file is detailed and well commented. Cheers!

