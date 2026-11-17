# Implementation backlog

Status: all milestones unstarted. Check a task only when its evidence exists.

## M1 — Design and contracts

Write a topology and failure-domain plan. Compare a local virtual-node cluster with a cluster across physical hosts; document limits on HA evidence.

- [ ] Turn this milestone into a small design/task note with inputs and outputs.
- [ ] Implement the smallest complete behavior for this milestone.
- [ ] Add positive, negative and recovery checks relevant to this behavior.
- [ ] Record commands, environment and observed results in the learning journal.
- [ ] Update the README status and architecture if the implementation changes them.

**Review gate:** demonstrate the behavior, explain a tradeoff and link actual evidence. Do not mark complete using foundation checks alone.

## M2 — Build the first path

Bootstrap a supported cluster and verify host/storage prerequisites. Choose a compatible CNI and reserve a non-conflicting MetalLB address pool.

- [ ] Turn this milestone into a small design/task note with inputs and outputs.
- [ ] Implement the smallest complete behavior for this milestone.
- [ ] Add positive, negative and recovery checks relevant to this behavior.
- [ ] Record commands, environment and observed results in the learning journal.
- [ ] Update the README status and architecture if the implementation changes them.

**Review gate:** demonstrate the behavior, explain a tradeoff and link actual evidence. Do not mark complete using foundation checks alone.

## M3 — Integrate deliberately

Deploy ingress and an application with readiness, resource limits, topology spread and a disruption budget. Test graceful shutdown.

- [ ] Turn this milestone into a small design/task note with inputs and outputs.
- [ ] Implement the smallest complete behavior for this milestone.
- [ ] Add positive, negative and recovery checks relevant to this behavior.
- [ ] Record commands, environment and observed results in the learning journal.
- [ ] Update the README status and architecture if the implementation changes them.

**Review gate:** demonstrate the behavior, explain a tradeoff and link actual evidence. Do not mark complete using foundation checks alone.

## M4 — Handle failure

Add Longhorn only where node privileges and storage prerequisites are satisfied. Run volume replica, detach/attach and restore exercises.

- [ ] Turn this milestone into a small design/task note with inputs and outputs.
- [ ] Implement the smallest complete behavior for this milestone.
- [ ] Add positive, negative and recovery checks relevant to this behavior.
- [ ] Record commands, environment and observed results in the learning journal.
- [ ] Update the README status and architecture if the implementation changes them.

**Review gate:** demonstrate the behavior, explain a tradeoff and link actual evidence. Do not mark complete using foundation checks alone.

## M5 — Demonstrate and operate

Measure availability during node loss, network disruption and storage failure. Record RTO/RPO observations, backup locations and cleanup.

- [ ] Turn this milestone into a small design/task note with inputs and outputs.
- [ ] Implement the smallest complete behavior for this milestone.
- [ ] Add positive, negative and recovery checks relevant to this behavior.
- [ ] Record commands, environment and observed results in the learning journal.
- [ ] Update the README status and architecture if the implementation changes them.

**Review gate:** demonstrate the behavior, explain a tradeoff and link actual evidence. Do not mark complete using foundation checks alone.

