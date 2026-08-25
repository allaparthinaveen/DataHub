Daily chart-analysis prompt
----------
Act as a neutral technical-market analyst, not a trade-call provider.

Analyze only the information visible in the attached chart. Do not use future candles,
later market knowledge, or hindsight.

Instrument:
Market:
Date:
Timezone:
Chart timeframe:
Current price:
Opening price:
Trading session:
My maximum risk per trade:

Analyze:

1. Market structure:
   - Trend: bullish, bearish, or range
   - Higher highs/lows or lower highs/lows
   - Important support and resistance

2. Darvas box or range:
   - Box high
   - Box low
   - Is the box confirmed or still forming?
   - Is price inside, above, or below the box?

3. Momentum and confirmation:
   - Candle strength
   - Volume, if visible
   - EMA/MACD/RSI status, if visible
   - Whether the signal is confirmed at candle close

4. Scenarios:
   - Bullish scenario
   - Bearish scenario
   - No-trade scenario
   - Exact invalidation level for each scenario

5. Trade plan:
   - Entry trigger
   - Stop-loss location
   - First target
   - Risk-to-reward ratio
   - Whether the setup is already late or still actionable

6. Confidence:
   Give a confidence score from 0 to 100, but explain the uncertainty.
Do not give a BUY or SELL instruction unless the conditions are explicit.
If the chart does not provide enough information, say “insufficient data.”




-----------

Also ask the AI to produce three scenarios, not one prediction:

| Scenario | Condition                                          | Invalidation                       | Action                           |
| -------- | -------------------------------------------------- | ---------------------------------- | -------------------------------- |
| Bullish  | Candle closes above resistance with follow-through | Price falls back below resistance  | Consider only after confirmation |
| Bearish  | Price rejects resistance and closes below support  | Price reclaims the broken level    | Avoid chasing; reassess          |
| No trade | Price remains inside the range                     | Range expands without confirmation | Wait                             |

Important limitation
Do not ask the AI to produce a guaranteed daily “BUY/SELL prediction.” Ask it to produce:

A market-structure assessment.

Clear bullish and bearish conditions.

A no-trade condition.

Entry only after confirmation.

Stop-loss and invalidation.

A risk-based position size.
--------------


Use a structured morning workflow
For consistency, give the AI:

The same instrument and timeframe.

A clean screenshot taken before the trading session or at a defined time.

The current price and candle timestamp.

The previous day’s high, low, close, and volume.

Relevant support and resistance levels.

The exact indicator settings.

The market session and timezone.

Whether candles are closed or still forming.
Most importantly, separate:
A. What is already confirmed
B. What is only a possible future scenario
C. What would invalidate the view
