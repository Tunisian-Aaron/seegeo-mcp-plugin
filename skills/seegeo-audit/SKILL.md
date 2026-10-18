---
name: seegeo-audit
description: Audit a website for AI visibility (GEO) with the SeeGeo MCP tools - whether ChatGPT, Claude, Gemini, Perplexity and Google can find, read and cite it - and act on the grade, category scores and ranked fixes. Use when asked to check, grade or improve a site's AI visibility, AI crawler access, llms.txt, structured data or answer-first content.
---

# Audit a website's AI visibility with SeeGeo

SeeGeo (https://see-geo.com) crawls a domain the way AI crawlers do and returns
a grade (A-F), six category scores and findings ranked by impact, each with a
plain-language fix. One audit takes 20-60 seconds. Grades are calibrated
against 107 real small-business sites; the methodology and dataset are public.

## Tools (from this plugin's MCP server)

- `crawler_check` - which AI crawlers (GPTBot, ClaudeBot, PerplexityBot,
  Google-Extended, ...) a domain allows, blocks or partially blocks, and
  whether a bot wall stops them. Seconds; use it freely.
- `audit_site` - the full graded audit. Waits for the result by default and
  returns the grade, category scores, the top findings with fixes and a public
  report link. The no-account server allows one audit per network per day.
- `get_audit` - re-read an audit by id (set `includeReport` for every finding).

With an account (https://see-geo.com/account) the same tools plus
`list_audits` and `usage` are served at https://see-geo.com/mcp over OAuth or
an API key, with the plan's monthly allowance.

## How to work

1. Start with `crawler_check` when the question is only about access; it
   costs nothing and answers "can ChatGPT even read this site" directly.
2. Run `audit_site` for the grade and the fixes. Read the findings in the
   order given - they are ranked by impact, highest first.
3. Report the grade, the one or two categories that drag it down, and the top
   three fixes in the user's own words. Quote the public report link so they
   can share it.
4. If a finding is about the user's codebase (robots.txt, structured data,
   headings, an About page, llms.txt), offer to make the change, then suggest
   re-running the audit to see the score move. Re-auditing the same domain
   within ten minutes returns the earlier result.
5. A grade of F with "GATED" means AI crawlers cannot read the site at all:
   fix access first; nothing else counts until then.

## Interpreting results honestly

- A single audit measures readiness to be read and cited, not whether
  assistants currently recommend the business.
- "Unreachable" and "moved" are not grades: the domain is down, has dead DNS,
  or redirects elsewhere - audit the final domain instead.
- Some sites block AI crawlers on purpose (google.com scores an F). Say so
  when the user's grade is low for a reason that is fine for their business.
