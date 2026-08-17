# Live Data Connectors (MCP)

The agents work file-first: exports dropped into `channels/*/data/`. Connectors
(MCP servers / claude.ai connectors) upgrade specific agents from stale exports to
live pulls. The repo convention (root `CLAUDE.md`): **agents prefer live connector
data when available, and save what they pull into the channel's `data/` folder** so
every report stays reproducible after the session ends.

Connectors are optional per company — everything works without them, just with
more manual exporting.

## What helps which channel

| Connector | Channel(s) | What it unlocks |
|---|---|---|
| **Ahrefs** | Marketing | Live SEO data for `cmo-seo-content-strategist` and competitor traffic for `cmo-competitor-analyst` (already referenced by those agents) |
| **Web fetch / Firecrawl** | Marketing, Ecom, Technology | Live competitor pages, storefront audits, website health checks |
| **QuickBooks / Xero** | Finance | Live P&L/balance/AR instead of monthly exports for the analyst/AR-AP/tax agents |
| **Google Analytics (GA4)** | Marketing | Live funnel and traffic data for `cmo-funnel-analyst` |
| **Google Ads / Meta** | Marketing | Live campaign pulls for `cmo-ad-analyst` between exports |
| **CRM (HubSpot, Pipedrive…)** | Sales | Live pipeline for `sales-pipeline-analyst` and hygiene checks without CSV round-trips |
| **Shopify / Amazon** | Ecom | Live orders/inventory for the inventory and SKU-profitability agents |
| **Helpdesk (Zendesk, Intercom…)** | CX | Live ticket data for `cx-support-auditor` |
| **Slack** | CEO/all | Pull decisions/updates from team conversations into briefs (see `docs/slack.md`) |
| **Google Drive / email** | All | Fetch source documents without manual download-upload hops |

## How to connect

Where a connector is added depends on how you run Claude Code:

- **claude.ai (web/desktop) connectors**: claude.ai → Settings → Connectors →
  enable/authorize (e.g., Google Drive, and any MCP connectors your plan offers).
  These follow your account into Claude Code on the web sessions.
- **MCP servers in Claude Code**: in a session, `/mcp` shows what's connected;
  `claude mcp add <name> …` (CLI) or a `.mcp.json` at this repo's root configures
  project-scoped servers that load for anyone opening the repo. Example
  `.mcp.json` for a remote MCP server:

  ```json
  {
    "mcpServers": {
      "example-connector": {
        "type": "http",
        "url": "https://mcp.example.com/mcp"
      }
    }
  }
  ```

  Commit a `.mcp.json` only for servers every user of the repo should load;
  authentication happens per-user at first use (OAuth) — **never commit API keys
  or tokens to the repo**.

- **Scheduled runs**: sessions started by Routines or GitHub Actions may not carry
  interactively-authorized connectors — the file-first design is the fallback that
  keeps scheduled routines working regardless.

## Agent etiquette with connectors (already in agent definitions)

1. Check what's connected before assuming (a session without the connector falls
   back to `data/` files — and says which export it wants).
2. Save meaningful pulls into the channel's `data/` folder with a dated filename.
3. Cite the source and retrieval date for every number, live or file.
