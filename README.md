# Project Osmos demo kit

A ready-to-publish repository structure for the Project Osmos presentation, recorded session, VS Code setup job aid, and reusable demo prompts.

## What is included

| Path | Purpose |
|---|---|
| [`presentation/`](presentation/) | The original PowerPoint deck and presentation guidance. |
| [`video/`](video/) | A stable pointer to the hosted YouTube recording. The video is not duplicated in the repository. |
| [`setup/vscode/`](setup/vscode/) | The standalone HTML setup job aid and instructions for downloading, opening, and using it. |
| [`prompts/`](prompts/) | Original prompt files, separated by how Project Osmos context is established. |
| [`demos/`](demos/) | Reproduction runbooks for the three demo patterns in the presentation. |
| [`docs/`](docs/) | Source inventory and checks to complete before publishing or presenting. |

## Recommended learning path

1. Review [`presentation/Osmos_DFW_Fabric_User_Group.pptx`](presentation/Osmos_DFW_Fabric_User_Group.pptx) or watch the [recorded session](https://youtu.be/b5K9Eo41HrI?si=1WBMphbUmy21YpMp).
2. Follow the [`setup/vscode/README.md`](setup/vscode/README.md) and open the HTML job aid locally.
3. Confirm access to Project Osmos, a Fabric workspace on supported capacity, a target Lakehouse, the required identity/permissions, GitHub Copilot CLI, and Microsoft Fabric Skills.
4. Choose the correct prompt flow in [`prompts/README.md`](prompts/README.md):
   - **Osmos-explicit prompts** invoke Project Osmos in the prompt itself.
   - **Context-required prompts** must be sent only after a separate turn establishes Project Osmos, the full Fabric URL, the target workspace, and the target Lakehouse.
5. Reproduce a presentation scenario with the runbooks under [`demos/`](demos/).
6. Preserve the prompt, plan, approvals, generated artifacts, validation evidence, task/checkpoint information, and reset notes for each run.

## Two supported conversation patterns

### Pattern A — Project Osmos is explicit in the task prompt

Use a prompt from [`prompts/01-osmos-explicit/`](prompts/01-osmos-explicit/). Paste the file as the first task turn. If the prompt does not contain an exact target URL, supply the full Fabric browser URL and confirm the workspace and Lakehouse before approving writes.

### Pattern B — Project Osmos context was established earlier

Prompts under [`prompts/02-context-required/`](prompts/02-context-required/) intentionally do **not** repeat “Use Project Osmos.” Reproduce the original sequence rather than pasting these into a new, unprepared chat:

**Turn 1 — establish routing and target**

```text
Use Project Osmos for this Microsoft Fabric data engineering task.
Use Microsoft Fabric Skills for Fabric-specific APIs and conventions.

Full Fabric browser URL: <paste the complete target URL>
Target workspace: <workspace name>
Target Lakehouse: <Lakehouse name>

Treat the task as read-only until you show the plan, expected artifacts,
validation approach, and write boundaries. Ask before changing Fabric artifacts.
If a matching task already exists in .dataprojects, resume it instead of
creating a duplicate.
```

Confirm that the assistant identifies the intended workspace/Lakehouse and the correct read/write boundary.

**Turn 2 — send the task prompt**

Paste one unchanged file from [`prompts/02-context-required/`](prompts/02-context-required/). Keeping the context and task in separate turns reproduces how these prompts were originally used.

## Reproduction discipline

- Use a dedicated development workspace and synthetic or representative data.
- Start read-only; inspect and approve the plan before write-capable actions.
- Do not paste secrets, tokens, client secrets, or connection credentials into chat or source control.
- Replace or verify tenant-specific URLs, Lakehouse names, paths, table names, and `.dataprojects` identifiers before execution.
- Keep approvals interactive; do not enable broad auto-approval for a demo.
- Validate outputs against the prompt’s acceptance criteria, then rerun to prove idempotency when required.
- Never treat generated code or a successful run as sufficient proof; retain reconciliation, exception, row-count, and amount checks.

## Important scope notes

- The source package contains prompts and guidance, but it does not contain all demo input data or pre-existing Fabric artifacts. Each demo runbook lists what must be prepared separately.
- The incremental sales demo is described in the presentation, but no dedicated text prompt for that demo was attached. Its runbook includes a clearly labeled prompt reconstructed from the deck’s requirements.
- Source filenames are preserved verbatim, including the original `utlization` spelling and trailing hyphen in one filename, to keep links and checksums stable.
- Project Osmos is described as preview functionality in the deck. Recheck current service documentation, tenant availability, and supported capabilities before each session.

## Related resources

- [Recorded Project Osmos session](https://youtu.be/b5K9Eo41HrI?si=1WBMphbUmy21YpMp)
- [Microsoft Skills for Fabric](https://github.com/microsoft/skills-for-fabric)
- [Project Osmos](https://github.com/microsoft/project-osmos)

## Repository publishing

No license was included with the source materials, so this kit does not select one on the owner's behalf. Before making the repository public, complete [`docs/publishing-checklist.md`](docs/publishing-checklist.md), choose an appropriate license, and review all content for organization-specific information.
