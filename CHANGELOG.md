# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## [Unreleased]



















## [v0.6.21-rc.3] - 2025-11-24

No significant changes documented.


## [v0.6.21-rc.2] - 2025-11-24

No significant changes documented.


## [v0.9.20-rc.2] - 2025-11-24

No significant changes documented.


## [v0.9.20-rc.1] - 2025-11-24

No significant changes documented.


## [v0.6.20] - 2025-11-24

### Added
- 18 [#30](https://github.com/gshaibi/KAI-Scheduler/pull/30) [gshaibi](https://github.com/gshaibi)

### Fixed
- 18 [#30](https://github.com/gshaibi/KAI-Scheduler/pull/30) [gshaibi](https://github.com/gshaibi)


## [v0.9.19] - 2025-11-24

### Added
- 18 [#30](https://github.com/gshaibi/KAI-Scheduler/pull/30) [gshaibi](https://github.com/gshaibi)

### Fixed
- 18 [#30](https://github.com/gshaibi/KAI-Scheduler/pull/30) [gshaibi](https://github.com/gshaibi)


## [v0.9.18] - 2025-11-24

### Fixed
- 16 fixed [#26](https://github.com/gshaibi/KAI-Scheduler/pull/26) [gshaibi](https://github.com/gshaibi)


## [v0.9.17] - 2025-11-24

No significant changes documented.


## [v0.9.16] - 2025-11-24

No significant changes documented.


## [v0.9.15] - 2025-11-24

### Added
- 14 [#22](https://github.com/gshaibi/KAI-Scheduler/pull/22) [gshaibi](https://github.com/gshaibi)

### Fixed
- 14 [#22](https://github.com/gshaibi/KAI-Scheduler/pull/22) [gshaibi](https://github.com/gshaibi)


## [v0.9.14] - 2025-11-24

No significant changes documented.


## [v0.9.13] - 2025-11-24

### Added
- 12 [#19](https://github.com/gshaibi/KAI-Scheduler/pull/19) [gshaibi](https://github.com/gshaibi)
- 13 [#18](https://github.com/gshaibi/KAI-Scheduler/pull/18) [gshaibi](https://github.com/gshaibi)

### Fixed
- 12 [#19](https://github.com/gshaibi/KAI-Scheduler/pull/19) [gshaibi](https://github.com/gshaibi)
- 13 [#18](https://github.com/gshaibi/KAI-Scheduler/pull/18) [gshaibi](https://github.com/gshaibi)


## [v0.9.11] - 2025-11-24

### Added
- 11 [#16](https://github.com/gshaibi/KAI-Scheduler/pull/16) [gshaibi](https://github.com/gshaibi)
- Added 11 [#16](https://github.com/gshaibi/KAI-Scheduler/pull/16) [gshaibi](https://github.com/gshaibi)
- Should be ignored [#16](https://github.com/gshaibi/KAI-Scheduler/pull/16) [gshaibi](https://github.com/gshaibi)

### Fixed
- 11 [#16](https://github.com/gshaibi/KAI-Scheduler/pull/16) [gshaibi](https://github.com/gshaibi)
- 11 [#16](https://github.com/gshaibi/KAI-Scheduler/pull/16) [gshaibi](https://github.com/gshaibi)
- Fixed 11 [#16](https://github.com/gshaibi/KAI-Scheduler/pull/16) [gshaibi](https://github.com/gshaibi)


## [v0.9.10] - 2025-11-24

### Fixed
- 10 [#14](https://github.com/gshaibi/KAI-Scheduler/pull/14) [gshaibi](https://github.com/gshaibi)


## [v0.9.8] - 2025-11-24

### Fixed
- 7 [#12](https://github.com/gshaibi/KAI-Scheduler/pull/12) [gshaibi](https://github.com/gshaibi)
- 7 [#13](https://github.com/gshaibi/KAI-Scheduler/pull/13) [github-actions[bot]](https://github.com/apps/github-actions)


## [v0.9.7] - 2025-11-24

### Added
- Added support for custom runtime classes 4 [#6](https://github.com/gshaibi/KAI-Scheduler/pull/6) [gshaibi](https://github.com/gshaibi)
- Added support for custom runtime classes 4 [#7](https://github.com/gshaibi/KAI-Scheduler/pull/7) [github-actions[bot]](https://github.com/apps/github-actions)


## [v0.9.6] - 2025-11-23

### Fixed
- Fixed scheduler pod group status update conflict [#5](https://github.com/gshaibi/KAI-Scheduler/pull/5) [github-actions[bot]](https://github.com/apps/github-actions)


## [v0.9.5] - 2025-11-23

No significant changes documented.


## [v0.9.1] - 20250-09-15

### Added
- Added the option of providing the podgrouper app a scheme object to use

## [v0.9.0] - 20250-09-10

### Added
- config.kai.scheduler CRD that will describe the installation of all KAI-scheduler services for the operator
- Initial KAI-operator implementation for managing components
- PodGroup Controller, Queue Controller, Admission and Scale Adjuster operands to operator lifecycle management
- Deployment of operator in Helm chart alongside pod group controller
- Deploy PodGroup Controller, Queue Controller, Admission and Scale Adjuster via operator for streamlined deployment
- schedulingshrards.kai.scheduler CRD that describes partitioning the cluster nodes for different scheduling options.

### Changed
- Moved the CRDs into the helm chart so that they are also installed by helm and not only by the crd-upgrader, but removed the external kueue clone of topology CRD from being automatically installed.
- Updated queue controller image name to align with current deployment standards

### Fixed
- Removed webhook manager component as part of operator-based refactoring

## [v0.8.5] - 20250-09-04

### Added
- Added configurable plugins hub for podgrouper using interface and RegisterPlugins

## [v0.8.4] - 20250-09-02

### Added
- Added a plugin to reflect joborder in scheduler http endpoint - Contributed by Saurabh Kumar Singh <singh1203.ss@gmail.com>

### Fixed
- Fixed a bug where workload with subgroups would not consider additional tasks above minAvailable

## [v0.8.3] - 20250-08-31

### Removed
- Removed unused code that required gpu-operator as a dependency

## [v0.8.2] - 2025-08-25

### Fixed
- Fixed wrong GPU memory unit conversion from node `nvidia.com/gpu.memory` labels
- Fixed incorrect MIG GPU usage calculation leading to wrong scheduling decision

## [v0.8.1] - 2025-08-20

### Added
- Added a new scheduler flag `--update-pod-eviction-condition`. When enabled, a DisruptionTarget condition is set on the pod before deletion

### Fixed
- Fixed scheduler panic in some elastic reclaim scenarios

## [v0.8.0] - 2025-08-18

### Added
- Added leader election configuration in all deployments and added global helm value that controls it during installation

## [v0.7.13] - 2025-08-12

### Added
- Separated admission webhooks from binder service to a separate `kai-admission` service

### Fixed
- crd-upgrader respects global values for nodeSelector, affinity and tolerations 
- kai-scheduler will not ignore pod spec.overhead field

## [v0.7.12] - 2025-08-04

### Fixed
- Fixed container env var overwrite to cover possible cases where env var with Value is replaced with ValueFrom or the other way

## [v0.7.7] - 2025-07-16

### Fixed
- Fixed a scenario where only GPU resources where checked for job and node, causing it to be bound instead of being pipelined

## [v0.7.6] - 2025-07-11

### Added
- Added GPU_PORTION env var for GPU sharing pods

## [v0.7.5] - 2025-07-10

### Fixed
- Fixed a miscalculation where cpu/memory releasing resources were considered idle when requesting GPU fraction/memory

## [v0.7.4] - 2025-07-09

### Changed
- Changed RUNAI-VISIBLE-DEVICES key in GPU sharing configmap to NVIDIA_VISIBLE_DEVICES

## [v0.7.3] - 2025-07-08

### Removed
- Removed GPU sharing configmap name resolution from env vars and volumes

## [v0.7.2] - 2025-07-07
### Added
- Added LeaderWorkerSet support in the podGrouper. Each replica will be given a separate podGroup.

## [v0.7.1] - 2025-07-07

### Added
- Added kueue topology CRD to kai installations

### Fixed
- Fixed cases where reclaim validation operated on outdated info, allowing invalid reclaim scenarios

## [v0.7.0] - 2025-07-02

### Added
- Added optional pod and namespace label selectors to limit the scope of monitored pods
- Added a plugin extension point for scheduler plugins to add annotations to BindRequests
- Added support for Grove

### Changed
- Changed `run.ai/top-owner-metadata` to `kai.scheduler/top-owner-matadata`

## [v0.6.0] - 2025-06-16

### Changed
- Changed `runai-reservation` namespace to `kai-resource-reservation`. For migration guide, refer to this [doc](docs/migrationguides/README.md)
- Changed `runai/queue` label key to `kai.scheduler/queue`. For migration guide, refer to [doc](docs/migrationguides/README.md)

### Fixed
- Fixed pod status scheduled race condition between the scheduler and the pod binding
- Removed redundant `replicas` key for binder from `values.yaml` as it is not used and not supported

### Removed
- Removed `runai-job-id` and `runai/job-id` annotations from pods and podgroups

### Added
- Added [minruntime](docs/plugins/minruntime.md) plugin, allowing PodGroups to run for a configurable amount of time without being reclaimed/preempted.
- PodGroup Controller that will update podgroups statuses with allocation data.
- Queue Controller that will update queues statuses with allocation data.


## [v0.5.1] - 2025-05-20

### Added
- Added support for [k8s pod scheduling gates](https://kubernetes.io/docs/concepts/scheduling-eviction/pod-scheduling-readiness/)
- nodeSelector, affinity and tolerations configurable with global value definitions
- Added `PreemptMinRuntime` and `ReclaimMinRuntime` properties to queue CRD
- Scheduler now adds a "LastStartTimestamp" to podgroup on allocation

### Changed
- Queue order function now takes into account potential victims, resulting in better reclaim scenarios.

### Fixed
- Fixed preempt/reclaim of elastic workloads only taking one pod.
- Scheduler now doesn't label pods' nodepool when nodepool label value is empty
