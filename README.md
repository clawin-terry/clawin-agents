# clawin-agents

**Install-ready OpenClaw agents, organized by industry and role.**

This repository is the **public output catalog** for Clawin.
It publishes curated agent packages that can be copied into an OpenClaw installation and used directly after local configuration.

## What this repo is for

Use this repository if you want to:
- browse ready-to-install OpenClaw agents by role
- pick a specialist agent instead of starting from a blank workspace
- copy one package into your own OpenClaw setup and start using it quickly

## What this repo is not

This repository does **not** include the private production pipeline.
It does not contain:
- raw role-source documents
- normalization or generation scripts
- internal review queues
- private run logs or private specs
- production environment details

## Current public release

Current published slice:
- **1 industry**: `industry-1-software-it`
- **2 role families**:
  - `engineering` (**19** agents)
  - `platform-engineering` (**8** agents)
- **27 total install-ready agent packages**

## Good starting points

If you want a quick place to start, these are strong entry points:

- **Frontend Engineer (JS/TS)**
  - Path: `categories/industry-1-software-it/agents/engineering/i1-frontend-engineer-js-ts/`
  - Good for: web UI implementation, component work, frontend delivery

- **Backend Engineer (Java)**
  - Path: `categories/industry-1-software-it/agents/engineering/i1-backend-engineer-java/`
  - Good for: backend services, APIs, Java-centric delivery

- **Kubernetes Platform Engineer (Go)**
  - Path: `categories/industry-1-software-it/agents/platform-engineering/i1-kubernetes-platform-engineer-go/`
  - Good for: platform operations, Kubernetes-heavy engineering environments

See the full catalog in:
- `CATALOG.md`

## Install in a few minutes

1. Pick one agent folder under `categories/<industry>/agents/<family>/<agentId>/`
2. Copy that folder into:
   - `~/.openclaw/agents/<agentId>/`
3. Merge the included config entry or config snippet into your OpenClaw config
4. Fill your local provider secrets and environment-specific settings
5. Reload OpenClaw
6. Start chatting with the installed agent

Detailed instructions:
- `INSTALL.md`

## Package contract

Each published package is expected to be a directly shareable agent folder.
A package includes:
- `README.md`
- `INSTALL.md`
- `PACKAGE.json`
- `workspace/`
- `workspace/skills/`
- `config/`

Formal contract:
- `docs/shareable-folder-package.md`

## Repository layout

```text
categories/<industry-id>/agents/<role-family-key>/<agentId>/
```

This repository intentionally stays simple:
- `categories/` — public install-ready agent packages
- `docs/` — public packaging contract
- top-level docs — install and catalog navigation

## Publishing model

Clawin uses a **private-source / public-output** split:
- private repo: production pipeline, specs, review artifacts, generation workflow
- this public repo: curated, install-ready agent packages only

That keeps the public catalog clean while allowing the private production system to continue evolving.

## Notes

- Secrets are intentionally excluded.
- Users must provide their own local provider configuration.
- These packages are designed for direct OpenClaw use, not as standalone apps.
- Future releases should continue expanding this catalog with curated agent outputs from the private source repository.
