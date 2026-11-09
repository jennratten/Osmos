# Demo 3 — Idempotent incremental sales load

## Source status

This scenario is described in the presentation, but no dedicated prompt text file was included in the attached source package. The starter prompt below is **reconstructed from the deck's stated prerequisites, task, proof, observability, and recovery requirements**. It is not represented as an original attachment.

## Goal

Build an incremental sales ingestion pattern that uses a watermark and Delta MERGE semantics, handles inserts/updates and any deliberately modeled deletes, persists batch metadata, reconciles results, and can rerun the second batch without changing counts or totals.

## Prepare separately

- `orders_day1.csv`
- `orders_day2.csv`, containing a controlled mix of new and updated orders; include deletes only if the chosen source contract defines a delete indicator.
- Expected row counts and amount totals after day 1 and day 2.
- A target Delta table design.
- A watermark/control table design.
- A dedicated Fabric development workspace and target Lakehouse.

## Conversation sequence

Use the **context-required** pattern:

1. Paste [`../../prompts/00-context/osmos-controlled-starter-prompt.txt`](../../prompts/00-context/osmos-controlled-starter-prompt.txt).
2. Provide the full Fabric browser URL, exact workspace, exact Lakehouse, input paths, business key, delete semantics, and expected day-1/day-2 results.
3. Confirm that the assistant will show and await approval on the plan.
4. Paste the reconstructed starter prompt below.

## Reconstructed starter prompt

```text
Build an idempotent incremental sales-ingestion solution in the confirmed
Microsoft Fabric workspace and Lakehouse using orders_day1.csv and
orders_day2.csv.

Requirements:
- Use order_id as the business key and implement a safe Delta MERGE.
- Load day 1, then process day 2 as an incremental batch.
- Apply inserts and updates, and handle deletes only according to the approved
  source delete contract.
- Maintain a watermark/control table and persist batch metadata, including a
  batch ID, source window/file, status, start/end timestamps, inserted count,
  updated count, deleted count if applicable, rejected count, and error detail.
- Add reconciliation checks for row counts and sales totals.
- Quarantine invalid records with reason codes rather than silently dropping
  them.
- Make retries and reruns safe: rerunning orders_day2.csv must leave final
  counts and totals unchanged.
- Produce the implementation artifacts, validation evidence, and concise
  operating/reset notes.

Before writing anything, show the plan, schemas, merge keys, watermark
semantics, artifacts, failure recovery, and validation approach, then ask for
approval.
```

## Run and prove

1. Run day 1 and capture target counts/totals, watermark, and batch-log row.
2. Run day 2 and capture inserted/updated/deleted/rejected counts plus final totals.
3. Rerun day 2 unchanged.
4. Prove final business counts and totals did not change and that the duplicate/retry attempt is observable.
5. Inspect watermark advancement and confirm it occurs only after required writes and validation succeed.

## Evidence to collect

- Target, watermark, and batch-log schemas.
- MERGE key and any delete contract.
- Day-1, day-2, and day-2-rerun counts/totals.
- Inserted/updated/deleted/rejected metrics.
- Watermark before/after each run.
- Failure/retry and reset behavior.
- Capacity/duration observations.

## Success condition

The day-2 rerun produces no unintended business changes, the control state is consistent with successful processing, and every batch is reconcilable and observable.
