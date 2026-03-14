# Design Director

A shareable OpenClaw agent folder package for **Design Director**.

## Package identity
- Agent ID: `software-it-design-director`
- Industry: `industry-1-software-it`
- Role family: `design`
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
- ui-ux-pro-max
- frontend-design

## Install
See `INSTALL.md`.

## Important note
This repository path is a library/catalog location.
After copying this package to a target machine, the intended install path is:

```text
~/.openclaw/agents/software-it-design-director
```