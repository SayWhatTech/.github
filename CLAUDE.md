# CLAUDE.md — SayWhatTech Organization

This is the SayWhatTech organization meta-repo (`.github`). It holds org-level documentation, governance, and the public org profile.

## Conventions

- **Branch protection**: All repos enforce PR-based workflow on `main`. No direct pushes. See [GOVERNANCE.md](GOVERNANCE.md).
- **Commit format**: Reference issues with `[#N]` in commit messages (e.g., `Fix upload timeout [#42]`).
- **PR-based workflow**: All changes go through pull requests. 0 approvals required (solo-dev workflow), but PRs are mandatory for traceability.

## Claude Code Plugin Marketplace

Shared skills live at **SayWhatTech/claude-plugins**. Skills are organized in three layers:

| Layer | Scope | Examples |
|-------|-------|---------|
| Layer 0 | Scaffold | `/scaffold` — bootstrap new repos with standard structure, CLAUDE.md, CI, infra templates |
| Layer 1 | Generic workflow | `/start-feature`, `/implement`, `/review-feature` — work across any repo |
| Layer 2 | Repo-specific | Custom skills defined in individual repo CLAUDE.md files |

## Creating New Repos

When creating a new repository in the SayWhatTech org:

1. Use `/scaffold` from the plugin marketplace — it generates the standard repo structure
2. The scaffold creates a `CLAUDE.md` with standard sections (conventions, architecture, deployment)
3. Add repo-specific Terraform config under `infra/terraform/`
4. Set up SSM parameters under `/<app>/<env>/`

## Key Documents in This Repo

- [ONBOARDING.md](ONBOARDING.md) — New engineer start-here guide
- [GOVERNANCE.md](GOVERNANCE.md) — Branch protection and org policies
- [ARCHITECTURE.md](ARCHITECTURE.md) — How repos and infrastructure connect
- [profile/README.md](profile/README.md) — Public org profile on GitHub
