---
name: run-routines
description: Check the routine cadence in company/routines.md and run whatever is due — the entry point for scheduled sessions (Claude Code Routines, GitHub Actions) and manual catch-ups. Use when the user says "run routines", "catch up", "what's due?", or when a scheduled session starts with this skill.
---

Run the company's recurring cadence.

## Steps
1. Read `company/routines.md`. For each **Active** routine, find the newest matching
   report (patterns below) and classify: current / due / overdue using the
   frequency rules in that file. Report-name patterns:
   - `/weekly-brief` → `channels/ceo/reports/*-weekly-brief.md`
   - `/monthly-close` → `channels/finance/reports/*-monthly-close-*.md`
   - `/inventory-review` → `channels/ecommerce/reports/*-inventory-review.md`
   - `/competitor-scan` → `channels/marketing/reports/*-competitor-*.md`
   - `/cost-cut` → `channels/finance/reports/*-cost-optimization.md`
   - `/hr-compliance-check` → `channels/hr/reports/*-compliance-audit.md`
   - `/it-security-check` → `channels/technology/reports/*-security-check.md`
   - `/marketing-audit` → `channels/marketing/reports/*-marketing-audit.md`
   - `/board-pack` → `channels/ceo/reports/*-board-pack.md`
   - `/ecom-audit` → `channels/ecommerce/reports/*-ecom-audit.md`
   - agent rows → that agent's standard report path per its definition
2. **Data pre-check** per due routine: if its required data folder is empty or
   stale (e.g., `/monthly-close` with no new statements), don't run it — record it
   as "blocked: needs <file> in <folder>" instead. Blocked items surface loudly in
   the summary; that's the human's homework.
3. **Run what's due**, highest priority first, oldest-overdue first within a
   priority. If more than 3 substantial routines are due at once (e.g., first run
   or after a long gap), run the top 3 and list the rest as "deferred — run
   /run-routines again" so no single session balloons.
4. **Log**: append one row to the Run log table in `company/routines.md` (date,
   what ran, what was skipped/blocked and why).
5. **Summarize** in the reply: what ran (with report paths and each one's headline
   finding), what's blocked on missing data (exact file + folder), what was
   deferred, and the next natural due dates.
6. If this session runs unattended (scheduled), also commit and push the new
   reports and the run-log update with message `routines: <date> <what ran>` —
   reports nobody can see didn't happen. In an interactive session, offer to
   commit instead.

## Rules
- Never fake currency: a routine that can't run for missing data is reported
  blocked, not silently skipped or run on stale inputs.
- Respect each skill's own rules; this skill orchestrates, it doesn't shortcut.
- If `company/routines.md` is missing or all rows inactive, say so and suggest
  enabling rows — don't invent a cadence.
