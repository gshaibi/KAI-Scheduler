---
title: "Plugins"
linkTitle: "Plugins"
weight: 70
description: "Optional scheduler plugins and their configuration."
---

KAI Scheduler ships optional plugins that extend scheduling behavior. Enable and configure them per shard via the scheduler configuration.

- **[MinRuntime Plugin](minruntime.md)** — Protect jobs from preemption or reclaim for a minimum duration.
- **[Reflect Job Order Plugin](reflectjoborder.md)** — Expose the pending-job scheduling order over an HTTP endpoint.
- **[Snapshot Plugin](snapshot.md)** — Capture and analyze scheduler and cluster state.
