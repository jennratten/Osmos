# Project Osmos + Fabric Skills setup job aid

## Download the HTML

You need the actual `.html` file, not a browser preview of its source.

### From the repository page

1. Open [`project_osmos_fabric_skills_setup.html`](project_osmos_fabric_skills_setup.html).
2. Select **Download raw file** (or **Raw**, then save the page).
3. Save the file with the exact `.html` extension. If the browser appends `.txt`, rename it to `project_osmos_fabric_skills_setup.html`.

### From a repository ZIP

1. Download the repository ZIP.
2. Extract the ZIP; do not try to run the HTML from inside the compressed archive.
3. Browse to `setup/vscode/project_osmos_fabric_skills_setup.html`.

### From Git

```powershell
git clone <repository-url>
cd <repository-folder>\setup\vscode
```

## View it locally

1. Double-click `project_osmos_fabric_skills_setup.html`, or right-click it and choose **Open with** → Microsoft Edge, Google Chrome, or Firefox.
2. The address bar should show a local `file:///.../project_osmos_fabric_skills_setup.html` path.
3. No web server, package installation, build step, or VS Code extension is required to display the job aid.

The file contains its CSS and JavaScript inline and does not fetch a runtime framework. Internet access is still required to follow external references, install software/plugins, authenticate, and access Microsoft Fabric.

## Use it as a standalone tool

Work from the top down:

1. Confirm account, capacity, workspace, Lakehouse, permission, and organizational-policy prerequisites.
2. Install and verify the required software.
3. Install `ripgrep` and reopen PowerShell so later processes inherit the updated environment.
4. Create the clean VS Code profile described by the job aid.
5. Authenticate to GitHub Copilot and Azure with the intended identity/tenant.
6. Install Project Osmos and Fabric Skills from the approved marketplaces.
7. Apply the recommended settings, launch Copilot CLI from the dedicated workspace, and run the readiness checks.
8. Use the controlled first prompt before any context-dependent task prompt.

### Interactive behavior

- Checkboxes update the completion bar.
- Progress is saved in the browser's local storage for that local file/browser profile.
- **Reset checklist** clears saved checkbox state.
- **Copy** buttons copy command blocks. A browser may restrict clipboard access for a `file:///` page; if so, select and copy the command text manually.
- **Print or save as PDF** creates a portable, non-interactive copy for reference.

Keep the original HTML as the canonical interactive tool. A printed/PDF copy will not retain checkboxes, progress storage, reset behavior, or copy buttons.

## Microsoft Skills for Fabric

The job aid installs the Fabric Skills collection used with Project Osmos. Review the source repository and current instructions before each setup:

- [microsoft/skills-for-fabric](https://github.com/microsoft/skills-for-fabric) — Microsoft Fabric skills and MCP systems for CLI, VS Code, and supported coding assistants.

The job aid also links to Microsoft's current Skills for Fabric installation documentation. If commands in the local HTML differ from current official guidance, use the current official instructions and record the change in the demo notes.

## Safety notes

- Keep approvals interactive.
- Use the intended Microsoft Entra tenant and verify the target Fabric workspace before proceeding.
- Never place secrets or tokens in the HTML, prompt files, terminal history committed to Git, or screenshots.
- The setup steps are Windows-oriented. Adapt paths and package-management commands deliberately for other operating systems.
