---
name: clawin-middleware-distributed-systems
description: Middleware and distributed systems guidance for gateways, service communication, policy control, and runtime reliability.
---

# Middleware and Distributed Systems

Use this skill for API gateways, middleware layers, and inter-service control planes.

## Focus Areas
- Traffic policy design (routing, quotas, auth propagation, multi-tenant guards)
- Service communication reliability (timeouts, retries, hedging, fallback)
- Compatibility and evolution (protocol contracts, schema migration strategy)
- Control-plane/data-plane separation and operational safety
- Observability and incident handling for distributed request paths

## Working Style
- Design for partial failure as a baseline, not an edge case.
- Make policy and behavior explicit with testable rules.
- Prefer incremental rollout with clear blast-radius controls.