# PathAble organization configuration

This public repository manages PathAble's GitHub organization profile and shared GitHub community files.

Its root README is written for maintainers. The public-facing organization profile is maintained separately in [`profile/README.md`](profile/README.md).

## What this repository controls

| Path | Purpose | Effect |
|---|---|---|
| `profile/README.md` | Public organization profile | Displayed on the PathAble GitHub organization page |
| `README.md` | Maintainer documentation | Displayed on this repository |
| `CODE_OF_CONDUCT.md` | Community expectations | May become the default for repositories without their own version |
| `CONTRIBUTING.md` | Contribution guidance | May become the default for repositories without their own version |
| `SECURITY.md` | Vulnerability reporting | May become the default for repositories without their own version |
| `SUPPORT.md` | Support boundaries | May become the default for repositories without their own version |
| `.github/ISSUE_TEMPLATE/` | Issue forms and templates | May be offered across repositories without local templates |
| `.github/PULL_REQUEST_TEMPLATE.md` | Pull request guidance | May become the default where no local template exists |
| `workflow-templates/` | Reusable GitHub Actions workflows | Available to repositories in the organization |

## Organization-wide defaults

Files added here can affect repositories throughout the PathAble organization.

Before adding or changing a shared default:

1. Confirm which repositories may inherit the change.
2. Check whether specialized repositories need their own version.
3. Keep instructions applicable across languages and project types.
4. Avoid assumptions about a specific product, customer, or deployment environment.
5. Document exceptions and ownership.
6. Use a pull request so the organization-wide impact can be reviewed.

Repository-specific guidance always takes precedence over defaults from this repository.

## Review expectations

Changes should be reviewed for:

- Organization-wide impact
- Technical accuracy
- Accessibility
- Brand and editorial consistency
- Privacy and security implications
- Contributor clarity
- Ongoing maintenance requirements

Public-facing copy should receive brand or communications review. Security-sensitive guidance should receive engineering or security review.

## Brand guidance

PathAble is the umbrella identity for the organization. Until the product and software sub-brand is formally approved, use **Engineering at PathAble** as a descriptive label rather than presenting it as a separate company or finalized brand.

Public GitHub materials should reflect these principles:

- Build practical tools around real disability-service workflows.
- Augment people rather than replace judgment or relationships.
- Treat accessibility as infrastructure.
- Preserve human agency and meaningful control.
- Be candid about limitations, uncertainty, and project maturity.
- Connect technical work to PathAble's disability-services mission.

Do not create new logo arrangements, colors, taglines, or sub-brand names without approval.

## Privacy and security

This repository and its inherited files are public.

Never include:

- Protected health information
- Participant or customer information
- Credentials, secrets, or private endpoints
- Confidential architecture or security details
- Production data
- Unsupported security, accessibility, or compliance claims

Examples must use synthetic data. Security vulnerabilities should be reported through the applicable `SECURITY.md` process rather than a public issue.

## Related repositories

- [PathAble engineering publication](https://github.com/PathableAI-org/PathableAI-org.github.io)
- [PathAble organization profile source](profile/README.md)

## Source guidance

- [PathAble website](https://pathableai.com/)
- [PathAble on LinkedIn](https://www.linkedin.com/company/pathable-ai/)
- [PathAble visual guidelines](https://drive.google.com/file/d/1lHd9C5R7uEKiP8DxnRzBrP8iVXPvIzJd/view)
- [Draft technology and engineering identity plan](https://app.notion.com/p/3857cbd04b6d81f0afcdf8cddfb9def2)

## Maintenance status

This repository is under active development. Shared files should be introduced incrementally, with explicit ownership and review, as PathAble's public engineering practice matures.
