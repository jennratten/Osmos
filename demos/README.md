# Demo reproduction runbooks

The presentation describes three core demonstrations. Each runbook separates **provided content** from **environment/data that must be prepared separately**.

| Demo | Best use | Prompt source |
|---|---|---|
| [Synthetic claims medallion](01-synthetic-claims-medallion/) | End-to-end build across Bronze, Silver, Gold, exceptions, and validation. | Attached Osmos-explicit text prompt. |
| [Schema drift and quarantine](02-schema-drift-and-quarantine/) | Fast troubleshooting demo with investigation, versioned change, quarantine, and regression proof. | Attached context-required text prompt. |
| [Incremental sales load](03-incremental-sales-load/) | Production habits: watermark, MERGE, rerun safety, and observability. | Reconstructed from the presentation because no dedicated text prompt was attached. |

## Standard run sequence

1. Prepare a development workspace, Lakehouse, identity, permissions, capacity, and scenario-specific source data/artifacts.
2. Use the setup job aid and verify Project Osmos plus Microsoft Fabric Skills.
3. Establish the correct prompt pattern and exact target.
4. Ask for a plan; stop and correct scope, artifacts, write boundaries, or validation gaps before approval.
5. Execute while preserving checkpoints and approval decisions.
6. Inspect every created or modified artifact.
7. Run scenario acceptance checks and capture evidence.
8. Repeat any required batch/file to prove idempotency.
9. Record unresolved issues, capacity observations, and rollback/reset steps.

Never run a demo prompt against production merely to reproduce the presentation.
