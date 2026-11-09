# Publishing and reuse checklist

Complete this review before publishing the repository publicly, presenting from a new tenant, or running a prompt in another environment.

## Rights and repository metadata

- [ ] Confirm you have permission to publish the PowerPoint, HTML, prompt files, presenter name, screenshots, branding, and linked resources.
- [ ] Choose and add an appropriate `LICENSE`; none was supplied with the source package.
- [ ] Add owner/contact, contribution, support, and code-of-conduct information if this becomes a maintained public project.
- [ ] Keep the YouTube content as a link unless redistribution rights explicitly allow another approach.

## Organization-specific content

- [ ] Review the SharePoint site prefix in both Purview prompt files.
- [ ] Review the named `OsmosInsurance_Jenn` Lakehouse and `benefits` schema.
- [ ] Review the `.dataprojects/8c65fe41-4494-4226-b006-d7aed652f03b/` path in the gateway prompt.
- [ ] Review presenter/user names and organization/path examples in the PowerPoint and HTML.
- [ ] Redact full Fabric browser URLs, workspace IDs, item IDs, tenant IDs, task IDs, and screenshots from committed run records.

## Security and configuration

- [ ] Scan the complete repository and commit history for secrets, tokens, connection strings, tenant details, client IDs, client secrets, Key Vault values, and credentials.
- [ ] Keep secrets in approved secret stores; never convert the Key Vault references in the prompts into committed literal values.
- [ ] Validate Office 365 Management Activity API permissions and least-privilege identity design.
- [ ] Review table/path identifiers and any configuration-driven SQL/Spark operations for injection or unsafe path handling.
- [ ] Use synthetic data for public demonstrations.

## Product and operational accuracy

- [ ] Recheck Project Osmos preview availability, supported regions/capacities, permissions, and current documentation.
- [ ] Recheck Copilot CLI/plugin and Fabric Skills installation commands.
- [ ] Review [microsoft/skills-for-fabric](https://github.com/microsoft/skills-for-fabric) for current guidance.
- [ ] Test every relative repository link after publishing.
- [ ] Run the HTML locally and verify checklist, copy, reset, print, and external links.
- [ ] Open the PowerPoint on the presentation device and verify formatting.
- [ ] Dry-run each demo in a dedicated development workspace and record reset/rollback steps.

## Evidence

- [ ] Record source checksums and compare them to [`source-inventory.md`](source-inventory.md).
- [ ] Tag the repository version used for each presentation.
- [ ] Retain prompts, approvals, artifact inventory, validation results, rerun evidence, known issues, and capacity observations.
