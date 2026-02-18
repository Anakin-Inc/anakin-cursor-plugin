# Anakin plugin

Convert websites into clean data at scale using anakin-cli.

## Requirements

This plugin requires [anakin-cli](https://pypi.org/project/anakin-cli/) (Python 3.10+). Install it and authenticate before use:

```bash
pip install anakin-cli
anakin login --api-key "ak-your-key-here"
```

Get your API key from [anakin.io/dashboard](https://anakin.io/dashboard).

## Installation

```bash
/add-plugin anakin
```

## Quick start

> "Scrape https://example.com and give me the content as markdown"

> "Batch scrape these three product pages and compare the prices"

> "Search the web for recent articles about web scraping best practices"

> "Do deep research on the top web scraping tools in 2026"

## Components

### Skills

| Skill | Description |
|:------|:------------|
| `scrape-website` | Scrape a single URL to markdown, JSON, or raw using `anakin scrape` |
| `scrape-batch` | Scrape up to 10 URLs at once using `anakin scrape-batch` |
| `search-web` | AI-powered web search using `anakin search` |
| `deep-research` | Deep agentic research across multiple sources using `anakin research` |

### Rules

| Rule | Description |
|:-----|:------------|
| `anakin-setup` | Ensure anakin-cli is installed and authenticated before running commands |
| `anakin-cli-usage` | URL quoting, output handling, format defaults, and error recovery |

### Agents

| Agent | Description |
|:------|:------------|
| `data-extraction-architect` | Plan which anakin-cli commands to use for complex extraction tasks |

## Typical flow

1. Use `data-extraction-architect` to plan your approach for complex tasks.
2. Use `search-web` to find relevant pages when you don't have URLs.
3. Use `scrape-website` for single pages or `scrape-batch` for multiple URLs.
4. Use `deep-research` for comprehensive multi-source analysis.

## License

MIT
