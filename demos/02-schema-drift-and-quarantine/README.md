# Demo 2 — Schema drift and quarantine

## Goal

Diagnose why a previously successful ingestion notebook fails on a changed file, propose a backward-compatible remediation, preserve the original notebook, create a versioned copy, quarantine invalid rows, and prove both old and new files work.

## Provided content

- Prompt: [`../../prompts/02-context-required/osmos-remediate-schema-drift-in-existing-notebook-as-versioned.txt`](../../prompts/02-context-required/osmos-remediate-schema-drift-in-existing-notebook-as-versioned.txt)
- Presentation: [`../../presentation/Osmos_DFW_Fabric_User_Group.pptx`](../../presentation/Osmos_DFW_Fabric_User_Group.pptx)
- Recording: [YouTube](https://youtu.be/b5K9Eo41HrI?si=1WBMphbUmy21YpMp)

## Prepare separately

The source package does not include the notebook or test files. Prepare:

- A working original ingestion notebook.
- An original input file that succeeds.
- A new input file that:
  - adds a currency field;
  - renames the amount field;
  - contains at least one malformed timestamp; and
  - contains at least one null business key.
- Expected accepted/quarantined counts and reason codes for both files.
- A dedicated Fabric development workspace and target Lakehouse.

Commit or export the original notebook before the demo so its unchanged state can be proven afterward.

## Conversation sequence

This is a **context-required** prompt.

1. In turn 1, paste [`../../prompts/00-context/osmos-controlled-starter-prompt.txt`](../../prompts/00-context/osmos-controlled-starter-prompt.txt).
2. Provide the complete Fabric browser URL, exact workspace, exact Lakehouse, and identify the existing notebook and source-file locations.
3. Confirm that the first phase is diagnostic/read-only and that writes require approval.
4. In turn 2, paste the schema-drift prompt unchanged.
5. Require the expected-versus-actual schema comparison and root-cause explanation before approving edits.
6. Confirm the plan creates a versioned copy and does not overwrite the original notebook.

## Evidence to collect

- Expected and actual schema comparison.
- Root cause and explicit old-to-new field mapping.
- Versioned notebook name/path plus proof that the original is unchanged.
- Safe timestamp parsing and currency-field preservation.
- Accepted and quarantined counts for the original file.
- Accepted and quarantined counts for the changed file.
- Reason codes for null business keys and unparseable timestamps.
- Regression checks showing both old and new formats work.
- Rerun behavior and rollback instructions.

## Likely failure modes to intercept

- The agent guesses a rename without inspecting the files.
- It edits the original notebook instead of making a versioned copy.
- It drops invalid rows rather than quarantining them.
- It proves only the changed file and regresses the original format.
- It reports success without accepted/quarantined counts or sample reason codes.

## Success condition

The versioned notebook accepts both supported schemas, preserves the new currency information, quarantines bad records with clear reasons, passes regression checks, and leaves the original notebook untouched.
