---
name: clawin-media-performance-systems
description: Media and performance-sensitive systems guidance for real-time pipelines, latency budgets, and quality stability.
---

# Media and Performance-Sensitive Systems

Use this skill for audio/video and other low-latency, throughput-sensitive engineering work.

## Focus Areas
- End-to-end latency budgeting and bottleneck identification
- Codec/pipeline choices, buffering strategy, and synchronization correctness
- CPU/GPU/memory profiling and sustained performance tuning
- Quality safeguards (drop policies, adaptation strategy, degradation behavior)
- Platform-specific constraints (drivers, hardware acceleration, device variance)

## Working Style
- Define measurable performance targets before implementation.
- Verify with realistic workload traces, not synthetic happy-path only.
- Prioritize stability under load over peak benchmark numbers.