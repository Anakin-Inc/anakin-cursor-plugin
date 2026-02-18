# Anakin plugin

Convert websites into clean data at scale: scrape, batch-scrape, search, and deep research.

## Requirements

This plugin requires [anakin-cli](https://pypi.org/project/anakin-cli/) (Python 3.10+):

```bash
pip install anakin-cli
anakin login --api-key "ak-your-key-here"
```

Get your API key from [anakin.io/dashboard](https://anakin.io/dashboard).

## Installation

```bash
/add-plugin anakin
```

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

## License

MIT
