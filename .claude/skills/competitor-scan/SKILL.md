---
name: competitor-scan
description: Refresh competitor intelligence — current offers, pricing, messaging, and what changed since the last scan, with battle-card updates. Use when the user says "competitor scan", "what are competitors doing?", or names a competitor to tear down.
---

Run the competitor scan.

## Steps
1. Competitor list: from the request (single teardown) or
   `company/company-profile.md` (full scan). Read prior teardowns in
   `channels/marketing/data/competitors/` and `reports/` — the scan's job is
   *changes* as much as state.
2. Gather: live pages via web fetch/Firecrawl where available (save copies into
   `data/competitors/` with retrieval dates); otherwise work from saved material and
   label its age.
3. Run the `cmo-competitor-analyst` method per competitor (offer/pricing,
   positioning, channels, delta vs. us, changes since last scan).
4. Reply with: the changes-since-last-scan list first, biggest threat and biggest
   opening, updated battle-card lines, and the report path
   (`channels/marketing/reports/YYYY-MM-DD-competitor-scan.md`).

## Rules
- Public information only; observations dated; inference labeled as inference.
- If nothing material changed, say so in one line — a short honest scan beats padded
  analysis.
