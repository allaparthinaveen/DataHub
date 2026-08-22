🧠 The whole strategy in ONE picture
                         EVERY NEW CANDLE
                                │
                                ▼
                    ┌─────────────────────┐
                    │ 1. FIND PIVOTS      │
                    │ Pivot High / Low    │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │ 2. BUILD DARVAS BOX │
                    │                     │
                    │      TOP ─────────  │
                    │      │              │
                    │      │ CONSOLIDATION│
                    │      │              │
                    │      ───────── BOTTOM│
                    └──────────┬──────────┘
                               │
                               ▼
                  ┌──────────────────────────┐
                  │ 3. IS THIS A VALID BOX? │
                  │                          │
                  │ ✓ Small enough?          │
                  │ ✓ Enough bars?           │
                  │ ✓ No spike outside?      │
                  └────────────┬─────────────┘
                               │
                     NO ───────┤────── YES
                     │                   │
                     ▼                   ▼
                 WAIT / RESET       BOX ACTIVE
                                         │
                                         ▼
                          ┌────────────────────────┐
                          │ 4. BREAKOUT / BREAKDOWN│
                          └───────────┬────────────┘
                                      │
                       ┌──────────────┴──────────────┐
                       │                             │
                 CLOSE > TOP                    CLOSE < BOTTOM
                       │                             │
                       ▼                             ▼
                🟢 BULLISH BO                    🔴 BEARISH BD
                       │                             │
                       └──────────────┬──────────────┘
                                      │
                                      ▼
                           WAIT FOR RETEST
                                      │
                                      ▼
                         ┌────────────────────┐
                         │ 5. PRICE RETURNS   │
                         │ TO BROKEN LEVEL    │
                         └─────────┬──────────┘
                                   │
                                   ▼
                            RETEST TOUCHED
                                   │
                                   ▼
                         ┌────────────────────┐
                         │ 6. REJECTION?      │
                         │                    │
                         │ Close back in the  │
                         │ breakout direction │
                         └─────────┬──────────┘
                                   │
                         ┌─────────┴─────────┐
                         │                   │
                        NO                  YES
                         │                   │
                         ▼                   ▼
                       WAIT             RETEST OK
                                             │
                              ┌──────────────┴──────────────┐
                              │                             │
                         2-STAGE                       3-STAGE
                         DEFAULT                       OPTIONAL
                              │                             │
                              ▼                             ▼
                       🎯 SIGNAL NOW                 WAIT AGAIN
                                                            │
                                                            ▼
                                                   CONTINUATION
                                                            │
                                                            ▼
                                                       🎯 SIGNAL


1. First: What is the script actually trying to find?

It is NOT simply looking for a breakout candle.

The strategy wants:

A clean consolidation → breakout → retest → rejection → confirmed directional move.

So mentally, forget the code for a moment.

Imagine this:

PRICE

       ───────────────────────  BOX TOP
       │                      │
       │    ↕    ↕    ↕       │
       │   CONSOLIDATION      │
       │    ↕    ↕    ↕       │
       │                      │
       ───────────────────────  BOX BOTTOM
                    │
                    │
                    ▼
                 BREAKOUT
                    │
                    ▼
                  RETEST
                    │
                    ▼
                 REJECTION
                    │
                    ▼
                 SIGNAL

18. Now put EVERYTHING together
Here's the complete mental model I would use when looking at your script:
                        ┌───────────────┐
                    │ NEW CANDLE    │
                    └───────┬───────┘
                            ↓
                  ┌───────────────────┐
                  │ Find Pivot High   │
                  └─────────┬─────────┘
                            ↓
                  ┌───────────────────┐
                  │ Find Pivot Low    │
                  └─────────┬─────────┘
                            ↓
                  ┌───────────────────┐
                  │ Build Candidate   │
                  │ Darvas Box        │
                  └─────────┬─────────┘
                            ↓
              ┌────────────────────────────┐
              │ VALID BOX?                 │
              │                            │
              │ Height <= 4%               │
              │ Enough consolidation       │
              │ Price contained            │
              └─────────────┬──────────────┘
                            │
                    NO ─────┴───── YES
                    │               │
                    │               ▼
                    │          BOX ACTIVE
                    │               │
                    │               ▼
                    │       ┌───────────────┐
                    │       │ BREAKOUT?      │
                    │       └───────┬───────┘
                    │               │
                    │       ┌───────┴───────┐
                    │       │               │
                    │     BULL             BEAR
                    │       │               │
                    │       ▼               ▼
                    │     BO 🟠           BD 🟠
                    │       │               │
                    │       └───────┬───────┘
                    │               ↓
                    │          STATE = 1
                    │               │
                    │               ▼
                    │          WAIT RETEST
                    │               │
                    │       ┌───────┴────────┐
                    │       │                │
                    │    RETEST            TIMEOUT
                    │       │                │
                    │       ▼                ▼
                    │   TOUCH LEVEL       CANCEL
                    │       │
                    │       ▼
                    │   WAIT NEXT BAR
                    │       │
                    │       ▼
                    │    REJECTION?
                    │       │
                    │   ┌───┴────┐
                    │   │        │
                    │  NO       YES
                    │   │        │
                    │   │        ▼
                    │   │   2-STAGE?
                    │   │        │
                    │   │   YES──┴──NO
                    │   │    │       │
                    │   │    ▼       ▼
                    │   │  🎯CALL   STATE=2
                    │   │  🎯PUT       │
                    │   │              ▼
                    │   │       WAIT CONTINUATION
                    │   │              │
                    │   │         ┌────┴────┐
                    │   │         │         │
                    │   │       YES        TIMEOUT
                    │   │         │         │
                    │   │         ▼         ▼
                    │   │       🎯SIGNAL   CANCEL
                    │   │
                    └───┴────────────────────
                                                       
