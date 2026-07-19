---
title: "Developer Guide"
linkTitle: "Developer Guide"
weight: 50
description: "Internals and contributor documentation for KAI Scheduler."
---

Documentation for contributors and anyone working on KAI Scheduler internals.

- **[Scheduler Concepts](scheduler-concepts.md)** — Core building blocks: cycles, cache, sessions, actions, plugins, and BindRequests.
- **[Action Framework](action-framework.md)** — The action-based scheduling system (Allocate, Consolidate, Reclaim, Preempt).
- **[Plugin Framework](plugin-framework.md)** — The plugin architecture and session extension points.
- **[Binder](binder.md)** — The controller that executes pod binding, separated from scheduling.
- **[Pod Grouper](pod-grouper.md)** — Automatic PodGroup creation for gang scheduling.
- **[Building from Source](building-from-source.md)** — Build and deploy KAI images from source.
- **[Scale Tests](scale-tests.md)** — What the scale tests validate and how they run.
- **[Action Victim-Invariant Pre-Filter](action-victim-invariant-prefilter.md)** — Guard that skips solver work for unfixable pre-solver failures.
- **[Design Proposals](designs/)** — RFC-style design documents for major features.
