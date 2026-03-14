# Install SAST and DAST Platform Engineer (Java/Python)

## Goal
Install this shareable OpenClaw agent folder package on a target machine.

## Target location
Copy this folder to:

```text
~/.openclaw/agents/software-it-sast-dast-platform-engineer-java-python
```

The final installed layout should look like:

```text
~/.openclaw/agents/software-it-sast-dast-platform-engineer-java-python/
  workspace/
  config/
  INSTALL.md
  PACKAGE.json
```

## Steps
1. Copy this entire folder to `~/.openclaw/agents/software-it-sast-dast-platform-engineer-java-python`.
2. Open `config/openclaw.agent.software-it-sast-dast-platform-engineer-java-python.entry.json`.
3. Append that JSON object to `agents.list` in the target machine's `~/.openclaw/openclaw.json`.
4. If you prefer a wrapper snippet, merge `config/openclaw.agent.software-it-sast-dast-platform-engineer-java-python.snippet.json` into the target config instead.
5. Review `config/SECRETS.md` and fill in the target machine's provider credentials or channel tokens.
6. Restart OpenClaw Gateway.

## Skill loading
This package keeps bundled skills under:

```text
~/.openclaw/agents/software-it-sast-dast-platform-engineer-java-python/workspace/skills
```

OpenClaw loads agent-specific skills from `workspace/skills/`, so no extra global skill copy step is required for the bundled skills in this package.

## Config paths used by this package
- workspace: `~/.openclaw/agents/software-it-sast-dast-platform-engineer-java-python/workspace`
- agentDir: `~/.openclaw/agents/software-it-sast-dast-platform-engineer-java-python/agent`

## Not included
This package does not include:
- provider secrets or API keys
- login state or channel auth sessions
- routing bindings specific to the recipient's environment