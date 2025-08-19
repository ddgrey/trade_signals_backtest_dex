# Backtesting z-score-based mean reversion signals on PHI/WSOL (17-18 Aug 2025, 21h interval) with grid search optimization.

## Project goals
1. Build foundational experience in DEX-based algorithmic trading using Python and statistical methods.
2. Demonstrate genuine commitment to career growth as a quant trader and/or developer together with Peanut Trade.
3. Explore the practical power of statistics in financial strategy design — and of course, enjoy the process!

## Briefly about project
* **Coin Pair**: The [PHI/WSOL pair](https://dexscreener.com/solana/2rkzjad7ssues6yxoujsafcbyjxw6t4h9avgirwydjdw) was randomly selected to test a mean-reversion algorithm.  
  *Phi Protocol enables AI-driven trading across multi-chain assets, enhanced by analytics and Wormhole-based bridging.*
* **[Swap Data](dex_pair_swap_fetching_MoralisAPI.ipynb)**: Market data was retrieved via the [Moralis](https://moralis.com/) Web3 API for the period of August 17–18, 2025.
* **Algorithm**: A z-score-based strategy determines long/short positions using rolling VMAP (blue line), standard deviation of price-to-VMAP deviations, and std threshold-based signal generation (e.g., z-score > *std threshold\* → 'short').
* **[Python File](trade_signals_phi_wsol_backtest.ipynb) Workflow**: Fetch swap data via Moralis API → Load data → Aggregate OHLC candles → Compute VWAP z-score signals → Clean signal cycles (long/short signals shown in gray are noise) → Backtest parameter grid → Evaluate performance metrics (win rate, # of trades, median/max returns, max drawdown (i.e. largest peak-to-trough equity decline)) → Rank top configurations → Visualize results.  
**Can be used for any swap pair (reusable)**.

  <p align="left">
    <img src="https://drive.google.com/uc?export=view&id=1n_g68CWbtz6UmOIkaySEGcukGjvlKF_o" width="900">
  </p>
  <p align="center">Example visualization of a high-performing parameter set</p>
  <p align="center">100% Win Rate | 11 Trades | 9% Median Return per Trade | 21% Max Return</p> 
  <p align="center">[ yet 11 trades over ~1 day is too small to claim statistical significance ]</p> 

## Results
### Top 5 Parameter Configurations

  <p align="left">
    <img src="https://drive.google.com/uc?export=view&id=1lu8u7iSS-Ovd33JmRB1Li7_2q4gwMr6g" width="450">
  </p>
  
  <p align="left">
    <img src="https://drive.google.com/uc?export=view&id=1txK6fARVEQEnIQ-yBgk6KZE35OluriJo" width="800">
  </p>
  
**Metric Descriptions**
- **`win_rate_%`** — Percentage of trades that closed profitably  
- **`n_trades`** — Total number of executed trades in the backtest  
- **`median_change_%`** — Median percentage return per trade  
- **`max_change_%`** — Highest percentage return from a single trade  
- **`max_drawdown_%`** — Largest peak-to-trough equity decline during the test

### Key Takeaways
* **Strong Short-Term Results**: All top 5 configurations hit 100% win rate with zero drawdown in a 21‑hour window, likely reflecting a temporary period of strong mean reversion in PHI/WSOL. The results aren’t statistically significant — they serve as a proof of concept, not a validated live strategy.
* **Robust Across Parameters**: Consistent performance across settings suggests the VWAP z‑score logic is effective; next step is out‑of‑sample and cross‑pair testing.

---

***This experience has solidified my intention to work in quantitative trading. I am confident in my ability to learn quickly and make valuable contributions, and I would welcome the chance to start that journey with Peanut Trade.***

[**LinkedIn**](https://www.linkedin.com/in/dvyemchuk/) | [**Telegram**](https://t.me/ddgrrey)
