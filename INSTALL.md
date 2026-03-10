# Install an Agent from this Repository

## Prerequisites

- an existing OpenClaw installation
- a working model/provider configuration on the target machine
- permission to edit the target OpenClaw config

## Install steps

### 1. Choose an agent package
Pick one agent folder from:

```text
categories/<industry-id>/agents/<role-family-key>/<agentId>/
```

Example:

```text
categories/industry-1-software-it/agents/engineering/i1-backend-engineer-java/
```

### 2. Copy the folder into your local OpenClaw agents directory
Target path:

```text
~/.openclaw/agents/<agentId>/
```

Example:

```text
~/.openclaw/agents/i1-backend-engineer-java/
```

### 3. Merge the provided config
Each package provides:
- `config/openclaw.agent.<agentId>.entry.json`
- `config/openclaw.agent.<agentId>.snippet.json`

Use:
- `entry.json` if you are adding one agent entry into `agents.list`
- `snippet.json` if you prefer a wrapper fragment for config merging

### 4. Fill local secrets and provider choices
Read:

```text
config/SECRETS.md
```

Provide your own local configuration for:
- model/provider credentials
- any recipient-specific routing or environment decisions

### 5. Reload OpenClaw
Reload or restart OpenClaw so the new agent is available.

### 6. Start using the agent
Open a chat with the installed agent and give it a task that matches its role.

## Important notes

- Do not commit your local secrets back into this repository.
- These packages are meant to be install-ready folders, not standalone apps.
- Bundled agent-specific skills live under `workspace/skills/` when included.
