---
name: scrape-batch
description: Scrape up to 10 URLs at once using anakin-cli and return combined results in a single output file.
---

# Batch scrape multiple URLs

## Trigger

Scraping multiple web pages at once — comparing products, collecting articles, or gathering data from several sources.

## Workflow

1. Verify anakin-cli is authenticated by running `anakin status`.
2. Run the batch scrape: `anakin scrape-batch "<url1>" "<url2>" "<url3>" -o batch-results.json`.
3. If the user provides more than 10 URLs, split into batches of 10:
   - `anakin scrape-batch "<url1>" ... "<url10>" -o batch-1.json`
   - `anakin scrape-batch "<url11>" ... "<url20>" -o batch-2.json`
4. Read the output and present a summary of all scraped pages.

## Commands

```bash
# Batch scrape multiple URLs
anakin scrape-batch "<url1>" "<url2>" "<url3>" -o batch-results.json

# Split large lists into batches of 10
anakin scrape-batch "<url1>" ... "<url10>" -o batch-1.json
anakin scrape-batch "<url11>" ... "<url20>" -o batch-2.json
```

## Guardrails

- Maximum 10 URLs per `scrape-batch` command — split larger lists into batches.
- Always quote every URL to prevent shell interpretation.
- If individual URLs fail within a batch, report which ones failed and suggest retrying with `anakin scrape` using `--browser`.

## Output

- Combined results from all URLs in a single JSON file
- Summary listing each URL with its scrape status
