# Install Clawin Agents from the Public Catalog

Clawin now supports **two practical install paths**:

1. **Discover by chat** when you do not know the right agent yet
2. **Install by known ID** when you already know the exact package you want

Both paths use the same public catalog and end in the same local OpenClaw install flow.

---

## Prerequisites

- Node.js and npm available on the target machine
- an existing OpenClaw installation
- permission to edit the target OpenClaw config
- a working model/provider setup for the machine where the agent will run

---

## Path A — Discover and install by chat

Use this path when you want OpenClaw to help you find the right Clawin package first.

### 1. Install or update the Clawin install skill

```bash
clawhub install clawin-agent-match-install
```

### 2. Make sure the public Clawin CLI is available locally

```bash
npm install -g agents.clawin
clawin init
```

### 3. Refresh from the current public catalog release

```bash
clawin catalog refresh --catalog https://agents.clawin.club/releases/2026-03-18-p6-full-catalog-1395-agent/catalogs/published/catalog.json
```

### 4. Ask OpenClaw to find the right agent

Example prompts:

- `Find me a Clawin agent for frontend performance work.`
- `I need a Clawin agent for financial research company analysis.`
- `Recommend a Clawin agent for growth and attribution work.`

Expected flow:
- the skill searches the public Clawin catalog
- it recommends one or more candidate agents
- it may compare options or explain tradeoffs
- it should ask for confirmation before the actual install step

### 5. Confirm the install

After confirmation, use the recommended install path for the chosen agent. If you want to run the final install step yourself, use the direct path below.

---

## Path B — Install directly by known agent ID

Use this path when you already know the exact package you want.

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

Recommended direct command:

```bash
clawin install financial-research-company-research-analyst --allow-main
```

The recommended direct path installs the agent and completes the registration steps needed so `main` can call it.

If you prefer the older explicit mental model, this is the modern one-step equivalent of install + register + allow-main.

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

---

## Good first installs

Software / developer path:

```bash
clawin info software-it-web-performance-engineer-js-ts
clawin install software-it-web-performance-engineer-js-ts --allow-main
```

Research path:

```bash
clawin info financial-research-company-research-analyst
clawin install financial-research-company-research-analyst --allow-main
```

---

## Important notes

- Do not commit your local secrets back into this repository.
- The public catalog is release-scoped; refresh the catalog again when you want a newer published release.
- Bundled agent-specific skills still live under `workspace/skills/` inside installed packages when included.
- Clawin packages intentionally keep required skills inside each agent package so a single install remains usable on its own.
- The conversational install skill helps you choose, but it may still ask you to confirm before the final install runs.
- Provider API keys, channel auth state, recipient-specific bindings, and environment-specific routing choices remain local responsibilities.
