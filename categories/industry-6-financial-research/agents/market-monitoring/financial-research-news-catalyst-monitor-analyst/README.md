# News Catalyst Monitor Analyst

A shareable OpenClaw agent folder package for **News Catalyst Monitor Analyst**.

## Package identity
- Agent ID: `financial-research-news-catalyst-monitor-analyst`
- Industry: `industry-6-financial-research`
- Role family: `market-monitoring`
- Package version: `0.1.0`
- Recommended model: `openai-codex/gpt-5.4`

## Included
- `workspace/` — agent workspace files and persona docs
- `workspace/skills/` — bundled agent-specific skills
- `config/` — install-ready config entry + snippet + secrets checklist
- `INSTALL.md` — target machine installation steps
- `PACKAGE.json` — package metadata for GitHub/library use

## Bundled skills
- coding-agent

## Install
See `INSTALL.md`.

## Important note
This repository path is a library/catalog location.
After copying this package to a target machine, the intended install path is:

```text
~/.openclaw/agents/financial-research-news-catalyst-monitor-analyst
```
## Boundary guidance
- This package supports research preparation and evidence organization, not investment advice, trading instructions, suitability analysis, or fiduciary decisions.
- Require explicit uncertainty, assumptions, source freshness, and missing-data notes in outputs that could influence capital allocation or security-selection decisions.
- Escalate to a qualified human reviewer for final recommendations, client-facing advice, legal/compliance interpretation, or decisions requiring licensed judgment.