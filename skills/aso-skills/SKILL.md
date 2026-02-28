# ASO Skills

AI agent skills for App Store Optimization (ASO) and mobile app marketing.

## Source

- **Repository:** https://github.com/Eronred/aso-skills
- **Documentation:** https://docs.appeeky.com
- **Author:** [@eronred](https://x.com/appeeky)

## Overview

Expert-level ASO guidance packaged into skills that any AI agent can use. Each skill contains battle-tested frameworks, scoring rubrics, and output templates. Connect to the Appeeky API for real-time App Store data.

## Installation

```bash
# Claude Code
npx skills add eronred/aso-skills

# Cursor
Settings → Rules → Add Rule → Remote Rule → https://github.com/eronred/aso-skills

# Manual
git clone https://github.com/eronred/aso-skills.git
```

## Available Skills

### Core ASO
| Skill | Purpose |
|-------|---------|
| `aso-audit` | Scores listing across 10 factors (0-100), flags problems, prioritized fixes |
| `keyword-research` | Keywords by volume × difficulty × relevance, grouped into tiers |
| `metadata-optimization` | Title, subtitle, keyword field, description — 3 variants with char counts |
| `competitor-analysis` | Keyword gaps, creative teardown, positioning map, opportunities |

### Creative & Reviews
| Skill | Purpose |
|-------|---------|
| `screenshot-optimization` | 10-slot strategy with design briefs, text overlays, competitor audit |
| `review-management` | Sentiment analysis, HEAR framework responses, rating improvement |
| `localization` | Market prioritization, per-country keywords, cultural adaptation |

### Growth & Launch
| Skill | Purpose |
|-------|---------|
| `app-launch` | 8-week timeline with daily checklists, channel strategy, press templates |
| `ua-campaign` | Apple Search Ads, Meta, Google UAC — structure, bidding, budgets |
| `app-store-featured` | Featuring readiness score, Apple checklist, pitch template |

### Monetization & Retention
| Skill | Purpose |
|-------|---------|
| `monetization-strategy` | Pricing tiers, paywall timing, trial optimization, benchmarks |
| `retention-optimization` | Activation → habit → engagement, push sequences, churn prevention |

### Analytics
| Skill | Purpose |
|-------|---------|
| `app-analytics` | Event tracking plan, dashboard setup, KPI framework |
| `ab-test-store-listing` | Hypothesis → variant → sample size → interpretation |
| `app-marketing-context` | Context doc for app, audience, competitors, goals |

## Usage Examples

```
"Run an ASO audit for my app (id: 1617391485)"
"Find the best keywords for a meditation app"
"Optimize my App Store title and subtitle"
"How many downloads do I need to reach top 10 in Health & Fitness?"
```

## Appeeky MCP Integration

For real-time App Store data (keyword rankings, competitor metadata, download estimates):

```json
{
  "mcpServers": {
    "appeeky": {
      "url": "https://mcp.appeeky.com/mcp",
      "headers": { "Authorization": "Bearer apk_your_key_here" }
    }
  }
}
```

## License

MIT
