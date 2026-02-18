---
name: deep-research
description: Run a deep agentic research task using anakin-cli that autonomously explores the web and returns a comprehensive report.
---

# Deep research

## Trigger

Comprehensive research on a topic — comparisons, market analysis, technical deep-dives, or questions requiring multiple sources.

## Workflow

1. Verify anakin-cli is authenticated by running `anakin status`.
2. Inform the user that deep research takes 1-5 minutes and runs autonomously.
3. Run the research task: `anakin research "<topic>" -o research-report.json`.
4. If the research times out, increase with `--timeout 600`.
5. Read the report and present a structured summary with key findings, sources, and insights.

## Commands

```bash
# Deep agentic research (1-5 minutes)
anakin research "<topic>" -o research-report.json

# With extended timeout for complex topics
anakin research "<topic>" --timeout 600 -o research-report.json
```

## Guardrails

- Always warn the user about the 1-5 minute duration before starting.
- Use `search-web` for quick factual lookups — reserve `deep-research` for multi-source exploration.
- Always save output to a file with `-o` to prevent terminal buffer overflow.
- If research fails, fall back to `search-web` plus multiple `scrape-website` calls as a manual alternative.

## Output

- Comprehensive research report with findings and sources
- File path where the full report was saved
