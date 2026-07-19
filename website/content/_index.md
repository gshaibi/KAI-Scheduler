---
title: KAI Scheduler
---

{{< blocks/cover title="KAI Scheduler" image_anchor="top" height="auto" >}}
<img class="td-cover__logo" src="assets/kai-logo-dark.png" alt="KAI Scheduler" />
<p class="lead mt-3">A Kubernetes scheduler optimized for GPU resource allocation in AI &amp; ML workloads</p>

<a class="btn btn-lg btn-light me-3 mb-4" href="docs/">
  Read the docs <i class="fas fa-arrow-alt-circle-right ms-2"></i>
</a>
<a class="btn btn-lg btn-secondary me-3 mb-4" href="https://github.com/gshaibi/KAI-Scheduler">
  Source <i class="fab fa-github ms-2"></i>
</a>
{{< /blocks/cover >}}

{{% blocks/lead color="dark" %}}
KAI Scheduler is a robust, efficient, and scalable Kubernetes scheduler that dynamically allocates
GPU resources to AI and machine learning workloads — from small interactive jobs to large-scale
training and inference — while maintaining fairness across teams. It can run alongside other
schedulers on the cluster.
{{% /blocks/lead %}}

{{< blocks/section color="light" type="row" >}}

{{% blocks/feature icon="fas fa-layer-group" title="Batch & gang scheduling" %}}
Schedule all pods in a group together, or not at all. Elastic workloads scale between
minimum and maximum thresholds.

[Get started](docs/getting-started/)
{{% /blocks/feature %}}

{{% blocks/feature icon="fas fa-microchip" title="GPU sharing" %}}
Let multiple workloads share single or multiple GPUs by fraction or memory to maximize
utilization.

[GPU sharing guide](docs/user-guide/gpu-sharing/)
{{% /blocks/feature %}}

{{% blocks/feature icon="fas fa-balance-scale" title="Fairness & queues" %}}
Hierarchical queues with quotas, priorities, and Dominant Resource Fairness keep usage
fair across teams.

[Concepts](docs/concepts/)
{{% /blocks/feature %}}

{{< /blocks/section >}}

{{< blocks/section color="dark" type="row" >}}

{{% blocks/feature icon="fas fa-project-diagram" title="Topology-aware scheduling" %}}
Optimize placement using cluster network topology for modern distributed and disaggregated
serving architectures.
{{% /blocks/feature %}}

{{% blocks/feature icon="fas fa-cloud" title="Cloud & on-prem" %}}
Works with autoscalers such as Karpenter as well as static on-premise clusters.
{{% /blocks/feature %}}

{{% blocks/feature icon="fab fa-github" title="Contributions welcome!" url="https://github.com/gshaibi/KAI-Scheduler" %}}
We do a [Pull Request](https://github.com/gshaibi/KAI-Scheduler/pulls) contributions workflow on GitHub.
{{% /blocks/feature %}}

{{< /blocks/section >}}
