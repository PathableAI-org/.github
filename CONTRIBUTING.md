# Contributing to PathAble Projects

Thank you for your interest in contributing to PathAble's technical work.

PathAble builds accessible technology that advances disability employment,
empowerment, and inclusion. We welcome thoughtful technical participation,
especially from disabled people, practitioners, and others with relevant
lived or professional experience.

## Before You Contribute

Each repository has its own purpose, maturity, license, and contribution model.

Before opening an issue or pull request:

1. Read the repository's `README.md`.
2. Review any repository-specific contributing or agent instructions.
3. Confirm that the repository accepts the type of contribution you propose.
4. Check existing issues and pull requests for related work.
5. Discuss substantial changes with maintainers before implementation.

Access to a repository does not necessarily mean that it accepts unsolicited
contributions. Maintainers may decline work that does not fit current scope,
capacity, architecture, or priorities.

Repository-specific instructions take precedence over this organization-wide
guide.

Open source repositories that follow PathAble's public planning workflow
should also read [Open Source Operating Model](#open-source-operating-model)
below.

## Open Source Operating Model

PathAble open source projects default to public planning and public
implementation history. For these repositories, the project repository is the
operational source of truth for contributors and maintainers.

Internal systems may still hold company strategy, partnership context, and
early thinking. Once planning is ready to guide work, durable project artifacts
should live in or be mirrored to the public repository.

This section establishes shared expectations across PathAble open source
repositories. It does not replace repository-specific release docs, milestone
docs, contributor guides, or agent instructions.

### Public Documentation Locations

| Artifact | Location |
| --- | --- |
| Project overview | `README.md` |
| Vision and direction | `docs/vision/` |
| Release definitions | `docs/releases/<release>.md` |
| Milestone definitions | `docs/milestones/<milestone>.md` |
| Feature specs, plans, and tasks | `specs/` (Spec Kit) |
| Pending release notes | `.changeset/` |
| Implementation work | GitHub Issues |
| Vertical slice tracking | GitHub Milestones |
| Shipped release summaries | GitHub Releases |

Release and milestone markdown files are the public planning contract for a
project. Organization-wide templates for creating those documents live in the
[PathableAI-org/.github](https://github.com/PathableAI-org/.github)
repository under `templates/docs/releases/` and `templates/docs/milestones/`.
Each project repository stores its own release and milestone documents.

### Planning Hierarchy

Open source work should be traceable through a linked hierarchy of artifacts.
Each level answers a different question:

- **Release** — What capability will exist when this release ships?
- **Milestone** — What is the smallest demoable product capability we are
  building next?
- **Feature spec** — What specific behavior are we implementing to support
  this milestone?
- **Plan and tasks** — How will this spec be implemented, and what work must
  be done?
- **Issues** — What concrete work remains?
- **Pull requests** — What change is being proposed to the repository?

The intended workflow is:

```text
Release definition
  -> Milestone definition
    -> GitHub Milestone
      -> Spec Kit setup issue
        -> Spec Kit spec / plan / tasks
          -> GitHub Issues
            -> PRs
              -> Changesets
                -> Changesets CI / Version Packages PR
                  -> GitHub Release
```

Release and milestone markdown files carry the planning intent. GitHub
Milestones are operational trackers that link issues back to those documents.
They are not a substitute for milestone definitions.

### Releases and Milestones

A planned release should be defined first as a markdown file at
`docs/releases/<release>.md`. The release definition is the public contract for
what the release will deliver. It should capture the release goal, scope,
success criteria, and the vertical slice milestone list.

A milestone is a demoable vertical slice of product capability, not merely a
calendar checkpoint. Each milestone should be defined at
`docs/milestones/<milestone>.md` and should include:

- A demo goal and expected demonstration
- User-visible or agent-visible behavior
- Acceptance criteria framed in terms of the demo
- Scope and out-of-scope boundaries
- An `Inputs to Spec Kit` section

The `Inputs to Spec Kit` section is the canonical source material for
`/speckit.specify`. The rest of the milestone document provides supporting
context.

Each GitHub Milestone should correspond to one milestone document. The GitHub
Milestone description should link to that document and to the relevant release
definition.

To create consistent release and milestone documents, copy the organization-wide
templates from
[`templates/docs/releases/release-template.md`](https://github.com/PathableAI-org/.github/blob/main/templates/docs/releases/release-template.md)
and
[`templates/docs/milestones/milestone-template.md`](https://github.com/PathableAI-org/.github/blob/main/templates/docs/milestones/milestone-template.md).

### Spec Kit and GitHub Issues

Spec Kit turns a planned milestone requirement into implementation-ready
artifacts. Feature specs, plans, and tasks live under `specs/`.

Every milestone should begin with a setup issue:

```text
Create Spec Kit spec, plan, and tasks for <milestone>
```

No implementation issues should be created for a milestone until its Spec Kit
feature spec, implementation plan, and task breakdown exist.

The setup issue should:

1. Read the release definition.
2. Read the milestone definition.
3. Use the milestone document's `Inputs to Spec Kit` section as the canonical
   source for `/speckit.specify`.
4. Produce or update the Spec Kit feature spec, implementation plan, and task
   list.
5. Create GitHub Issues from the generated tasks.

Implementation issues should link to the release definition, milestone
document, GitHub Milestone, and relevant Spec Kit spec when possible.

Use the organization-wide
[Spec Kit setup issue template](.github/ISSUE_TEMPLATE/spec_kit_setup.yml)
when opening the first issue for a GitHub Milestone.

### Pull Request Traceability

Pull requests should make the planning chain visible to reviewers. When
applicable, link:

- The GitHub issue being implemented
- The relevant Spec Kit spec, plan, or task
- The milestone document
- The release definition
- The GitHub Milestone

Use the organization-wide
[pull request template](.github/PULL_REQUEST_TEMPLATE.md) to record these
links and related verification details.

Not every pull request implements Spec Kit work. Documentation, process, and
infrastructure changes are valid contributions. When a pull request does not
implement tracked feature work, say so in the pull request description.

### Changesets

Changesets connect implementation work to release communication. Add a changeset
in your pull request when the change should appear in package release notes or
other user-facing release communication.

Changeset-worthy changes include:

- CLI commands added, removed, or changed
- Public APIs, schemas, or storage formats changed
- MCP resources or tools added, removed, or changed
- Validation or protocol behavior changed in a user-visible way
- Documentation changes that affect usage expectations

Usually not changeset-worthy:

- Internal-only refactors with no behavior change
- Test-only changes
- CI-only changes that do not affect published behavior

Write changesets in the pull request that introduces the change. Do not
reconstruct them at the end of a release.

During normal development on `main`, changesets accumulate until Changesets CI
opens or updates a Version Packages PR. Prerelease mode belongs on `release/*`
branches when a project is ready to publish installable prerelease packages,
not on `main`.

### Branching Expectations

Unless a repository specifies otherwise:

- **Feature branches** implement GitHub Issues and merge into `main`.
- **`main`** is the stable integration branch. It accumulates reviewed work and
  pending changesets. Do not enter Changesets prerelease mode on `main`.
- **`release/<name>`** branches handle publishing mechanics, such as
  `release/alpha` or `release/v0.1`.

A GitHub Milestone tracks a demoable vertical slice. A release branch handles
package publishing. Completing a milestone does not necessarily mean a package
has been published or a GitHub Release has been created.

### Proposing Workflow Improvements

To propose changes to this operating model, use the organization-wide
[workflow and process improvement issue template](.github/ISSUE_TEMPLATE/workflow_process_improvement.yml).

Use the
[feature request](.github/ISSUE_TEMPLATE/feature_request.yml) or
[bug report](.github/ISSUE_TEMPLATE/bug_report.yml) templates for product
features, defects, and accessibility issues instead.

Changes that affect organization-wide defaults belong in the
[PathableAI-org/.github](https://github.com/PathableAI-org/.github)
repository. Repository-specific workflow changes belong in the affected project
repository.

## Privacy and Sensitive Information

Never include any of the following in source code, tests, examples,
documentation, issues, pull requests, commits, screenshots, or logs:

- Protected health information or real participant information
- Customer, partner, or employee information
- Production data or realistic copies of production records
- Credentials, tokens, private keys, or secrets
- Private endpoints or confidential architecture details
- Security vulnerabilities or exploit details

Use clearly synthetic names and data in all examples.

If you accidentally disclose sensitive information, stop sharing it and notify
a repository maintainer privately. Do not repeat the information in another
issue or pull request.

Security concerns must follow the reporting instructions in the affected
repository. Do not report vulnerabilities through a public issue.

## Accessibility

Contributions should preserve or improve accessibility.

When relevant:

- Use semantic structures and familiar interaction patterns.
- Support keyboard and assistive-technology use.
- Provide meaningful labels, names, instructions, and alternative text.
- Do not rely on color alone to communicate meaning.
- Consider cognitive accessibility and plain-language content.
- Test loading, empty, error, validation, and responsive states.
- Document known accessibility limitations.

Avoid claiming conformance with a standard unless the contribution has
received the required review and testing.

## Making a Change

Unless a repository specifies another workflow:

1. Start from the repository's current default branch.
2. Create a focused branch for one coherent change.
3. Follow local architecture, formatting, and naming conventions.
4. Add or update tests in proportion to the change's risk.
5. Update relevant documentation.
6. Run the repository's required checks.
7. Open a pull request describing the change and its verification.

Keep changes narrowly scoped. Do not combine unrelated cleanup or refactoring
with the requested work without prior agreement.

## Pull Requests

A pull request should explain:

- The problem or need being addressed
- The proposed approach
- User, workflow, or operational effects
- Privacy, security, and accessibility implications
- Tests and manual verification performed
- Known limitations or follow-up work

Use synthetic data in screenshots and examples. Draft pull requests are
welcome when early feedback would prevent wasted work.

Opening a pull request does not guarantee acceptance. Maintainers may request
changes, defer the work, or close it based on scope, risk, capacity, or project
direction.

## AI-Assisted Contributions

AI tools may assist with a contribution, but the contributor remains
responsible for the result.

Contributors must:

- Review and understand submitted changes.
- Verify generated claims, code, tests, and documentation.
- Ensure prompts, outputs, and tool logs contain no sensitive information.
- Follow repository-specific disclosure or provenance requirements.
- Be able to explain and revise the contribution during review.

## Conduct

Participation in PathAble projects is governed by the organization
`CODE_OF_CONDUCT.md` when published, along with any repository-specific rules.

## Licensing

By submitting a contribution, you agree that it may be distributed under the
license identified by the repository. Do not submit code, content, data, or
assets that you do not have the right to contribute.

If a repository does not yet identify a license, ask the maintainers before
submitting work intended for public reuse.

## Questions

Use the repository's documented discussion or issue channel for ordinary
contribution questions. Do not use public channels for security concerns,
personal information, customer information, or protected health information.
