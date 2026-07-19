---
title: "PodGroup"
linkTitle: "PodGroup"
weight: 20
description: "The gang-scheduling unit: a set of pods the scheduler places all-or-nothing."
---

A **PodGroup** is the unit of gang scheduling in KAI Scheduler. It represents a set of pods that belong to the same logical workload and must be scheduled as a group: the scheduler either places the group's required minimum number of pods **all at once**, or none of them. This all-or-nothing behavior is what lets distributed workloads — multi-worker training, MPI/HPC jobs, distributed inference — start reliably without deadlocking on partially-allocated resources.

Every workload scheduled by KAI belongs to exactly one PodGroup, and every PodGroup belongs to a [queue](../queues/_index.md).

## How PodGroups are created

In most cases you **never create a PodGroup by hand**. The [Pod Grouper](../../developer/pod-grouper.md) component watches incoming pods, finds their top-level owner, and automatically creates and maintains a PodGroup for the workload. It ships plugins for common workload types — plain `Deployment`/`Job`, Kubeflow (`PyTorchJob`, `TFJob`, …), Ray, Spark, and more — so submitting a supported workload is enough.

Pods are linked to their PodGroup by the `pod-group-name` annotation on the pod (set automatically by the Pod Grouper).

**Creating one directly** is supported for advanced cases (see [external PodGroups](../../developer/pod-grouper.md#external-podgroups)): set `kai.scheduler/skip-podgrouper: "true"` so the Pod Grouper leaves membership alone, create the `PodGroup` resource yourself, and set `pod-group-name` on the pods.

## Example

```yaml
apiVersion: scheduling.run.ai/v2alpha2
kind: PodGroup
metadata:
  name: my-training-job
  namespace: team-a
spec:
  minMember: 4                 # schedule all 4 workers together, or none
  queue: default-queue         # the queue this workload draws resources from
  priorityClassName: train     # optional workload priority
```

A pod joins that group via its annotation:

```yaml
metadata:
  annotations:
    pod-group-name: my-training-job
```

## Key fields

| Field | Description |
|-------|-------------|
| `minMember` | Minimum number of pods that must be schedulable together for the group to start. Mutually exclusive with `minSubGroup`. |
| `queue` | The [queue](../queues/_index.md) the PodGroup draws resources from. If the queue does not exist, the group is not scheduled. |
| `priorityClassName` | Workload [priority](../../user-guide/workload-priority/_index.md). Determines scheduling order and, by default, preemptibility. |
| `preemptibility` | `preemptible` or `non-preemptible`. Overrides the priority-based default (priorities below 100 are preemptible). |
| `subGroups` / `minSubGroup` | Finer-grained subsets of pods with their own constraints, enabling hierarchical and multi-level gang scheduling. |
| `topologyConstraint` | Required/preferred [topology](../../user-guide/topology-aware-scheduling/_index.md) placement for the group's pods. |
| `preemptionDelay` | How long the group must stay pending before it may evict other workloads (see [Preemption Delay](../../user-guide/preemption-delay/_index.md)). |
| `schedulingBackoff` | Number of scheduling cycles to try before marking the group unschedulable on a node pool. |
| `markUnschedulable` | Whether to emit `Unschedulable` events on the group's pods. |

## Elastic workloads and SubGroups

Because `minMember` is a *minimum*, a PodGroup can be **elastic**: set `minMember` below the total pod count and the scheduler runs the gang once the minimum is met, scaling up opportunistically as capacity frees up. See [Elastic Workloads](../../user-guide/elastic-workloads/_index.md).

For multi-level workloads (for example, distributed and disaggregated serving such as Dynamo/Grove), **SubGroups** partition a PodGroup into nested subsets, each with its own `minMember`/`minSubGroup` and topology constraints. See [Multi-Level Topology-Aware Scheduling](../../user-guide/topology-aware-scheduling/multilevel.md).

## Status

The PodGroup's `status` reports how scheduling is progressing:

- **`conditions`** — the group's lifecycle conditions.
- **`schedulingConditions`** — why the group is unschedulable on a node pool, with structured reasons such as `NonPreemptibleOverQuota`, `OverLimit`, `QueueDoesNotExist`, and `PreemptionDelayNotElapsed`. This is the primary signal for explaining *why a workload is pending*.
- **`resourcesStatus`** — resources currently allocated (preemptible and non-preemptible) and requested by the group's pods.

## See also

- [Scheduling Queues](../queues/_index.md) — where a PodGroup's resources come from
- [Batch Scheduling](../../user-guide/batch-scheduling/_index.md) — running gang-scheduled workloads
- [Elastic Workloads](../../user-guide/elastic-workloads/_index.md) — `minMember` below the full pod count
- [Pod Grouper](../../developer/pod-grouper.md) — how PodGroups are created automatically
