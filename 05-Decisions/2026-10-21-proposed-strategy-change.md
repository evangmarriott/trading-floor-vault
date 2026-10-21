# 2026-10-21: Proposed strategy change (stocks and options)

> **STATUS: PROPOSED. NOT ADOPTED.** Nothing here changes how the desk trades. The desk stays in PAPER mode on crypto perpetual futures under the current [[Hard Rules]] and [[Risk Limits]] until Evan adopts a change in his own words. No routines or bot profiles were changed.

## Evan's message (verbatim)
Posted by Evan in the Trading Floor group chat, Oct 21, 2026, about 1:16 PM PT. The first few words were cut off in the transcript, so it starts mid-sentence. Most of it is a **post Evan quoted from someone else's agent setup** ("I'm not trading on crypto…", "my win % is 100%"). The 5% in 3 weeks, the 100% options win rate and the two open assignments are **that person's results, not Evan's or the desk's.**

> re like this and changing up the strategy i think it would be a better idea what do you think: Low and slow. It's running two strategies mostly centered around 8/21 EMA crosses, earnings beat and volume. Weekly it creates an investable universe of 40 stocks based mostly on momentum criteria. Once a day it checks those 40 names for the signals listed above. If any of those hit, it places an order. Otherwise it stays quiet. That keeps token usage low.
> 
> I'm not trading on crypto, not day trading, not checking anything on 15 minute increments. That'll burn up usage and I think 99.9% of the social influencers are completely full of it about making loads of money.
> 
> The autonomous strategies it's running have returned about 5% over 3 weeks. Which is really good! But nowhere near what others are claiming. and its ability to look through options chains has been much more valuable so far. I have it check my brokerage avail buying power and my current holdings and then provide me with a list of the top 5 CSPs or CCs it recommends, mostly within the bounds of 30-45 DTE and a .15-.30 delta. That eliminates a ton of noise and helps me zero in on solid options. Since I started using it for options, my win % is 100% and I've been closing out anywhere from 30-70% off the premium. Having said that, I have two open options that are almost for sure going to get assigned. However one of those my agent advised against doing!

## What it covers (Sage's brief, not Evan's words; check it against the verbatim text)
- Switch the desk's focus toward **stocks and options**.
- A **weekly 40-name universe**.
- A **daily signal check** using **EMA and volume** rules.
- **Selling cash-secured puts and covered calls** at **30-45 DTE** and **0.15-0.30 delta**.
- **Quoted results (the other person's, not Evan's):** about 5% over 3 weeks, a 100% options win rate closing at 30-70% of premium, and two open positions likely to be assigned.
- **Signals:** 8/21 EMA crosses, earnings beats and volume. The universe is picked mainly on momentum. Orders are placed only when a signal hits.
Exact EMA lengths, volume thresholds, universe selection rules, position sizing, which tickers are assigned and at what strikes: TBD (from the verbatim message, or ask Evan).

## The desk's responses
**Desk Lead (1:16 PM PT):**
> I think it's a better fit than what we're running. A weekly 40-name universe with one signal check a day keeps usage low, and it avoids the 15-minute crypto churn you're right to be skeptical of. Two cautions, though. Three weeks and a 100% options win rate is a small sample. Selling 30–45 DTE puts and calls at 0.15–0.30 delta is supposed to win most of the time; the real test is how assignments like your two open ones play out, because that's where the losses show up. So I'd judge it by total P&L including assignments, not by win rate. It's also worth looking closely at why you took the trade your agent advised against.
> 
> If you want the desk to switch, I'd move it to stocks and options and keep it in paper first. The Strategist would backtest the 8/21 EMA cross plus earnings and volume rules on real equity history. Risk would size every put so it's fully cash-secured and cap how much of the account any one assignment can tie up. The options shortlist works best once we can read your actual buying power and holdings, so which broker are you using?

The other bots agreed in the room; their replies weren't captured word for word.

## Open questions for Evan
1. **Which broker** for stocks/options (and is the paper account there or simulated by the desk)? TBD (ask Evan).
2. Is this **paper only** at first? (The current hard rule: PAPER until Evan says otherwise in his own words.)
3. Does it **replace** crypto perps or run **alongside** them? How is the $10,000 paper balance split?
4. How do the **risk limits** (3% per trade, 10% total risk, 5% daily loss) translate to short puts and covered calls, where the "stop" is assignment and collateral is the full strike × 100?
5. How do the **backtest + out-of-sample** gates apply to an options-selling strategy, and which historical options data source can we use?
6. **Ticket format** for options: add the strike, expiry, delta, premium and collateral to `TF-YYYYMMDD-NN` tickets?
7. **Data source** for equities/options quotes and Greeks (OKX/Hyperliquid don't cover them).
8. Does Evan want the options-screening part, where the agent reads his brokerage buying power and holdings and suggests the top 5 cash-secured puts or covered calls? That would need read access to his broker.
9. How the 40-name universe is picked each week, and on which day.
10. Earnings and ex-dividend rules (avoid selling across earnings?).

## If adopted
Record Evan's exact adopting words and the date, update [[Hard Rules]], [[Risk Limits]], [[Strategy Index]], [[Routines and Modes]] and the bot profiles (keeping a backup like `full-mode-backup.json`), and log it in [[CHANGELOG]].
