# Slack Channel Mapping

The repo's `channels/` mirror how department Slack channels work — and with Claude
in Slack, they connect literally: a message in **#finance** becomes a session on
this repo working in `channels/finance/`.

## Setup (once per workspace)

1. Install the **Claude app** from the Slack App Marketplace
   (<https://slack.com/marketplace> → search "Claude") and connect your Claude
   account in the app's Home tab. On Team/Enterprise plans, admins set up the
   org-level **Claude Tag** app instead — see <https://claude.com/docs> for the
   current setup path for your plan.
2. Make sure Claude Code on the web (claude.ai/code) is connected to GitHub with
   access to the company repo(s).
3. Invite Claude to each department channel: `/invite @Claude` in #leadership,
   #finance, #marketing, #hr, etc.
4. In each department channel, pin a short instruction message (template below) so
   requests route to the right part of the repo. Claude reads the pinned context
   and channel conversation when it picks up a request; specify the repo in your
   first request if it isn't auto-detected.

## Pinned-message template (adjust per channel)

> @Claude requests in this channel are for **<Company>**'s <department> work.
> Repo: `<org>/<company-repo>` — work within `channels/<channel>/` per the repo's
> CLAUDE.md. Typical asks here: <e.g., "process the statements I just dropped",
> "/monthly-close", "how's cash looking?">.

## Per-company mapping

Each company repo carries its own mapping table at `company/slack-channel-map.md`
(template in this repo). Fill it during `/onboard-company` or whenever the Slack
workspace gets organized. Agents use it in reverse, too: a report that says "post
the summary to the team" cites the mapped channel.

## Ways to use it day-to-day

- **Drop → analyze**: upload a statement/export to the Slack channel and ask
  @Claude to file it in the right `data/` folder and run the matching skill.
- **Question → channel agent**: "@Claude how's our pipeline coverage?" in #sales
  runs the pipeline analyst and replies with the headline + report link.
- **Routines announcements**: end scheduled `/run-routines` prompts with "post a
  3-bullet summary to #leadership" once the Slack connector is available to the
  scheduled session (see the caveat in `docs/connectors.md` — scheduled runs may
  lack interactive connectors; the reports in the repo are always the source of
  truth).

## Cautions

- A Slack channel is an input surface, not a data store: files that matter get
  committed into `channels/*/data/` — Slack uploads expire from Claude's reach.
- Anyone in the Slack channel can ask Claude to act on the repo. Keep sensitive
  channels (#finance, #hr) membership-tight, mirroring the repo's privacy rules —
  comp data stays in HR/finance contexts.
- Claude in Slack runs under the account that connected it; its repo access is
  that account's access.
