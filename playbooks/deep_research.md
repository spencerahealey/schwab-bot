# Playbook: Deep Research

Triggered by: "deep research [ANYTHING]", "research everything about [X]", or any request for comprehensive, multi-source analysis.

Deep research applies to **any topic** — a single ticker, an entire portfolio, a strategy question ("build me a low-risk portfolio"), a macro theme ("how do tariffs affect semis"), or anything else that benefits from structured, parallel investigation.

## How It Works

This playbook uses **parallel sub-agents** to maximize research breadth and speed. Each agent runs independently, searches the web, reads primary sources, and returns structured findings. The number and focus of agents adapts to the question.

## Agent Design Principles

1. **Decompose the question.** Break the research request into 3 independent angles that, combined, give a comprehensive answer.
2. **Launch all agents in parallel.** Each agent gets a clear, specific research mandate.
3. **Each agent searches exhaustively.** Multiple search queries, read full pages, follow links, find primary sources.
4. **Synthesize across agents.** Resolve contradictions, identify consensus, surface disagreements.
5. **Deliver actionable output.** Every research report ends with concrete next steps or recommendations.

## Research Modes

### Single Ticker
3 agents: Financials, Competitive/Strategic, Catalysts/Risks.

Output: Bull case, bear case, thesis verdict, key dates.

### Portfolio-Wide (Monthly Review)
One agent per holding (all parallel) + one macro agent.

Output: Per-holding verdicts, concentration analysis, action items.

### Strategy Construction
_e.g., "build me a low-risk portfolio", "what's a good income strategy", "design a barbell portfolio"_

3 agents:
1. **Framework Agent** — Research the strategy concept: what defines it, historical performance, who it's suited for, common implementations
2. **Candidates Agent** — Find specific tickers/ETFs that fit the strategy: screen for candidates, compare expense ratios/yields/risk metrics, identify best-in-class options
3. **Risk & Context Agent** — What can go wrong: historical drawdowns, correlation to existing holdings, current market conditions, tax implications

Output: Recommended portfolio with specific allocations, reasoning for each pick, risks to monitor, how it fits alongside existing holdings.

### Sector / Theme Analysis
_e.g., "AI infrastructure supply chain", "nuclear energy renaissance", "defense stocks"_

3 agents:
1. **Landscape Agent** — Key players, market size, growth drivers, competitive dynamics
2. **Holdings Impact Agent** — How does this affect the user's current positions? Which holdings benefit/lose?
3. **Opportunity Agent** — Investable ideas the user is missing, with entry theses

Output: Sector map, impact on current portfolio, ranked opportunities.

### Macro / Event Analysis
_e.g., "what happens if Fed cuts rates", "tariff impact", "recession playbook"_

3 agents:
1. **Scenario Agent** — What's happening, historical precedents, probability-weighted outcomes
2. **Portfolio Stress Test Agent** — How would each holding perform under this scenario? Which are most exposed?
3. **Positioning Agent** — What moves (if any) should be made? What hedges exist?

Output: Scenario analysis, portfolio exposure assessment, recommended actions.

### Open-Ended Research
_Anything that doesn't fit the above categories._

Decompose into 3 research angles based on the specific question. Always include:
1. An agent focused on **facts and data**
2. An agent focused on **implications for the user's portfolio**
3. An agent focused on **actionable recommendations**

## Rules
- Every finding must include a date or timeframe — undated claims are flagged
- Fact vs opinion: label analyst targets as opinions, revenue/earnings as facts
- If an agent can't find reliable data on something, it says so — no guessing
- Always connect findings back to the user's portfolio and situation
- Save all substantial research to `strategy/research_notes/{date}_{topic}.md`
- End every report with clear, specific next steps

## Change Log

| Date | Change | Reason |
|------|--------|--------|
| 2026-03-12 | Initial creation | Built parallel agent research workflow |
| 2026-03-12 | Expanded to cover any research topic | Deep research should handle strategies, macro, sectors — not just tickers |
