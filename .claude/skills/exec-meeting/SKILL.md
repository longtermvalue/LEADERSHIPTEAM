---
name: exec-meeting
description: Prepare a leadership/management meeting — agenda, pre-read, talking points, and a decision list built from the latest channel reports. Use when the user says "prep the exec meeting", "leadership meeting agenda", or similar.
---

Prepare an executive meeting package.

## Steps
1. Ask (or infer from the request) the meeting's focus: routine monthly ops review,
   quarterly planning, or a special topic.
2. Gather: latest weekly brief / KPI scorecard, each channel's most recent report,
   open decisions from prior `*-exec-meeting.md` and `*-decision-*.md` files in
   `channels/ceo/reports/` (decisions made? actions done?).
3. Build the package:
   - **Agenda** with time boxes (60–90 min default): 5 min scorecard, 10 min last
     meeting's action review, then topic blocks ordered by decision-weight — items
     needing a DECISION before items that are FYI.
   - **Pre-read** (1 page): the scorecard + a 3-line status per channel.
   - **Per agenda item**: the question to resolve, 2–3 sentence context with the
     source report cited, options if it's a decision, and the recommendation.
   - **Decision log template** at the end: decision | owner | due — to fill during
     the meeting.
4. Save to `channels/ceo/reports/YYYY-MM-DD-exec-meeting.md`, show the agenda and
   decision list in the reply.

## Rules
- Anything unresolved from the last meeting leads the agenda — meetings that re-lose
  the same decisions are theater.
- Cap the agenda at what fits the time box; overflow goes to a "parking lot" section.
