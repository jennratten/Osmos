# Demo 1 — Synthetic claims medallion

## Goal

Build a Microsoft Fabric data engineering solution from four synthetic files, preserving raw inputs in Bronze, conforming and validating records in Silver, producing a monthly claims summary in Gold, and retaining rejected records with reason codes.

## Provided content

- Prompt: [`../../prompts/01-osmos-explicit/osmos-medallion-architecture-claims-analysis-using-synthetic-file-data-.txt`](../../prompts/01-osmos-explicit/osmos-medallion-architecture-claims-analysis-using-synthetic-file-data-.txt)
- Presentation: [`../../presentation/Osmos_DFW_Fabric_User_Group.pptx`](../../presentation/Osmos_DFW_Fabric_User_Group.pptx)
- Recording: [YouTube](https://youtu.be/b5K9Eo41HrI?si=1WBMphbUmy21YpMp)

## Prepare separately

The source package does not include these files. Create small, synthetic, non-sensitive datasets:

- `claims.csv`
- `members.csv`
- `providers.csv`
- `policies.csv`

Include enough controlled conditions to test the contract, such as exact duplicate claims, a missing provider/member/policy reference, an invalid claim/service date, and an invalid or out-of-range paid amount. Document the expected accepted/rejected row counts and amount totals before the demo.

Also prepare:

- A dedicated Fabric development workspace on supported capacity.
- A target Lakehouse and a location in which the four files can be discovered.
- Contributor-or-higher access and Project Osmos availability.
- A clean Copilot CLI/VS Code context with Project Osmos and Fabric Skills visible.

## Conversation sequence

This is an **Osmos-explicit** prompt.

1. Paste the attached prompt as the first task turn.
2. Provide the full Fabric browser URL when asked and confirm the exact workspace and Lakehouse.
3. Require a plan before writes. Check that it names Bronze, Silver, Gold, exception handling, validation/reconciliation, idempotency, a validation notebook, and a concise README.
4. Correct assumptions about file paths, schemas, keys, dates, amounts, or duplicate behavior before approving execution.
5. Approve only the bounded plan.

## Evidence to collect

- Artifact inventory and locations.
- Bronze ingestion metadata and source row counts.
- Silver schemas, deterministic business keys, duplicate behavior, accepted/rejected counts, and exception reason codes.
- Broken member/provider/policy relationship results.
- Source-to-Silver and Silver-to-Gold row/amount reconciliation.
- Gold monthly totals by policy, provider specialty, and service month.
- Validation notebook output and generated README/assumptions.
- A second run proving no unintended duplicate outputs.

## Reset

Before presenting, decide whether reset means deleting demo-only tables/files or restoring a clean Lakehouse snapshot. Do not improvise destructive cleanup during the live session. Preserve one known-good result as a fallback.

## Success condition

The demo is complete only when the artifacts are inspectable, exceptions are explainable, totals reconcile, and an identical rerun does not create duplicate business results.
