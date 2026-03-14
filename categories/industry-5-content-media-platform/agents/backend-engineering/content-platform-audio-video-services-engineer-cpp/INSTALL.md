# Install Audio and Video Services Engineer (C++)

## Goal
Install this shareable OpenClaw agent folder package on a target machine.

## Target location
Copy this folder to:

```text
~/.openclaw/agents/content-platform-audio-video-services-engineer-cpp
```

The final installed layout should look like:

```text
~/.openclaw/agents/content-platform-audio-video-services-engineer-cpp/
  workspace/
  config/
  INSTALL.md
  PACKAGE.json
```

## Steps
1. Copy this entire folder to `~/.openclaw/agents/content-platform-audio-video-services-engineer-cpp`.
2. Open `config/openclaw.agent.content-platform-audio-video-services-engineer-cpp.entry.json`.
3. Append that JSON object to `agents.list` in the target machine's `~/.openclaw/openclaw.json`.
4. If you prefer a wrapper snippet, merge `config/openclaw.agent.content-platform-audio-video-services-engineer-cpp.snippet.json` into the target config instead.
5. Review `config/SECRETS.md` and fill in the target machine's provider credentials or channel tokens.
6. Restart OpenClaw Gateway.

## Skill loading
This package keeps bundled skills under:

```text
~/.openclaw/agents/content-platform-audio-video-services-engineer-cpp/workspace/skills
```

OpenClaw loads agent-specific skills from `workspace/skills/`, so no extra global skill copy step is required for the bundled skills in this package.

## Config paths used by this package
- workspace: `~/.openclaw/agents/content-platform-audio-video-services-engineer-cpp/workspace`
- agentDir: `~/.openclaw/agents/content-platform-audio-video-services-engineer-cpp/agent`

## Not included
This package does not include:
- provider secrets or API keys
- login state or channel auth sessions
- routing bindings specific to the recipient's environment