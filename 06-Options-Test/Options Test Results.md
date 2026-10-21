# Options Paper Test: Results and Journal

PAPER ONLY. Facts from `/workspace/optdesk` outputs only. Never invent fills or P&L. Add newest entries at the top of the journal.

## Scoreboard (update weekly)
| Week ending | Equity | vs $100k | SPY B&H | vs SPY | Open | Assignments | Closed W/L | Realized | Notes |
|---|---|---|---|---|---|---|---|---|---|
| 2026-10-21 (start) | $100,000 | 0.00% | $100,000 (SPY 773.09) | 0 | 0 | 0 | 0/0 | $0 | Ledger initialized, no trades |

## Stock-signal proxy backtest (NOT an options backtest), run 2026-10-21
Window 2024-10-21 to 2026-10-21, daily Yahoo bars, point-in-time weekly screen, universe = today's 248-name list (survivorship bias). "Hold" = stock closed at or above the strike-like level at day 30 / 45.

| Group | N | Hold ~0.20Δ (≈9.6% OTM) 30d / 45d | Hold 8% OTM 45d | Avg / worst shortfall (0.20Δ, 45d) | Mean ret 45d |
|---|---|---|---|---|---|
| Screen + bullish EMA cross | 78 | 82.1% / 82.1% | 82.1% | -8.7% / -24.8% | +6.1% |
| Same, earnings rule applied | 35 | 91.4% / 88.6% | 82.9% | -9.3% / -13.4% | +6.1% |
| Watchlist, any Friday (no cross) | 3,506 | 81.5% / 80.8% | 79.2% | -7.9% / -42.0% | +3.5% |
| Whole universe, any Friday | 21,445 | 79.2% / 78.9% | 79.2% | -7.5% / -58.0% | +2.4% |

Read: the signal and earnings rule look a bit better than baseline, but samples are small (35-78 overlapping events) and it's one mostly rising regime. Losses when wrong average ~8-9% below strike, worst about -25%. Full report: `/workspace/optdesk/out/backtest_signal_2026-10-21.md`.

## Journal
### 2026-10-21
- Test set up. Ledger at $100,000, SPY benchmark 773.09. No trades opened (setup day).
- Screen: 40 names (e.g. ACN, MRNA, TEAM, DOCU, SHOP, MPC, NOW, ZS). Signals: 1 bullish cross (OKTA), 0 bearish; 39/40 EMA8>EMA21.
- Candidates: earnings season blocked most names. Only OKTA passed everything: CSP 185 put, 2026-11-20 (30 DTE), delta -0.21, bid 4.40 / ask 5.50, $18,500 collateral (after-hours quote). ZS 200P was refused (collateral $20,000 is a hair over 20% of equity once fees count); COST too expensive for the 20% cap.
