# Reliability and failure verification

Status: verification scenarios planned; no results recorded yet.

## Required scenarios
- Drain a node while requests are in flight.
- Terminate a pod during a write.
- Remove one storage replica in an isolated disposable cluster.
- Restore an application and volume from backup to a clean namespace.

## Verification protocol
For each implemented scenario, document:
1. Commit, runtime versions, environment and topology.
2. Input workload and the expected invariant.
3. Baseline observations, fault injection and timestamps.
4. Observed errors, duplicate effects or state inconsistencies.
5. Recovery steps and measured time to restore behavior.
6. Resource cleanup and remaining limitations.

A simulator establishes application behavior within its assumptions. Real service ordering, consistency, failover and durability claims require verification against the selected dependencies. Distinguish those results in reports.

## Release evidence
- Availability report includes placement, hardware assumptions and observed errors.
- Storage recovery is tested rather than inferred from a replica count.
- Ingress remains reachable for faults the topology actually tolerates.
- A backup can be restored; a disruption budget is not described as preventing involuntary failures.

Store concise reports in [verification results](verification/README.md). Targets and illustrative fixture values must not be reported as measurements.
