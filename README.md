# SeeGeo for Cursor — AI visibility audit

Audit any website for AI visibility from inside Cursor: can ChatGPT, Claude,
Gemini and Perplexity read, understand and cite it? One tool call returns an
A–F grade, six category scores and the fixes ranked by impact. A second tool
answers the narrower question in seconds: which AI crawlers can read this
domain, and which are blocked.

**No account needed.** This plugin connects to the public endpoint
`https://see-geo.com/mcp/anonymous`: crawler checks any time, one full audit
per network per day, a public report link in every result.

## What you get

- `mcp.json` — the SeeGeo MCP server (remote, Streamable HTTP, no key).
- `skills/seegeo-audit` — how the agent should run an audit, read the
  findings and act on them in your codebase.

## Tools

| Tool | What it does |
| --- | --- |
| `crawler_check` | robots.txt and a live fetch as GPTBot, OAI-SearchBot, ClaudeBot and PerplexityBot; reports allowed / partial / blocked and bot walls |
| `audit_site` | the full graded audit: crawler access for 16 AI bots, technical basics, structured data, content extractability, off-site presence, entity clarity |
| `get_audit` | re-read an audit by id, optionally with the full report |

With a free SeeGeo account the same tools plus `list_audits` and `usage` are
served at `https://see-geo.com/mcp` over OAuth 2.1 or an API key, with the
plan's monthly allowance. Swap the URL in `mcp.json` and sign in when Cursor
asks.

## Try it

Ask the agent:

- "Audit example.com for AI visibility and give me the top three fixes."
- "Can ChatGPT read my site? Check mysite.com."
- "Grade our client's homepage and draft the robots.txt change it needs."

## About

Grades are calibrated against 107 real small-business websites; the
methodology, dataset (CC BY 4.0) and engine changelog are published at
https://see-geo.com. Docs for the API, the npm package (`seegeo-mcp`) and the
OAuth server: https://see-geo.com/developers. Privacy: https://see-geo.com/privacy.

MIT — SeeGeo, Navoy Technologies Inc.
