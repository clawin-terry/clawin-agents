# Shareable Folder Package Contract

This document defines the expected shape of a release-ready Clawin agent folder package.

## Goal
Each fine-grained role package in the repository should be directly shareable as a folder without an extra export step.

## Canonical Repository Location
```text
categories/<industry-id>/agents/<role-family-key>/<agentId>/
```

## Canonical Package Contents
```text
<agentId>/
  README.md
  INSTALL.md
  PACKAGE.json
  workspace/
    README.md
    SOUL.md
    IDENTITY.md
    USER.md
    AGENTS.md
    PLAYBOOK.md
    TOOLS.md
    HEARTBEAT.md
    skills/
  config/
    openclaw.agent.<agentId>.entry.json
    openclaw.agent.<agentId>.snippet.json
    SECRETS.md
```

## Packaging Rules
- Keep all persisted content in English.
- Treat the repository path as the catalog path.
- Treat `~/.openclaw/agents/<agentId>/` as the target install path.
- Bundle each required skill under `workspace/skills/` so the package remains self-contained.
- Do not require a separate global skill copy step for bundled skills.
- Keep secrets out of the package.

## Config Rules
A release-ready package should provide:
- a single-agent entry JSON object for `agents.list`
- a wrapper snippet JSON for users who prefer full-structure merge fragments
- explicit `workspace` and `agentDir` install paths
- a concrete recommended model id

A release-ready package should not include:
- provider API keys
- channel auth state
- recipient-specific bindings

## Install Rule
The package must be installable by copying the folder and merging the config entry, with only recipient-specific secrets left to fill.

## Validation Checklist
A package passes the shareable-folder contract only if:
- package-level docs exist
- workspace files exist
- bundled skills live under `workspace/skills/`
- config entry and wrapper snippet both exist
- config paths point to the target install path, not the repository path
- no secrets are stored in the package
