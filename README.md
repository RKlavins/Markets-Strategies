# Quant Finance Projects

Algorithmic trading strategies built, backtested, and validated using Python 
and AI-assisted development. Each project follows a rigorous research process: 
hypothesis → data analysis → strategy construction → stress testing → 
out-of-sample validation → live paper trading.

Built during summer 2025 as part of a self-directed quantitative finance 
curriculum, prior to starting BSc Economics at Stockholm School of Economics.

---

## Projects

### 1. Brent vs WTI Pairs Trading Strategy
**Folder:** `pairs-trading/`

A statistical arbitrage strategy exploiting the mean-reverting spread between 
Brent Crude and WTI Crude Oil futures. Uses a 20-day rolling Z-score to identify 
statistically unusual divergences and bet on convergence.

**Results:**
- Sharpe Ratio: 2.00 (out-of-sample, 2024-2026)
- Annualised Return: 13.3%
- Max Drawdown: -2.8%
- Validated across 5 time windows and 5 parameter thresholds
- Out-of-sample performance exceeds in-sample — no overfitting detected

**Key concepts:** Pairs trading, statistical arbitrage, Z-score, cointegration, 
market neutrality, walk-forward validation

---

### 2. Z-Score Mean Reversion — Crude Oil
**Folder:** `mean-reversion/`

Single-asset mean reversion strategy on WTI Crude Oil futures. Uses a rolling 
Z-score to identify when price has deviated significantly from its recent mean 
and enter positions expecting reversion.

**Results:**
- Sharpe Ratio: 0.68
- Total Return: 48% vs -6.7% buy and hold (2022-2024)
- Demonstrates why mean reversion strategies suit range-bound commodities

**Key concepts:** Rolling statistics, Z-score, mean reversion vs trend following, 
Sharpe ratio, drawdown analysis

---

### 3. Regime-Switching Strategy — SPY
**Folder:** `regime-switching/`

A hybrid strategy that first classifies the market regime (bullish, bearish, 
or ranging) using moving average relationships, then applies appropriate 
Z-score signals for each regime. Only buys dips in bull markets, only shorts 
rallies in bear markets, and trades both sides in ranging markets.

**Results:**
- Annualised Return: 12.1% vs 10.0% SPY buy and hold
- Demonstrates the importance of matching strategy type to market regime

**Key concepts:** Regime detection, golden/death cross, adaptive strategy 
selection, market regimes

---

## Stack
- **Python** — pandas, numpy, matplotlib, scipy
- **Data** — yfinance (market data), investing.com (commodity futures)
- **Environment** — Google Colab
- **Execution** — Alpaca Markets API (paper trading)
- **AI assistance** — Claude (Anthropic) for development, debugging, and research

---

## Methodology
All strategies follow the same validation pipeline:

1. **Hypothesis** — identify a market phenomenon with economic logic
2. **Data exploration** — understand the asset's statistical properties
3. **Strategy construction** — build signal, position, and return logic
4. **Initial backtest** — evaluate on in-sample data
5. **Stress testing** — multiple time windows + transaction costs
6. **Sensitivity analysis** — test across range of parameters
7. **Out-of-sample validation** — evaluate
