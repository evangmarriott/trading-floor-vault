# 2026-10-21 Decisions (Evan)

Source: the bot descriptions and README in `/workspace/trading-floor/`.

- **PAPER AUTO-APPROVE:** while in paper mode, Evan doesn't approve or monitor each trade. Tickets that pass the Strategist's checks and the Risk Manager's sizing execute automatically, marked "AUTO-APPROVED (paper)". He can still reject by ticket ID or pause it. Live mode would end auto-approve.
- **"10% total exposure" = total risk** across open trades (combined loss if every stop hits, incl. fees and slippage), not notional size or margin.
- **Don't wake Evan overnight** in paper auto-approve mode except for something that truly can't wait.
- **LOW-USAGE MODE** on for all six bots until Evan says to go back to full mode. Full-mode descriptions backed up at ~10:10 AM PT in `full-mode-backup.json`.
- **Proposed (not adopted):** a shift toward stocks and options. See [[2026-10-21-proposed-strategy-change]].
