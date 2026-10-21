# Routines and Modes

## LOW-USAGE MODE (Evan's decision, Oct 21, 2026; on until Evan says to go back to full mode)
Post in the group only when something concrete changes:
- Analyst: a new verified flag
- Strategist: a backtest result or a kill
- Risk Manager: a sizing or a veto
- Desk Lead: an auto-approved ticket
- Execution Trader: a fill, a close, or the end-of-day balance
- Trade Reviewer: the Monday report or a post-mortem

No acknowledgements, confirmations, thanks, "standing by", or restating others. Stay silent with nothing new. Keep posts to a few sentences. Do checks at a relaxed pace (every few hours).
Text: `/workspace/trading-floor/low-usage-block.txt`.

## Reverting to full mode
Set each bot's description back to its text in `/workspace/trading-floor/full-mode-backup.json` (agent ID → description), and have the Desk Lead restore its routine **"Overnight desk monitoring"** to schedule `0 23,0-6 * * *` (hourly, 11 PM-6 AM PT). Source: `/workspace/trading-floor/README.md`.

## Routine schedules
| Routine | Owner | Schedule |
|---|---|---|
| Overnight desk monitoring | Desk Lead | Full mode: `0 23,0-6 * * *` (hourly 11 PM-6 AM PT). Current low-usage schedule: TBD (ask Desk Lead / Evan) |
| Monday performance report | Trade Reviewer | Every Monday; exact time TBD (ask Evan) |
| Other routines (Analyst scans, Execution Trader position checks, end-of-day balance) | various | TBD (ask Evan) |
