# Risk Limits (Risk Manager enforces)

- **Max risk per trade:** 3% of account (at $10,000 = $300).
- **Max total exposure:** 10%. Per Evan's ruling (Oct 21, 2026), this means total **risk** across all open trades: the combined loss if every open position hit its stop, **including fees and slippage**, must not exceed 10% of the current paper balance (at $10,000 = $1,000). It is **not** a cap on notional size or margin.
- **Daily loss limit:** 5% (at $10,000 = $500). If hit, the desk goes flat and opens nothing more that day.
- Risk math includes 0.05% fees + 0.05% slippage per side.
- The Risk Manager can veto the Strategist and the Desk Lead, and states the reason.
- How these limits would apply to options (assignment risk, cash-secured collateral) if the [[2026-10-21-proposed-strategy-change]] is adopted: TBD (ask Evan).
Source: Risk Manager description, `/workspace/trading-floor/low-usage-mode.json`.
