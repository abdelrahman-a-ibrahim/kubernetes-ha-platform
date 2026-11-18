# Verification plan

Runtime behavior tests will be added with the implementation. The current source integrity check does not provide runtime coverage.

## Required behavior coverage
- Availability report includes placement, hardware assumptions and observed errors.
- Storage recovery is tested rather than inferred from a replica count.
- Ingress remains reachable for faults the topology actually tolerates.
- A backup can be restored; a disruption budget is not described as preventing involuntary failures.

## Failure coverage
- Drain a node while requests are in flight.
- Terminate a pod during a write.
- Remove one storage replica in an isolated disposable cluster.
- Restore an application and volume from backup to a clean namespace.

Add domain tests, adapter contract tests and integration tests as those components are implemented. Include relevant invalid input, unauthorized access, concurrency, retry and restart scenarios. Real dependency guarantees require real integration evidence; mocks alone cannot establish ordering, replication, consistency or durability.

See [reliability](../docs/reliability.md) for execution/reporting requirements.
