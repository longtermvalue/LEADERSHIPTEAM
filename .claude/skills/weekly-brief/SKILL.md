---
name: weekly-brief
description: Produce the weekly leadership brief — a one-page cross-channel status with KPI movement, wins, concerns, and this week's decisions. Use when the user asks for the weekly brief, a status rollup, or "how's the business doing this week?"
---

Run the weekly leadership brief as `ceo-chief-of-staff` would (delegate to that
agent, or follow its method directly for speed).

## Steps
1. Read `company/company-profile.md` + `company/goals-and-okrs.md`.
2. Sweep every `channels/*/reports/` for anything new since the last brief (find the
   previous `*-weekly-brief.md` in `channels/ceo/reports/` — read it for continuity:
   carry forward open actions and check whether they happened).
3. Check for fresh un-analyzed data: files in any `data/` folder newer than that
   channel's latest report → list as "new data awaiting analysis" with the suggested
   agent/skill to run.
4. Compose the brief per the chief-of-staff output skeleton (headline, scorecard,
   wins/concerns/decisions, per-channel two-liners with freshness, actions with
   owners). One page.
5. Save to `channels/ceo/reports/YYYY-MM-DD-weekly-brief.md` and show it in full in
   the reply.

## Rules
- Open actions from last week that didn't happen get named, not dropped.
- No new analysis rabbit-holes during the brief — flag "needs a run" instead, keep
  the brief fast.
