# Automation — Scheduling the Routines

The cadence lives in `company/routines.md`; the `/run-routines` skill checks what's
due and runs it. That design is **scheduler-agnostic**: anything that starts a
session and says `/run-routines` keeps the whole rhythm going — you never encode the
schedule in the scheduler, only "check in".

Pick one of these triggers per company repo (Option 1 recommended):

## Option 1 — Claude Code Routines (recommended)

Claude Code on the web has a built-in scheduler called **Routines** (research
preview): [claude.ai/code/routines](https://claude.ai/code/routines), or type
`/schedule` in a session on the repo.

Set up one recurring Routine per company repo:

- **Schedule**: weekdays or weekly (e.g., Monday 8:00) — `/run-routines` figures
  out what's actually due, so a single daily/weekly trigger covers the whole
  cadence table. Minimum interval is 1 hour; schedules use your local time.
- **Prompt**: `/run-routines`
- **Repo/environment**: this company's repo.

Runs execute in Anthropic's cloud whether or not your machine is on. Docs:
<https://code.claude.com/docs/en/routines.md>. Note the daily run cap on Routines —
one daily or weekly trigger per company is plenty.

A second, useful one-off pattern: before a board meeting, schedule a one-time
Routine with the prompt `/board-pack` for the morning you need it.

## Option 2 — GitHub Actions

Runs on GitHub's schedule with no Claude session involved. Copy
`docs/automation/routines-github-action.yml` to `.github/workflows/routines.yml`
in the company repo, then add ONE auth secret in the repo settings
(Settings → Secrets and variables → Actions):

- `ANTHROPIC_API_KEY` — an API key from console.anthropic.com, **or**
- `CLAUDE_CODE_OAUTH_TOKEN` — a subscription token from running
  `claude setup-token` locally (then adjust the workflow to pass
  `claude_code_oauth_token` instead of `anthropic_api_key`).

The workflow uses `anthropics/claude-code-action@v1` with `prompt: "/run-routines"`
and lets the run commit its reports back. Docs:
<https://code.claude.com/docs/en/github-actions.md>. Quick path: running
`/install-github-app` inside a Claude Code session on the repo installs the GitHub
app, creates the secret, and opens the workflow PR for you.

## Option 3 — Manual / in-session

No setup at all: open the company repo in Claude Code whenever and type
`/run-routines` — it catches up on everything owed since last time (the run log in
`company/routines.md` keeps score). In a long-lived session, `/loop /run-routines`
re-checks on an interval while the session stays open.

## Which to choose

| Situation | Use |
|---|---|
| Normal case, you use claude.ai/code | **Routines** (Option 1) |
| Want scheduling fully inside GitHub / CI conventions | GitHub Actions (Option 2) |
| Trying the system out, or low cadence | Manual (Option 3) |

Whichever trigger you use, unattended runs push their reports to the repo (the
skill handles this) — check `channels/*/reports/` or the commit history to read
what your leadership team did while you slept.
