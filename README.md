# Portfolio Management Agent for Claude Code

A self-annealing investment research and advisory agent that runs in [Claude Code](https://claude.ai/code). It tracks your portfolio, researches markets, and provides thesis-driven recommendations — all through natural conversation.

**Advisory only — this agent never executes trades.**

## What It Does

- **Parses brokerage CSVs** — upload an export from your broker and the agent saves, parses, and tracks your positions over time
- **Thesis-driven portfolio management** — every holding requires a written thesis; the agent holds you accountable to your own convictions
- **Research on demand** — ask about any ticker and get a structured analysis with a buy/watchlist/pass verdict
- **Monthly reviews** — comprehensive portfolio checkups covering every holding, macro context, and action items
- **Capital deployment** — "I have $X to invest" triggers a structured recommendation workflow
- **Sell discipline** — evaluates exit decisions against your thesis, not your emotions
- **Self-improving** — the agent updates its own playbooks, strategy docs, and theses as your investing evolves

## Prerequisites

- [Claude Code](https://claude.ai/code) (CLI or VS Code extension)
- A brokerage account with CSV export capability

## Quick Start

1. **Clone this repo** into a directory where you'll run Claude Code:
   ```bash
   git clone https://github.com/spencerahealey/schwab-bot.git
   cd schwab-bot
   ```

2. **Customize `CLAUDE.md`** — fill in the `About You` section with your age, income, risk tolerance, time horizon, and professional edge. This is how the agent calibrates advice to your situation.

3. **Customize `strategy/investment_strategy.md`** — adjust the account structure, standing rules, and constraints to match your setup.

4. **Add your holdings** to `strategy/position_theses.md` — write a thesis for every position you own.

5. **Start Claude Code** in this directory and start talking to your agent:
   - "Here's my latest portfolio CSV" (drag & drop or paste)
   - "Run my monthly review"
   - "What do you think about NVDA?"
   - "I have $2,000 to invest, where should it go?"
   - "Should I sell GOOGL?"

## How It Works

The agent is built entirely on Claude Code's `CLAUDE.md` convention — no code, no dependencies, no API keys. The `CLAUDE.md` file defines the agent's identity, protocols, and file structure. Strategy docs, playbooks, and portfolio state are plain files that the agent reads and updates as you interact with it.

### Key Design Principles

- **Thesis-first**: No position without a thesis. If the thesis breaks, you sell — even if you're down. If it strengthens, you add — even at all-time highs.
- **Self-annealing**: Every file is a living document. The agent updates strategy, theses, and playbooks after each interaction so the next session starts with full context.
- **Tax-aware**: The agent considers account type (taxable vs tax-advantaged) in every recommendation.
- **No sacred cows**: Every position gets scrutinized regardless of past performance.

### File Structure

```
CLAUDE.md                    # Agent identity, protocols, boundaries
strategy/
  investment_strategy.md     # Philosophy, account structure, rules
  position_theses.md         # Per-holding theses, watchlist, closed positions
  research_notes/            # Saved research deep-dives
data/
  snapshots/                 # Raw CSV exports from your broker
  state/
    portfolio_state.json     # Current holdings, history, review dates
playbooks/
  monthly_review.md          # Full portfolio review workflow
  new_money.md               # Capital deployment framework
  ticker_analysis.md         # Ticker research workflow
  sell_decision.md           # Exit decision framework
```

## CSV Support

Out of the box, the agent is configured for **Charles Schwab** CSV exports. If you use a different broker, update the CSV Handling section in `CLAUDE.md` with your broker's format (header rows, column names, special row labels).

## Customization Ideas

- Add new playbooks for workflows you repeat (e.g., earnings season prep, tax-loss harvesting)
- Extend the research protocol to use financial data APIs
- Add sector-specific analysis templates
- Create a rebalancing playbook if you prefer target allocations over pure thesis-driven sizing

## Disclaimer

This is a personal productivity tool, not financial advice software. The agent provides research and analysis to support your own investment decisions. Always do your own due diligence. Past performance doesn't guarantee future results. Consider consulting a qualified financial advisor for personalized advice.
