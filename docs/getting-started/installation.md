---
title: "Installation"
linkTitle: "Installation"
weight: 10
description: "Prerequisites and installation methods for KAI Scheduler."
---

KAI Scheduler is installed into the `kai-scheduler` namespace.

> ⚠️ When submitting workloads, use a dedicated namespace. Do not use the `kai-scheduler` namespace for workload submission.

## Prerequisites

Before installing KAI Scheduler, ensure you have:

- A running Kubernetes cluster
- [Helm](https://helm.sh/docs/intro/install) CLI installed
- [NVIDIA GPU-Operator](https://github.com/NVIDIA/gpu-operator) installed, in order to schedule workloads that request GPU resources

## Installation methods

KAI Scheduler can be installed:

- **From production (recommended)** — a published release from the container registry.
- **From source** — see [Building from Source](../developer/building-from-source.md).
- **With ArgoCD (GitOps)** — see the [GitOps installation guide](../administration/gitops/_index.md).

### Install from production

Locate the latest release version on the [releases](https://github.com/kai-scheduler/KAI-scheduler/releases) page.
Run the following command after replacing `<VERSION>` with the desired release version:

```sh
helm upgrade -i kai-scheduler oci://ghcr.io/kai-scheduler/kai-scheduler/kai-scheduler -n kai-scheduler --create-namespace --version <VERSION>
```

## Flavor-specific instructions

### OpenShift

When `gpu-operator` < v25.10.0 is installed, add the following flag to the installation command:

```
--set admission.gpuFractionRuntimeClassName=null
```

If CDI is enabled, add `--set binder.cdiEnabled=true` to the installation command.

### FIPS

FIPS-140-3-enabled image variants are available. See [FIPS-Enabled Images](../administration/fips/_index.md).

## Next steps

Continue to the [Quick Start](quick-start/_index.md) to create queues and submit your first workloads.
