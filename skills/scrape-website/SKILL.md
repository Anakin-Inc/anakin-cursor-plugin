---
name: scrape-website
description: Scrape a single URL using anakin-cli and return clean markdown, structured JSON, or the full raw API response.
---

# Scrape a website

## Trigger

Extracting content from a single web page — an article, product page, documentation, or any URL.

## Workflow

1. Verify anakin-cli is authenticated by running `anakin status`.
2. Scrape the URL in the requested format:
   - Markdown (default): `anakin scrape "<url>" -o output.md`
   - Structured JSON: `anakin scrape "<url>" --format json -o output.json`
   - Full raw response: `anakin scrape "<url>" --format raw -o output.json`
3. For JavaScript-heavy or single-page app sites, add the `--browser` flag.
4. For geo-targeted content, add `--country <code>`.
5. If the scrape times out, increase with `--timeout <seconds>`.
6. Read the output file and present results to the user.

## Commands

```bash
# Clean readable text (default)
anakin scrape "<url>" -o output.md

# Structured data
anakin scrape "<url>" --format json -o output.json

# Full API response with HTML and metadata
anakin scrape "<url>" --format raw -o output.json

# JavaScript-heavy or single-page app sites
anakin scrape "<url>" --browser -o output.md

# Geo-targeted scraping
anakin scrape "<url>" --country gb -o output.md

# Custom timeout for slow pages
anakin scrape "<url>" --timeout 300 -o output.md
```

## Guardrails

- Always quote URLs to prevent shell interpretation of `?`, `&`, `#` characters.
- Default to markdown format unless the user asks for structured data or raw output.
- Use `--browser` only when a standard scrape returns empty or incomplete content.
- On 429 errors, wait before retrying rather than looping immediately.

## Output

- Scraped content in the requested format
- File path where results were saved
