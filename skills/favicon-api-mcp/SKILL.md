---
name: favicon-api-mcp
description: Use Favicon.so API and MCP tools to fetch website favicons, provide search and generator routes, and return integration-ready outputs for engineering workflows.
license: MIT
metadata:
  author: favicon.so
  version: 1.0.0
---

# Favicon API + MCP Skill

Use this skill when users ask for favicon lookup, favicon generation guidance, or brand icon collection at scale.

## Core capabilities

1. Fetch favicon data for domains with MCP tools when available.
2. Fall back to the REST API when MCP is unavailable.
3. Return stable, integration-ready output (tables, links, and code snippets).

## Preferred execution order

1. Normalize the domain input before requests.
2. Try MCP tools first:
   - `get_favicon`
   - `get_favicon_generator_url`
   - `search_favicons`
3. If MCP tools are unavailable, use API fallback:
   - `GET https://favicon.so/api/favicon?url=<domain>&raw=true`
4. If the user asks for an embeddable image URL, use:
   - `https://favicon.so/api/favicon?url=<domain>`

## Output contract

- Always include `domain`, `url`, `format`, and `isDefault` when available.
- If a favicon cannot be fetched, explain the failure reason and provide a fallback route:
  - Search page: `https://favicon.so/en/search?q=<query>`
  - Generator page: `https://favicon.so/en/generator`
- Keep the final output concise and directly actionable.

## Prompt patterns

- "Fetch favicons for these domains and return a markdown table."
- "Check favicon quality coverage for a list of partner domains."
- "Provide fallback generator links when a site has no valid favicon."
