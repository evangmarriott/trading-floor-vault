# Desk Overview

- **What:** a six-bot trading desk run for Evan. See [[Roles]].
- **Mode:** **PAPER** only. No real money, no exchange account, no API keys.
- **Paper account:** $10,000 USD starting balance. Market: **crypto perpetual futures**.
- **Fills:** at the live public **OKX** perpetual swap price (USDT-margined) at the moment of execution, with **Hyperliquid** as the backup. Binance is geo-blocked from our computer, so it's not used for live data (Binance *historical* data from data.binance.vision is OK for backtests).
- **Costs modeled:** 0.05% taker fee per side + 0.05% slippage per side against us, plus funding at each OKX funding interval from the live rate.
- **Approval:** PAPER AUTO-APPROVE since Oct 21, 2026 (see [[Hard Rules]]).
- **Usage:** LOW-USAGE MODE since Oct 21, 2026 (see [[Routines and Modes]]).
- **Current balance, open positions, trades so far:** TBD (ask the Execution Trader / Trade Reviewer; record in [[Trade Log]]).
- **Proposed change:** Evan proposed moving toward stocks and options on Oct 21. **Not adopted.** See [[2026-10-21-proposed-strategy-change]].
Source: `/workspace/trading-floor/low-usage-mode.json` (bot descriptions as of Oct 21, 2026).
