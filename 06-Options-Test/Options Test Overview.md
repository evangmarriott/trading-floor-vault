# Options Paper Test: Overview

> **STATUS: ACTIVE PAPER TEST, started 2026-10-21.** PAPER ONLY. No broker, no API keys, no real money. Runs **alongside** the $10k crypto perps paper desk, which is **unchanged**. Separate ledger and files; never mix them.
> Adopted by Evan on 2026-10-21 (widget answers: "Start the options paper account at $100,000" and "Yes, set up the options paper test as described"). See [[2026-10-21-proposed-strategy-change]].

## Account
- Paper cash **$100,000** from 2026-10-21. Benchmark: **SPY buy-and-hold** from the 2026-10-21 close (773.09).
- Tooling: `/workspace/optdesk` (see its `README.md` for exact commands). Ledger `ledger.json`, append-only log `trades.csv`, daily marks `marks.csv`.
- Tickets: `TF-OPT-YYYYMMDD-NN` (distinct from the crypto desk's `TF-YYYYMMDD-NN`).

## Rules and limits (enforced in code by `ledger.py` risk check)
- **Universe (weekly, weekend):** ~40 US stocks. Price > $20, 50-day avg volume > 1M, above a rising 50-day SMA, positive 3-month and 1-month (> -3%) returns, last-quarter EPS beat, volume confirmation (20d avg ≥ 50d avg, or up-day volume > down-day volume over 20 sessions), and listed options with ≥ 5,000 OI in the first 30-45 DTE expiry. Ranked by momentum (60% 3m, 30% 1m, 10% volume ratio).
- **Signal (daily):** 8/21 EMA cross on daily bars. Bullish crosses get first look; names with EMA8 < EMA21 are skipped for new puts.
- **Trades:** sell cash-secured puts (CSPs), or covered calls (CCs) **only on shares held from assignment** (wheel). 30-45 DTE, |delta| 0.15-0.30, targeting ~0.20. Top 5 candidates per day, one per ticker.
- **Contract liquidity:** bid > 0, OI ≥ 100, spread ≤ max($0.15, 25% of mid).
- **Fills:** sell at the bid, buy to close at the ask, $0.65/contract commission. Assignment at expiration if ITM (CSP buys 100 sh/contract at strike; CC shares called away at strike). Daily marks at mid. Equity = cash + share value - option liabilities.
- **Risk:** max 20% of equity per ticker (CSP collateral + share value); max 5 open positions; no new position if earnings fall on/before expiry or within 7 days (unknown earnings date = refused and flagged); CSPs fully cash-secured, cash never negative.
- **Judge by total P&L including assignments, not win rate.** Never delete losing trades.

## Roles
| Role | Job | Command (from `/workspace/optdesk`) |
|---|---|---|
| Market & Research Analyst | Weekend screen; daily EMA signals | `.venv/bin/python screen.py`; `.venv/bin/python signals.py` |
| Strategist | Daily candidates + top 5; signal backtest | `.venv/bin/python candidates.py`; `.venv/bin/python backtest_signal.py` |
| Risk Manager | Pre-trade check (refuses breaches) | `.venv/bin/python ledger.py check --type CSP --ticker T --strike K --expiry YYYY-MM-DD --contracts N` |
| Execution Trader | Paper fills, expirations, marks | `ledger.py open ...`, `ledger.py close --ticket ...`, `ledger.py expire`, `ledger.py mark` |
| Trade Reviewer | Status + Monday report vs SPY | `ledger.py status`; reads `trades.csv`, `marks.csv` |
| Desk Lead | Daily summary to Evan; keeps it PAPER | reads `out/*.md` |

## Data source
Yahoo Finance via `yfinance` (about 15 min delayed). Delta is Black-Scholes with IV solved from the option mid (Yahoo IV fallback), risk-free rate from ^IRX (fallback 4.5%), no dividend adjustment. Earnings dates from Yahoo (`get_earnings_dates`, fallback `calendar`). Quotes pulled after the close are often stale or wide; prefer market hours (6:30 AM-1:00 PM PT) for candidates and fills.

## Schedule (PT)
- Sat/Sun: Analyst runs `screen.py`.
- Weekdays ~1:30 PM: Execution `expire` + `mark`; Analyst `signals.py`.
- Weekdays ~1:45 PM (or during market hours): Strategist `candidates.py` → Risk `check` → Execution `open`.
- Mondays: Trade Reviewer weekly report (options account reported separately from crypto).

## Known limits
- No free historical option prices, so only the **stock signal** can be backtested ([[Options Test Results]]); the options part has to prove itself going forward.
- Earnings season (late Oct-Nov) blocks most names under the earnings rule; expect few trades until it passes.

Related: [[Options Test Results]] · [[Hard Rules]] · [[Risk Limits]] · [[Strategy Index]]
