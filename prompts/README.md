# Prompt library

The original prompt files are stored unchanged and grouped by **conversation entry pattern**, not by topic. This distinction is required to reproduce the demos reliably.

## Folder map

### [`00-context/`](00-context/)

Reusable context setter:

- `osmos-controlled-starter-prompt.txt` — instructs the assistant to use Project Osmos, confirm the full Fabric target, expose the plan and validation approach, keep approvals visible, and resume an existing `.dataprojects` task when applicable.

### [`01-osmos-explicit/`](01-osmos-explicit/)

These prompts name Project Osmos themselves and can begin the task conversation:

| Prompt | Scenario | Additional preparation |
|---|---|---|
| `osmos-create-employee-benefits-agency-ontology.txt` | Create an employee-benefits agency ontology. | Verify the named `OsmosInsurance_Jenn` Lakehouse and `benefits` schema exist or intentionally replace them. |
| `osmos-get-sharepoint-utlization-from-purview-incremental-static-site.txt` | Build a fixed-window SharePoint audit notebook. | Replace/verify the tenant-specific site prefix; configure Key Vault and allowed operations. |
| `osmos-medallion-architecture-claims-analysis-using-synthetic-file-data-.txt` | Build the presentation's synthetic claims Bronze/Silver/Gold pattern. | Provide four synthetic CSVs and a target workspace/Lakehouse. |
| `osmos-synthetic-benefits-policy-book-of-business-end-to-end.txt` | Build a broad synthetic benefits policy platform. | Use a sandbox; review the large artifact scope before approving writes. |

Even when Osmos is explicit, confirm the exact full Fabric URL, workspace, Lakehouse, read/write boundary, planned artifacts, and validation before execution.

### [`02-context-required/`](02-context-required/)

These files do not repeat the instruction to use Project Osmos. Send them only after the earlier context turn has established Project Osmos and the target workspace/Lakehouse.

| Prompt | Scenario | Context/dependency to verify |
|---|---|---|
| `osmos-build-enhanced-billing-process.txt` | Metadata-driven PRE_BILL, COMPUTE, and POST_BILL lifecycle. | “This Lakehouse” must already resolve to the confirmed target. |
| `osmos-build-gateway-admin-solution.txt` | Gateway governance, monitoring, runbooks, and dashboard specification. | Review the embedded `.dataprojects/<id>/` target before reuse. |
| `osmos-configure-existing-benefits-policy-data-agent.txt` | Reconcile and configure an existing benefits data agent. | The named agent and verified workspace/Lakehouse sources must already exist. |
| `osmos-create-adventureworks-staging-table.txt` | Build and validate `CustomerSalesSummary`. | Required AdventureWorks tables must exist in the confirmed Lakehouse. |
| `osmos-explore-sample-lakehouse-and-create-improvement-plan.txt` | Read-only exploration and safe quality plan. | Identify the specific sample table; keep the first pass read-only. |
| `osmos-get-sharepoint-utlization-from-purview-incremental.txt` | Production-style incremental Purview/Office 365 audit framework. | Verify site prefixes, variable library, Key Vault, API permissions, control tables, execution mode, and target table. |
| `osmos-remediate-schema-drift-in-existing-notebook-as-versioned.txt` | Diagnose drift, preserve the original, create a versioned remediation, and test old/new files. | Existing notebook plus original and changed source files must be present. |

## Exact two-turn flow for context-required prompts

### Turn 1 — route to Osmos and bind the target

Paste [`00-context/osmos-controlled-starter-prompt.txt`](00-context/osmos-controlled-starter-prompt.txt), then provide:

```text
Full Fabric browser URL: <complete URL>
Target workspace: <exact workspace name>
Target Lakehouse: <exact Lakehouse name>
Expected mode: <read-only | write-capable after plan approval>
```

Do not proceed until the assistant confirms the same workspace and Lakehouse and explains its planned artifacts, write boundaries, and validation.

### Turn 2 — paste the task prompt unchanged

Paste one file from [`02-context-required/`](02-context-required/). Do not assume the task prompt alone will preserve routing or target context in a new conversation.

## Run record template

For each reproduction, retain:

```text
Date/time:
Presenter/operator:
Tool and version:
Tenant/environment:
Full Fabric URL (redact before public sharing):
Workspace:
Lakehouse:
Prompt file and commit:
Conversation pattern: Osmos-explicit | context-required
Task/checkpoint identifier:
Approved plan:
Created/updated artifacts:
Validation performed:
Observed counts/totals/exceptions:
Rerun result:
Capacity observations:
Open issues:
Reset/rollback steps:
```

## Public-repository review

The source files intentionally remain unchanged. Before publishing or running them elsewhere, review tenant-specific URLs, Lakehouse/schema names, `.dataprojects` IDs, company context, API scopes, table/path identifiers, and any embedded assumptions. Never commit secrets or completed run records containing sensitive URLs or identifiers.
