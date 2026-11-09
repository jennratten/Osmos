# Presentation

## File

- [`Osmos_DFW_Fabric_User_Group.pptx`](Osmos_DFW_Fabric_User_Group.pptx) — 36-slide presentation for the Dallas–Fort Worth Fabric and Power BI User Group.

## How to use the deck

1. Open the PowerPoint file in Microsoft PowerPoint. Use desktop PowerPoint when presenting so layout, fonts, and transitions are rendered consistently.
2. Review the prerequisite and setup material before attempting a demo. The deck emphasizes exact workspace/Lakehouse targeting, a clean tool context, interactive approvals, and validation.
3. Use the demo section together with the matching runbooks:
   - [Synthetic claims medallion](../demos/01-synthetic-claims-medallion/)
   - [Schema drift and quarantine](../demos/02-schema-drift-and-quarantine/)
   - [Incremental sales load](../demos/03-incremental-sales-load/)
4. Use the economics, best-practices, prompt-anatomy, security, and adoption slides as the operating guardrails around the live demonstrations.
5. Recheck links and preview-era product claims before each presentation.

## Suggested presentation sequence

- **Concept:** Explain the contract → plan → execution → checkpoint → evidence model.
- **Positioning:** Contrast inline assistance with a persistent, bounded Osmos engineering task.
- **Readiness:** Confirm the exact target, identity, permissions, capacity, Lakehouse, tools, and approval model.
- **Demo:** Run one scenario live, keep one abbreviated, and retain one as a discussion backup.
- **Proof:** Show artifacts, validation results, exceptions, rerun behavior, and handoff notes—not only generated code.
- **Operations:** Close with capacity observation, security, governance, versioning, and human accountability.

## Reproduction caveat

The PowerPoint describes required inputs and pre-existing artifacts, but the attached package does not include all CSVs, notebooks, or Fabric items used by the three demos. See each runbook for the preparation boundary.
