# Architecture

Status: proposed. Components shown below are implementation targets.

## Product context
A platform for deploying stateful and stateless workloads with documented failure domains and recovery procedures. The design brings together Kubernetes placement controls, ingress, MetalLB and Longhorn, with availability claims tied to the topology actually tested.

## Component view
```text
Client -> development environment network / MetalLB -> Ingress -> replicated application
                                                   |
                                          persistent storage / Longhorn
```

## Design decisions
- Local cluster versus independent physical failure domains
- Storage replication versus backup
- Ingress and address-pool constraints

Record decisions and alternatives in [ADR 0001](adr/0001-system-boundaries.md). Define authoritative state, acknowledgement boundaries, identities, retry behavior and recovery ownership before implementing adapters.

## Interface boundary
`src/kubernetes_ha_platform/interfaces.py` defines the initial application boundary. Return models and error contracts remain to be specified. These interfaces do not implement the component graph.

## Integration boundaries
Local adapters and synthetic fixtures precede external integrations. Every live adapter needs an explicit identity, permission scope, timeout strategy and observability contract. Separate user-supplied content from execution authority.

## Deployment design
Document topology, dependency versions, configuration and state persistence alongside the first executable delivery. Record what local environments cannot establish about availability, ordering or durability.

## Compatibility
Version interfaces and fixtures when their semantics change. Sibling projects are optional integrations, not implicit filesystem dependencies.
