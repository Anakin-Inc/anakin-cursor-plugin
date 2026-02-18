---
name: search-web
description: Run an AI-powered web search using anakin-cli and return relevant results instantly.
---

# Search the web

## Trigger

Finding pages, answering questions, discovering sources, or gathering links on a topic.

## Workflow

1. Verify anakin-cli is authenticated by running `anakin status`.
2. Run the search: `anakin search "<query>" -o search-results.json`.
3. Read the results and present them with titles, URLs, and relevant snippets.
4. If the user wants to dig deeper into a specific result, follow up with `anakin scrape "<result-url>" -o page.md`.

## Commands

```bash
# AI-powered web search
anakin search "<query>" -o search-results.json

# Scrape a specific result for full content
anakin scrape "<result-url>" -o page.md
```

## Guardrails

- Keep search queries concise and specific for better results.
- Present results as a clean summary, not a raw JSON dump.
- When the user's intent is broad research rather than a quick search, suggest `deep-research` instead.

## Output

- Search results with titles, URLs, and snippets
- Recommended follow-up actions
