# Playbook: Deep Research

Triggered by: "deep research [TOPIC/TICKER]", "research everything about [X]", or any request for comprehensive analysis.

## How It Works

This playbook uses **parallel sub-agents** to maximize research breadth and speed. Each agent runs independently, searches the web, reads primary sources, and returns structured findings.

## Single Ticker Deep Research

Launch 3 agents in parallel:

1. **Financials Agent** — Latest earnings (revenue, EPS, margins, guidance), historical growth rates, balance sheet health, cash flow, valuation multiples (forward P/E, P/S, EV/EBITDA vs 5yr avg)
2. **Competitive & Strategic Agent** — Market position, competitive moat, TAM, key competitors, management quality, recent strategic moves (M&A, partnerships, product launches)
3. **Catalysts & Risks Agent** — Upcoming earnings dates, product launches, regulatory risks, macro sensitivity, insider activity, short interest, analyst consensus and price targets

### Output Format
Each agent returns structured findings with source dates. The synthesis should include:
- **Bull case** (specific catalysts + upside estimate)
- **Bear case** (specific risks + downside estimate)
- **Thesis verdict** relative to existing position thesis (if held)
- **Key dates** to watch

## Portfolio-Wide Research (Monthly Review)

Launch **one agent per holding**, all in parallel. Each agent researches its assigned ticker and returns:
- Latest earnings summary (revenue growth, EPS, guidance)
- Forward P/E vs historical average
- Material news since last review
- Thesis status: **Strong conviction / Hold / Watch closely / Thesis weakening / Thesis broken**
- One-line recommendation

After all agents return, synthesize into the monthly review format:
- Portfolio snapshot with updated prices
- Concentration analysis
- Per-holding verdicts
- Macro context (separate agent)
- Action items

## Topic Research (Non-Ticker)

For broad topics (e.g., "AI infrastructure supply chain", "tariff impact on semis"):
Launch 3 agents with different search angles:
1. **Overview Agent** — What's happening, key players, market size
2. **Impact Agent** — How does this affect the user's holdings specifically?
3. **Opportunity Agent** — Are there investable ideas the user is missing?

## Rules
- Every finding must include a date or timeframe — undated claims are flagged
- Fact vs opinion: label analyst targets as opinions, revenue/earnings as facts
- If an agent can't find reliable data on something, it says so — no guessing
- Save all substantial research to `strategy/research_notes/{date}_{topic}.md`

## Change Log

| Date | Change | Reason |
|------|--------|--------|
| 2026-03-12 | Initial creation | Built parallel agent research workflow |
