# Shareable Folder Package Contract

This document defines the expected shape of a release-ready Clawin agent folder package.

## Goal
Each fine-grained role package in the repository should be directly shareable as a folder and also package cleanly into a release zip without changing package internals.

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
    entry.json
    snippet.json
    SECRETS.md
```

## Packaging Rules
- Keep all persisted content in English.
- Treat the repository path as the catalog path.
- Treat `~/.openclaw/agents/<agentId>/` as the target install path.
- Bundle each required skill under `workspace/skills/` so the package remains self-contained.
- Do not require a separate global skill copy step for bundled skills.
- Accept repeated skill families across packages when they reflect role-specific behavior, depth, or workflow differences.
- Keep secrets out of the package.

## Config Rules
Preferred layout for new and regenerated packages:
- `config/entry.json`
- `config/snippet.json`

During the legacy transition window, repository tooling may also accept:
- `config/openclaw.agent.<agentId>.entry.json`
- `config/openclaw.agent.<agentId>.snippet.json`

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

The same package must also remain installable after zip packaging for release output generation.

## Validation Checklist
A package passes the shareable-folder contract only if:
- package-level docs exist
- workspace files exist
- bundled skills live under `workspace/skills/`
- config entry (`config/entry.json`) and wrapper snippet (`config/snippet.json`) both exist
- generator preflight must fail before overwrite when generated paths would exceed the conservative 240-char Windows safety budget
- forced overwrite may remove only the exact target package directory after confirming it stays within the allowed package root
- config paths point to the target install path, not the repository path
- no secrets are stored in the package
