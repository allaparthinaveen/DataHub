# V2 Confluence Engine — First Pine Script Version

## Default profile
High R:R + Strong Confirmation, with 15-minute primary decision timeframe.

## Intended instruments
- NIFTY / Indian indices
- US stocks and other liquid TradingView symbols

## Included
- Higher-timeframe trend regime
- 15M primary setup logic
- 5M confirmation
- Momentum (RSI + DMI/ADX)
- Relative strength vs configurable benchmark and sector/comparison symbol
- VWAP
- Optional anchored-VWAP proxy
- Relative volume
- ATR/volatility-aware structural stops
- Previous-day high/low
- Opening range
- Liquidity sweep proxies
- Breakout/breakdown acceptance and retest proxies
- Optional Darvas evidence
- Confluence scoring
- High-R:R confirmation entries
- Strategy backtesting
- T1/T2 exits
- Dashboard
- LONG/SHORT/WAIT state
- TradingView alerts

## Important notes
1. Put the chart on 15 minutes for the primary engine.
2. Set Benchmark and Sector/Comparison Symbol appropriately for the instrument. For US stocks, common choices are SPY and an appropriate sector ETF.
3. The default minimum R:R is 2.0. This is a starting parameter, not a claim of profitability.
4. News/catalyst interpretation is not reliably available inside Pine. Use external/current market context as a separate validation layer.
5. The Anchored VWAP option is implemented as a configurable VWMA proxy in this first version; true event-anchored AVWAP can be added in a later version.
6. The script is a rules-based research/backtesting tool, not financial advice or a guarantee of profit. Validate with out-of-sample testing, realistic commissions/slippage, and the exact symbol/session you trade.
7. Do not assume a backtest result will persist in live markets.
