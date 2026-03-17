# Install an Agent from the Public Clawin Catalog

## Prerequisites

- Node.js and npm available on the target machine
- an existing OpenClaw installation
- permission to edit the target OpenClaw config
- a working model/provider setup for the machine where the agent will run

## Install steps

### 1. Install the Clawin CLI

```bash
npm install -g agents.clawin
```

### 2. Initialize Clawin on the machine

```bash
clawin init
```

This prepares the local Clawin workspace and config wiring used for catalog-driven installs.

### 3. Refresh from a published catalog

Catalog URL pattern:

```text
https://agents.clawin.club/releases/<release>/catalogs/published/catalog.json
```

Current full-catalog public release:

```bash
clawin catalog refresh --catalog https://agents.clawin.club/releases/2026-03-18-p6-full-catalog-1395-agent/catalogs/published/catalog.json
```

Current scoped financial research release (52 agents):

```bash
clawin catalog refresh --catalog https://agents.clawin.club/releases/2026-03-16-p5-financial-research-v2-52-agent/catalogs/published/catalog.json
```

Use the published release you want. The URL always points to a release-scoped catalog snapshot under `/releases/<release>/catalogs/published/catalog.json`.

### 4. Search and inspect agents

Search the catalog you just refreshed. For the full public catalog, a software example is:

```bash
clawin search "web performance"
```

For the financial research slice, an example is:

```bash
clawin search "financial research"
```

Inspect one package before install. Example financial research package:

```bash
clawin info financial-research-company-research-analyst
```

The scoped financial research release publishes 52 agent ids across the broader financial research industry roster, including equity analysis, screening and comparison, market monitoring, event and earnings monitoring, and portfolio research support.

### 5. Install the agent

```bash
clawin install financial-research-company-research-analyst
```

The install command handles the package fetch and local placement for you. You do not need to manually copy a folder from `categories/...` into `~/.openclaw/agents/<agentId>/`.

### 6. Review status and local config follow-up

Check the local install result:

```bash
clawin status financial-research-company-research-analyst
```

After install, finish the local-only pieces required by your environment:
- review the generated registration/config output
- keep provider credentials and other secrets local
- apply any environment-specific routing or recipient bindings

If the installed package ships a config entry or snippet, treat it as local configuration material. In safe-mode flows, review the generated registration/config snippet before enabling the agent in your own OpenClaw setup.

### 7. Reload OpenClaw if needed

If your OpenClaw process does not hot-reload the new registration automatically, reload or restart it so the agent becomes available.

## Important notes

- Do not commit your local secrets back into this repository.
- The public catalog is release-scoped; refresh the catalog again when you want a newer published release.
- Bundled agent-specific skills still live under `workspace/skills/` inside installed packages when included.
- Clawin packages intentionally keep required skills inside each agent package so a single install remains usable on its own.
- Provider API keys, channel auth state, recipient-specific bindings, and environment-specific routing choices remain local responsibilities.
