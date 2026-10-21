# 2026-10-21: Proposed strategy change (stocks and options)

> **STATUS: PROPOSED. NOT ADOPTED.** Nothing here changes how the desk trades. The desk stays in PAPER mode on crypto perpetual futures under the current [[Hard Rules]] and [[Risk Limits]] until Evan adopts a change in his own words. No routines or bot profiles were changed.

## Evan's message (verbatim)
Posted by Evan in the Trading Floor group chat, Oct 21, 2026, around 1:10-1:16 PM PT.

> **VERBATIM TEXT NOT YET CAPTURED.** The vault builder couldn't read the chat transcripts (no transcript tool was available to it). Paste Evan's exact message here from the Desk Lead's transcript (agent bae8406a-1cbb-49fe-babe-5948c26cac5d), then delete this notice.

## What it covers (Sage's brief, not Evan's words; check it against the verbatim text)
- Switch the desk's focus toward **stocks and options**.
- A **weekly 40-name universe**.
- A **daily signal check** using **EMA and volume** rules.
- **Selling cash-secured puts and covered calls** at **30-45 DTE** and **0.15-0.30 delta**.
- Evan's own **3-week results: about 5%, with a 100% win rate on options**.
- **Two open assignments.**
Exact EMA lengths, volume thresholds, universe selection rules, position sizing, which tickers are assigned and at what strikes: TBD (from the verbatim message, or ask Evan).

## The desk's responses
> **NOT YET CAPTURED.** Paste the Desk Lead's, Strategist's (47ac966e-0c84-41fc-a864-5178a21cf547), Risk Manager's (c224169b-9905-489f-835f-af3e69e777cb) and any other bots' replies here, verbatim or closely quoted, with times.

## Open questions for Evan
1. **Which broker** for stocks/options (and is the paper account there or simulated by the desk)? TBD (ask Evan).
2. Is this **paper only** at first? (The current hard rule: PAPER until Evan says otherwise in his own words.)
3. Does it **replace** crypto perps or run **alongside** them? How is the $10,000 paper balance split?
4. How do the **risk limits** (3% per trade, 10% total risk, 5% daily loss) translate to short puts and covered calls, where the "stop" is assignment and collateral is the full strike × 100?
5. How do the **backtest + out-of-sample** gates apply to an options-selling strategy, and which historical options data source can we use?
6. **Ticket format** for options: add the strike, expiry, delta, premium and collateral to `TF-YYYYMMDD-NN` tickets?
7. **Data source** for equities/options quotes and Greeks (OKX/Hyperliquid don't cover them).
8. The two **open assignments**: should the desk track them in the [[Trade Log]] as Evan's own positions, or keep them separate from the desk's paper ledger?
9. How the 40-name universe is picked each week, and on which day.
10. Earnings and ex-dividend rules (avoid selling across earnings?).

## If adopted
Record Evan's exact adopting words and the date, update [[Hard Rules]], [[Risk Limits]], [[Strategy Index]], [[Routines and Modes]] and the bot profiles (keeping a backup like `full-mode-backup.json`), and log it in [[CHANGELOG]].
