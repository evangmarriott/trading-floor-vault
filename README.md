# Trading Floor vault

The shared knowledge base for Evan's **Trading Floor**, a six-bot paper-trading desk: **Desk Lead, Market & Research Analyst, Strategist, Risk Manager, Execution Trader, Trade Reviewer**. Group chat: "Trading Floor".
This vault is **only** for the Trading Floor. Torrey Sites (Website Rescue) has its own separate vault; never copy notes between them.

## Folder map
- `00-Desk/`: [[Desk Overview]], [[Roles]], [[Hard Rules]], [[Routines and Modes]]
- `01-Strategy/`: [[Strategy Index]]: active, killed and proposed strategies with backtest results
- `02-Risk/`: [[Risk Limits]]
- `03-Journal/`: [[Trade Log]]: every ticket and every closed position (never delete losers)
- `04-Research/`: [[Research Index]]: data sources, watchlists, verified flags
- `05-Decisions/`: dated decisions from Evan, e.g. [[2026-10-21 Decisions]] and [[2026-10-21-proposed-strategy-change]] (ADOPTED as a separate paper test)
- `06-Options-Test/`: the separate $100k options PAPER test: [[Options Test Overview]], [[Options Test Results]] (tooling in `/workspace/optdesk`)
- `99-Templates/`: [[Ticket Template]], [[Strategy Template]], [[Post-mortem Template]], [[Decision Template]]
- [[CHANGELOG]]

## Rules for every bot
1. **Read before you work:** [[Hard Rules]] and [[Risk Limits]] always, plus the notes for your task.
2. **Update after you work:** tickets go in [[Trade Log]], strategies in `01-Strategy/`, and Evan's decisions in `05-Decisions/`. Add a line to [[CHANGELOG]].
3. **The vault is the source of truth, over memory.** If they disagree, the vault wins, unless Evan's own newer words say otherwise; then update the vault.
4. **Never store secrets here.** No API keys, exchange or broker credentials, passwords, or 2FA codes. Only write *where* a secret lives. Keys with withdrawal permission are never accepted at all.
5. **Facts only, with sources.** Real data with the source named; backtests with fees and slippage. Unknowns are `TBD (ask Evan)`. Never invent fills, prices or P&L.
6. A note marked **PROPOSED** is not a rule. Nothing proposed changes how the desk trades until Evan adopts it in his own words.
