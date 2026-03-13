# Playbook: Monthly Portfolio Review

Triggered by: CSV upload + "run my review", "portfolio review", "how am I doing", or monthly cadence.

## Steps

1. **Parse CSVs.** Save snapshots. Update `portfolio_state.json`. Detect account types automatically.

2. **Portfolio snapshot.** Total value across accounts. Per-position value, gain/loss, % of total. Cash positions. If prior snapshot exists, show month-over-month delta.

3. **Concentration analysis.** Group holdings by sector/theme. Flag if any single theme exceeds 50% with a specific downside scenario and dollar amount. Identify correlation risk — which positions drop together in a selloff?

4. **Deep research on every holding — PARALLELIZED.** Launch one sub-agent per ticker (all in parallel). Each agent returns:
   - Latest earnings (revenue growth, EPS, guidance)
   - Valuation check (forward P/E vs historical)
   - Thesis check against `position_theses.md` — still valid?
   - Material news, upcoming catalysts
   - **Verdict:** Strong conviction / Hold / Watch closely / Thesis weakening / Thesis broken
   See `playbooks/deep_research.md` for agent protocol.

5. **Macro context** (separate parallel agent). S&P/NASDAQ valuation, VIX, Fed policy, inflation, sector rotation. **Connect macro to the user's specific holdings** — don't just report news.

6. **Action items.**
   - Positions to act on (with reasoning and tax implications for brokerage)
   - Where to deploy new money
   - What to watch next month (earnings dates, Fed meetings, catalysts)
   - What NOT to do (call out panic-selling temptations if thesis is intact)

7. **Update files.** Refresh `Last Reviewed` dates in `position_theses.md`. Save research to `research_notes/`. Update any theses that changed.

## Rules
- No sacred cows. Every position gets scrutinized.
- Thesis-first, always. Don't say "buy the dip" without confirming the thesis.
- Be specific about downside. Not "you could lose money" — "$X,XXX if [specific scenario]."
- Don't over-trade. If nothing changed, say so.
- If holding leveraged ETFs: always calculate volatility decay.

## Change Log

| Date | Change | Reason |
|------|--------|--------|
| 2026-03-12 | Initial creation | — |
| 2026-03-12 | Added parallel agent research | Research all holdings simultaneously via sub-agents |
