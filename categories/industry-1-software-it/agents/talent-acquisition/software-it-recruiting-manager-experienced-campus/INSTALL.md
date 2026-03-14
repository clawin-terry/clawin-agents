# Install Recruiting Manager (Experienced / Campus)

## Goal
Install this shareable OpenClaw agent folder package on a target machine.

## Target location
Copy this folder to:

```text
~/.openclaw/agents/software-it-recruiting-manager-experienced-campus
```

The final installed layout should look like:

```text
~/.openclaw/agents/software-it-recruiting-manager-experienced-campus/
  workspace/
  config/
  INSTALL.md
  PACKAGE.json
```

## Steps
1. Copy this entire folder to `~/.openclaw/agents/software-it-recruiting-manager-experienced-campus`.
2. Open `config/openclaw.agent.software-it-recruiting-manager-experienced-campus.entry.json`.
3. Append that JSON object to `agents.list` in the target machine's `~/.openclaw/openclaw.json`.
4. If you prefer a wrapper snippet, merge `config/openclaw.agent.software-it-recruiting-manager-experienced-campus.snippet.json` into the target config instead.
5. Review `config/SECRETS.md` and fill in the target machine's provider credentials or channel tokens.
6. Restart OpenClaw Gateway.

## Skill loading
This package keeps bundled skills under:

```text
~/.openclaw/agents/software-it-recruiting-manager-experienced-campus/workspace/skills
```

OpenClaw loads agent-specific skills from `workspace/skills/`, so no extra global skill copy step is required for the bundled skills in this package.

## Config paths used by this package
- workspace: `~/.openclaw/agents/software-it-recruiting-manager-experienced-campus/workspace`
- agentDir: `~/.openclaw/agents/software-it-recruiting-manager-experienced-campus/agent`

## Not included
This package does not include:
- provider secrets or API keys
- login state or channel auth sessions
- routing bindings specific to the recipient's environment