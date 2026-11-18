# Kubernetes HA Platform

A Kubernetes platform design combining workload availability, ingress, service networking and persistent storage.

**Status: In development** · Personal project by Abdelrahman Ahmed

## Overview

A platform for deploying stateful and stateless workloads with documented failure domains and recovery procedures. The design brings together Kubernetes placement controls, ingress, MetalLB and Longhorn, with availability claims tied to the topology actually tested.

## Current state

The repository currently contains the system design, delivery requirements, a synthetic input fixture and initial Python interfaces. Runtime behavior, service integrations and deployment are planned. Interface methods raise `NotImplementedError`; there is no running application or published runtime benchmark yet.

## Planned capabilities

- Documented cluster topology and independent failure-domain assumptions.
- Workload replication, health probes, placement controls and disruption budgets.
- Ingress and MetalLB service exposure.
- Longhorn storage integration with backup and restoration workflows.
- Availability and recovery verification during node and storage failures.

Detailed scope is tracked in the [delivery roadmap](docs/roadmap.md) and [requirements](docs/requirements.md).

## Architecture

```text
Client -> development environment network / MetalLB -> Ingress -> replicated application
                                                   |
                                          persistent storage / Longhorn
```

This is the proposed component design. See [architecture](docs/architecture.md) for boundaries and [architecture decisions](docs/adr/0001-system-boundaries.md) for the choices still to resolve.

## Technology direction

Kubernetes · Longhorn · MetalLB · Ingress · Linux · Availability.

These technologies describe the intended implementation. Dependencies and compatible versions will be pinned when introduced. Optional services are not required by the current source checks.

## Working with the source

```sh
git clone https://github.com/abdelrahman-a-ibrahim/kubernetes-ha-platform.git
cd kubernetes-ha-platform
python3 tools/check_project.py
```

Python 3.9+ is sufficient for the current standard-library source check. It parses Python and JSON and checks required project files. It does **not** run an application, validate deployment behavior or establish feature completion.

The initial application boundary is in [`src/kubernetes_ha_platform/interfaces.py`](src/kubernetes_ha_platform/interfaces.py). [`examples/scenario.json`](examples/scenario.json) provides a synthetic development input. Installation and runtime commands will be added with the first executable release.

## Quality and reliability

- Availability report includes placement, hardware assumptions and observed errors.
- Storage recovery is tested rather than inferred from a replica count.
- Ingress remains reachable for faults the topology actually tolerates.
- A backup can be restored; a disruption budget is not described as preventing involuntary failures.

These are acceptance targets. Failure scenarios are specified in [reliability verification](docs/reliability.md); [results](docs/verification/README.md) will be recorded as implementation progresses. Correctness and performance claims must reference an actual environment, workload and commit.

## Development roadmap

- [ ] Contracts and system boundaries
- [ ] Core implementation and behavior tests
- [ ] External adapters and scoped access
- [ ] Failure recovery and operational visibility
- [ ] Reproducible deployment and release validation

See [delivery stages and future scope](docs/roadmap.md). For deployment prerequisites and resource lifecycle, see [operations](docs/operations.md).

## Repository structure

```text
src/kubernetes_ha_platform/       Initial application interfaces
examples/                  Synthetic development inputs
tests/                     Behavior verification plan
docs/architecture.md       Component design and boundaries
docs/requirements.md       Functional and quality requirements
docs/roadmap.md            Delivery stages and future scope
docs/reliability.md        Failure and recovery scenarios
docs/operations.md         Runtime and deployment plan
docs/verification/         Results as implementation progresses
tools/check_project.py     Source integrity check
```

## Development

Use focused feature branches, add behavior tests with implementation changes and update the relevant architecture decision when guarantees change. Read [CONTRIBUTING.md](CONTRIBUTING.md).

This is an independent personal project. Examples use synthetic data. See [NOTICE.md](NOTICE.md) for licensing status.

## References

- https://kubernetes.io/docs/concepts/workloads/pods/disruptions/
- https://longhorn.io/docs/
- https://metallb.io/
