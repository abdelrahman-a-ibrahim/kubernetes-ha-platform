# Failure lab

These are planned experiments, not observed results. Begin with disposable local fixtures. For each experiment establish a baseline, inject one fault, record timestamps, verify invariants and perform cleanup.

## Project-specific experiments
1. Drain a node while requests are in flight.
2. Terminate a pod during a write.
3. Remove one storage replica in an isolated disposable cluster.
4. Restore an application and volume from backup to a clean namespace.

## Experiment record
Copy this block for each run:

- Experiment / commit:
- Date, platform and tool versions:
- Input dataset and deterministic seed where applicable:
- Expected invariant:
- Hypothesis:
- Exact fault and injection command:
- Start/end timestamps:
- Observed behavior and raw output location:
- Lost/duplicate/rejected operations, if applicable:
- Recovery steps and elapsed time:
- Pass/fail against the stated invariant:
- Environment limits / what this does not prove:
- Residual resources and cleanup result:

## Stop conditions
Stop when the fault escapes the disposable boundary, the evidence cannot identify the affected resources, or the planned resource/cost allowance is exceeded. Do not conduct these experiments on shared production systems.
