# SayWhatTech — Organization Governance

> **New here?** Start with [ONBOARDING.md](ONBOARDING.md) for the full setup guide.

## Branch Protection

A single org-level ruleset protects the default branch (`main`) across **all repositories**.

**Ruleset:** "Protect main — all repos"
**Scope:** `~DEFAULT_BRANCH` on `~ALL` repos
**Enforcement:** Active

### Rules

| Rule | Effect |
|------|--------|
| Require pull request | All changes to `main` must go through a PR. No direct pushes. |
| 0 approvals required | PRs can be merged without reviewer approval (solo-dev workflow). |
| No deletion | Cannot delete the default branch. |
| No force-push | Cannot rewrite history on the default branch. |

### Bypass

| Role | Bypass |
|------|--------|
| Admin | Always |
| Maintainer | Always |
| All others | Never |

### How to view

```bash
# List org rulesets
gh api orgs/SayWhatTech/rulesets --jq '.[] | "\(.name) (\(.enforcement))"'

# View full ruleset details
gh api orgs/SayWhatTech/rulesets/<id>

# Check effective rules on a repo's main branch
gh api repos/SayWhatTech/<repo>/rules/branches/main
```

Or visit: https://github.com/organizations/SayWhatTech/settings/rules

### Changing the rules

Edit the org ruleset via API or the GitHub settings UI. Changes apply to all repos immediately. Do **not** create repo-level rulesets that duplicate org rules — keep everything in one place.

---

*Last updated: 2026-04-03*
