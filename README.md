# clawin-agents

A public catalog of **install-ready OpenClaw agents** organized by industry and role.

## What this repository contains

This repository is for **published outputs only**.
It contains release-ready agent folder packages that can be copied into an OpenClaw installation and used directly after local configuration.

## What this repository does not contain

This repository does **not** include the private production pipeline used to generate these agents.
It does not contain:
- raw source role documents
- normalization scripts
- review queues
- internal run logs
- private production specs

## Repository layout

```text
categories/<industry-id>/agents/<role-family-key>/<agentId>/
```

Each agent package includes:
- `README.md`
- `INSTALL.md`
- `PACKAGE.json`
- `workspace/`
- `workspace/skills/`
- `config/`

## Install model

Install an agent by:
1. choosing an agent folder from `categories/...`
2. copying that folder into `~/.openclaw/agents/<agentId>/`
3. merging the provided config entry or snippet into your OpenClaw config
4. filling local provider secrets and routing choices
5. reloading OpenClaw
6. starting a chat with that agent

See:
- `INSTALL.md`
- `docs/shareable-folder-package.md`
- `CATALOG.md`

## Current public slice

Current published slice:
- `industry-1-software-it`
- role families:
  - `engineering`
  - `platform-engineering`

## Publishing model

This repository should grow by publishing curated agent outputs from the private Clawin production repo.
Changes here should stay focused on:
- install-ready agent packages
- public-facing docs
- public catalog organization

## Notes

- Secrets are intentionally excluded.
- Users must provide their own local provider configuration.
- This repository is designed for direct OpenClaw use, not as a standalone application.
