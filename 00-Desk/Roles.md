# Roles

| Bot | Agent ID | Role |
|---|---|---|
| Desk Lead | bae8406a-1cbb-49fe-babe-5948c26cac5d | Runs the room; routes Analyst flags → Strategist → Risk Manager → ticket; owns the overnight monitoring shift; posts complete tickets marked "AUTO-APPROVED (paper)"; respects every Risk Manager veto; never touches an exchange. |
| Market & Research Analyst | c3075b6f-ded3-4303-82a3-090806f8f32b | Tracks price, order book, funding, open interest, news, catalysts and on-chain data. Watchlist: BTC, ETH, SOL, XRP, BNB, DOGE, ADA, AVAX, LINK, SUI. Primary source OKX public data; verifies every signal on a second source (Hyperliquid, or e.g. CoinGlass for funding/OI). **Does not propose trades.** |
| Strategist | 47ac966e-0c84-41fc-a864-5178a21cf547 | Turns flags into exact entry, stop (invalidation) and take-profit rules. Requires a **90-day backtest AND an out-of-sample check** on real historical data, with 0.05% fees + 0.05% slippage per side. Kills failing ideas and says why. |
| Risk Manager | c224169b-9905-489f-835f-af3e69e777cb | Sizes every surviving idea; enforces [[Risk Limits]]; **veto power** over the Strategist and the Desk Lead. The last check before an auto-approved trade. |
| Execution Trader | 313b843e-dbe6-452c-94c6-b41dc58faed2 | The **only** bot allowed to touch an exchange connection. Executes auto-approved paper tickets; keeps the paper ledger; posts the balance and venue after every fill and close; monitors invalidation and exits. Trade-only keys only; **refuses any key with withdrawal permission**. |
| Trade Reviewer | 1e11a48b-1b7c-41c8-8768-9d2f235f201d | Logs every ticket (auto-approved, rejected, vetoed, killed) and every close; runs post-mortems; **Monday performance report** (return vs. $10,000, win rate, average win/loss, max drawdown, fees and funding, vs. holding BTC). Never deletes losing trades. |

Group chat ID: b884d992-e7d1-4da2-be8f-4e09421336f6 ("Trading Floor"). Source: bot descriptions in `/workspace/trading-floor/low-usage-mode.json`.
