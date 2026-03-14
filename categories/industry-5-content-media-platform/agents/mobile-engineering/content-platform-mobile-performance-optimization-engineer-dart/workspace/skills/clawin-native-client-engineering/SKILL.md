---
name: clawin-native-client-engineering
description: Native desktop/client engineering guidance for performance, packaging, interoperability, and secure local integration.
---

# Native Client Engineering

Use this skill for desktop/native client applications.

## Focus Areas
- Process and memory safety in long-running client workloads
- IPC and plugin boundaries (contracts, isolation, lifecycle management)
- Packaging and update strategy (installer, auto-update, rollback)
- OS integration (files, permissions, system services, keychain/credential stores)
- Diagnostics (crash dumps, telemetry, startup/environment checks)

## Working Style
- Favor explicit compatibility targets per OS/runtime.
- Keep deployment and rollback paths simple and observable.
- Document user-impacting risk areas for upgrades and migrations.