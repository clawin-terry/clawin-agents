---
name: clawin-backend-service-engineering
description: Backend and service engineering playbook for API-first systems, data contracts, reliability, and operability.
---

# Backend Service Engineering

Use this skill when building or reviewing backend APIs and service logic.

## Focus Areas
- API contract clarity (versioning, idempotency, pagination, error model)
- Data and state boundaries (transactions, consistency, migrations)
- Reliability defaults (timeouts, retries, circuit-breaking, backpressure)
- Operability (structured logs, metrics, traces, SLO-oriented checks)
- Safe delivery (feature flags, rollback paths, compatibility tests)

## Working Style
- Prefer minimal, production-viable designs over framework-heavy rewrites.
- Call out assumptions about throughput, failure modes, and data growth.
- Include concrete verification steps for endpoint behavior and failure handling.