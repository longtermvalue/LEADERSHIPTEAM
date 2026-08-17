---
name: marketing-audit
description: Run the full marketing review — ads, funnel economics, email, SEO/content, and brand consistency — into one prioritized findings report. Use when the user says "marketing audit", "review our marketing", or "why isn't marketing working?"
---

Run the full-funnel marketing audit.

## Steps
1. Inventory what data exists across `channels/marketing/data/*` (and note what's
   missing — the audit covers what it can and lists the gaps).
2. Run the applicable specialist methods (delegate to the agents in parallel where
   possible):
   - `cmo-ad-analyst` on ad exports (skip if no paid ads)
   - `cmo-funnel-analyst` for the economics spine — this one always runs
   - `cmo-email-analyst` on email data
   - `cmo-seo-content-strategist` baseline + quick wins
   - `cmo-brand-guardian` audit mode across available assets
3. Synthesize into ONE report,
   `channels/marketing/reports/YYYY-MM-DD-marketing-audit.md`: overall verdict →
   the funnel table with $-sized leaks → top 10 findings across all areas ranked by
   expected dollar impact (not by area) → 30-day fix plan → data gaps blocking
   better analysis.
4. Reply with the verdict, top 5 moves, and the report path.

## Rules
- The unifying question is CAC vs. margin — every area's findings tie back to it.
- Ten ranked findings beat forty scattered ones; push the long tail to appendices.
