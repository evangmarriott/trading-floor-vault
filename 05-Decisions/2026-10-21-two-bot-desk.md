# Decision: two-bot desk (2026-10-21)

Status: ADOPTED (Evan, Oct 21 2026: "ok yea cut it down more")

The Trading Floor now runs with two bots:
- **Trader** (formerly Execution Trader): runs both paper accounts (crypto perps $10k, options test $100k). Does research, backtests, sizing within hard limits, tickets, fills, ledgers.
- **Reviewer** (formerly Trade Reviewer): independent auditor. Never trades. Daily rule audit after the close, logs, post-mortems, Monday report with separate sections per account.

Retired (kept, can be reactivated by Sage): Desk Lead, Market & Research Analyst, Strategist, Risk Manager.

Why: scripts in /workspace/optdesk now enforce limits and do the screening, so six bots mostly passed messages and cost usage. Keeping trading and checking in separate bots preserves the independent check.

All safety rules unchanged: PAPER only until Evan says otherwise, no withdrawal-permission keys, risk limits, never delete losing trades.
