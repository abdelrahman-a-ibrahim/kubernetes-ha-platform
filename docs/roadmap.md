# Delivery roadmap

Status: planned. No delivery stage is complete.

### 1. Contracts and system boundaries

Write a topology and failure-domain plan. Compare a local virtual-node cluster with a cluster across physical hosts; document limits on HA evidence.

- [ ] Implementation
- [ ] Behavior verification and failure coverage
- [ ] Documentation and reproducible results

### 2. Core implementation

Bootstrap a supported cluster and verify host/storage prerequisites. Choose a compatible CNI and reserve a non-conflicting MetalLB address pool.

- [ ] Implementation
- [ ] Behavior verification and failure coverage
- [ ] Documentation and reproducible results

### 3. Integrations and access controls

Deploy ingress and an application with readiness, resource limits, topology spread and a disruption budget. Test graceful shutdown.

- [ ] Implementation
- [ ] Behavior verification and failure coverage
- [ ] Documentation and reproducible results

### 4. Recovery and operational behavior

Add Longhorn only where node privileges and storage prerequisites are satisfied. Run volume replica, detach/attach and restore exercises.

- [ ] Implementation
- [ ] Behavior verification and failure coverage
- [ ] Documentation and reproducible results

### 5. Release validation

Measure availability during node loss, network disruption and storage failure. Record RTO/RPO observations, backup locations and cleanup.

- [ ] Implementation
- [ ] Behavior verification and failure coverage
- [ ] Documentation and reproducible results

## Future scope

- Linux compatibility preflight tool
- Restore to a new cluster
- Network-policy isolation experiments
- Latency measurement during storage rebuild

Select and pin implementation dependencies when introduced. Scope is refined through architecture decisions; completion requires working behavior and verification evidence.
