---
title: "Concepts"
linkTitle: "Concepts"
weight: 20
description: "The core scheduling primitives — queues and fairness — and how KAI decides what runs."
---

KAI Scheduler manages cluster resources through a hierarchy of **queues**. Workloads are submitted to a leaf queue, and on every scheduling cycle KAI decides which workloads run: it honors each queue's guaranteed quota, distributes spare capacity by priority and fairness, and reclaims resources when guarantees are violated.

These pages explain the building blocks and how they fit together:

- **[Scheduling Queues](queues/_index.md)** — The core resource primitive. Queues form a hierarchy and carry quota (guaranteed resources), over-quota weight, and limits.
- **[PodGroup](podgroup/_index.md)** — The gang-scheduling unit: a set of pods the scheduler places all-or-nothing. Usually created automatically from your workload.
- **[Fairness](fairness/_index.md)** — How KAI divides guaranteed and surplus resources between queues, and how it reclaims idle resources to keep usage fair.
- **[Scheduling Deep Dive](scheduling-deep-dive/_index.md)** — How queues, priority, fairness, and reclaim interact end-to-end across a scheduling cycle.

New to KAI? Read **Scheduling Queues** and **PodGroup** first, then **Fairness**, and finish with the **Scheduling Deep Dive** for the full picture.
