# clawin-agents

**Install-ready OpenClaw agents, organized by industry and role.**

This repository is the **public output catalog** for Clawin.
It publishes curated agent packages that can be installed into an OpenClaw environment through the public Clawin CLI flow and then used after local configuration.

## Quick links

- [Install guide](./INSTALL.md)
- [Full catalog](./CATALOG.md)
- [Package contract](./docs/shareable-folder-package.md)
- [Engineering family index](./categories/industry-1-software-it/agents/engineering/README.md)
- [Platform engineering family index](./categories/industry-1-software-it/agents/platform-engineering/README.md)

## What this repo is for

Use this repository if you want to:
- browse ready-to-install OpenClaw agents by role
- pick a specialist agent instead of starting from a blank workspace
- install a published package into your own OpenClaw setup through the public Clawin catalog flow

## What this repo is not

This repository does **not** include the private production pipeline.
It does not contain:
- raw role-source documents
- normalization or generation scripts
- internal review queues
- private run logs or private specs
- production environment details

## Current public release

Current published catalog snapshot:
- Industries (`4`):
  - `industry-1-software-it`
  - `industry-3-marketplace-ecommerce`
  - `industry-4-digital-marketing-agency`
  - `industry-5-content-media-platform`
- Total install-ready agent packages: **1343**
- Breakdown by industry:
  - `industry-1-software-it` — **394**
  - `industry-3-marketplace-ecommerce` — **355**
  - `industry-4-digital-marketing-agency` — **283**
  - `industry-5-content-media-platform` — **311**

For the full breakdown by role family and per-agent links, see:
- [CATALOG.md](./CATALOG.md)

## Featured starting points

If you want a quick place to start, these are strong entry points:

### Frontend Engineer (JS/TS)
- Path: `categories/industry-1-software-it/agents/engineering/software-it-frontend-engineer-js-ts/`
- Direct link: [open package](./categories/industry-1-software-it/agents/engineering/software-it-frontend-engineer-js-ts/)
- Good for: web UI implementation, component work, frontend delivery
- Bundled skills: `coding-agent`, `ui-ux-pro-max`, `frontend-design`

### Backend Engineer (Java)
- Path: `categories/industry-1-software-it/agents/engineering/software-it-backend-engineer-java/`
- Direct link: [open package](./categories/industry-1-software-it/agents/engineering/software-it-backend-engineer-java/)
- Good for: backend services, APIs, Java-centric delivery
- Bundled skills: `coding-agent`

### Kubernetes Platform Engineer (Go)
- Path: `categories/industry-1-software-it/agents/platform-engineering/software-it-kubernetes-platform-engineer-go/`
- Direct link: [open package](./categories/industry-1-software-it/agents/platform-engineering/software-it-kubernetes-platform-engineer-go/)
- Good for: platform operations, Kubernetes-heavy engineering environments
- Bundled skills: `coding-agent`, `healthcheck`

See the full catalog in:
- [CATALOG.md](./CATALOG.md)

## Install in a few minutes

1. Install the CLI:
   - `npm install -g agents.clawin`
2. Initialize it:
   - `clawin init`
3. Refresh from a published catalog:
   - `clawin catalog refresh --catalog https://agents.clawin.club/releases/2026-03-15-p0-canary-3-agent/catalogs/published/catalog.json`
4. Search or inspect an agent:
   - `clawin search "web performance"`
   - `clawin info software-it-web-performance-engineer-js-ts`
5. Install the agent:
   - `clawin install software-it-web-performance-engineer-js-ts`
6. Review local result and config follow-up:
   - `clawin status software-it-web-performance-engineer-js-ts`

Detailed instructions:
- [INSTALL.md](./INSTALL.md)

## Package contract

Each published package is expected to be a directly shareable agent folder.
A package includes:
- `README.md`
- `INSTALL.md`
- `PACKAGE.json`
- `workspace/`
- `workspace/skills/`
- `config/`

Clawin packages are intentionally **self-contained**.
If an agent depends on skills to do its job well, those required skills stay bundled with the package even when similar capabilities appear in other agents. That overlap is treated as part of the agent's role-specific identity, not as a catalog mistake.

Formal contract:
- [docs/shareable-folder-package.md](./docs/shareable-folder-package.md)

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

## License

Repository-level Clawin-authored catalog materials are released under **Apache License 2.0**.

Because some published packages include bundled skills and embedded upstream components, also read:
- [LICENSE](./LICENSE)
- [NOTICE](./NOTICE)
- [THIRD_PARTY.md](./THIRD_PARTY.md)

If a bundled component ships with its own license file or origin metadata, treat that component according to its own terms.

## Notes

- Secrets are intentionally excluded.
- Users must provide their own local provider configuration.
- These packages are designed for catalog-driven OpenClaw installs, not as standalone apps.
- Future releases should continue expanding this catalog with curated agent outputs from the private source repository.
