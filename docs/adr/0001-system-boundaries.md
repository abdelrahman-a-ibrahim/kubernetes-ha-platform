# ADR 0001: System boundaries and implementation approach

Status: proposed.

## Context
A platform for deploying stateful and stateless workloads with documented failure domains and recovery procedures. The design brings together Kubernetes placement controls, ingress, MetalLB and Longhorn, with availability claims tied to the topology actually tested.

## Questions
- Local cluster versus independent physical failure domains
- Storage replication versus backup
- Ingress and address-pool constraints

## Alternatives
- A local implementation with synthetic external adapters.
- An integrated deployment with real dependencies in an isolated environment.
- A smaller implementation that preserves the core invariant.

## Decision
Pending. Record the selected option, rejected alternatives and rationale before implementing external adapters.

## Consequences
Assess correctness, operational complexity, cost, security boundaries, recovery and maintenance. Define the concrete constraint that would justify revisiting the decision.
