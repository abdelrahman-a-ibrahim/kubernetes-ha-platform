# Functional and quality requirements

Status: proposed requirements, not delivered capabilities.

## Purpose
A platform for deploying stateful and stateless workloads with documented failure domains and recovery procedures. The design brings together Kubernetes placement controls, ingress, MetalLB and Longhorn, with availability claims tied to the topology actually tested.

## Target capabilities
- Write a topology and failure-domain plan. Compare a local virtual-node cluster with a cluster across physical hosts; document limits on HA evidence.
- Bootstrap a supported cluster and verify host/storage prerequisites. Choose a compatible CNI and reserve a non-conflicting MetalLB address pool.
- Deploy ingress and an application with readiness, resource limits, topology spread and a disruption budget. Test graceful shutdown.
- Add Longhorn only where node privileges and storage prerequisites are satisfied. Run volume replica, detach/attach and restore exercises.
- Measure availability during node loss, network disruption and storage failure. Record RTO/RPO observations, backup locations and cleanup.

## Acceptance criteria
- Availability report includes placement, hardware assumptions and observed errors.
- Storage recovery is tested rather than inferred from a replica count.
- Ingress remains reachable for faults the topology actually tolerates.
- A backup can be restored; a disruption budget is not described as preventing involuntary failures.

## Cross-cutting requirements
- Reproducible configuration and documented version requirements.
- Explicit invalid-input, authorization and dependency-failure behavior.
- Clearly defined durable state, retries and concurrency boundaries.
- Observable operations with bounded, non-sensitive diagnostic output.
- A documented resource lifecycle, recovery procedure and cleanup path.

## Scope control
This repository owns its implementation and contracts. Optional integrations with other personal projects use versioned interfaces. Sample data is synthetic. External accounts and paid services are not required for the current source checks.
