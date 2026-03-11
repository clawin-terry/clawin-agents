# SECRETS (fill on the target machine)

This package contains **no secrets**.

## Included and already configured
- agent workspace path
- agent state directory path
- recommended model id
- bundled agent-specific skills under `workspace/skills/`

## Still required on the target machine
1. Configure the provider credentials needed for the model id `mycodex/gpt-5.4`.
2. If you prefer a different model, change `model.primary` in the config entry/snippet.
3. Add any channel-specific tokens or login state on the target machine.
4. Add routing bindings if the target machine should receive inbound messages for this agent.

## Typical provider setup
In the target machine's `~/.openclaw/openclaw.json`, configure the relevant provider under `models.providers.<provider>`.
For example, set:
- `apiKey`
- optional `baseUrl`

Do not commit or share real secrets inside this package.