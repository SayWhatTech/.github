# SayWhatTech — New Engineer Onboarding

Welcome to SayWhatTech. This doc gets you from zero to shipping.

---

## What We Build

SayWhatTech builds **HOA (homeowner association) document management** and **developer tooling**. Our core product, SayWhat, transforms complex governing documents into clear, searchable, AI-powered answers for boards, residents, and property managers.

---

## Repo Inventory

| Repo | Type | Language | Version | Description |
|------|------|----------|---------|-------------|
| `saywhat` | Deployable (monorepo) | Python + TypeScript | API 0.2.63, Web 0.2.69 | HOA document repository and query system. FastAPI backend, Next.js frontend, Caddy proxy. Deployed on AWS EC2 via Docker Compose. |
| `devdash` | Deployable | TypeScript | 1.0.0 | Developer progress dashboard — GitHub project analytics. Next.js, Prisma, recharts. Deployed on AWS EC2. |
| `claude-plugins` | Library | Markdown | — | Org-wide Claude Code plugin marketplace. Shared workflow skills. |
| `.github` | Documentation | — | — | Org profile, governance, onboarding. |
| `mermaidpointehoa-demo-website` | Static site | HTML | — | Demo website for Mermaid Pointe HOA. |

---

## Dev Environment Setup

### 1. GitHub Access

- Get added to the [SayWhatTech](https://github.com/SayWhatTech) org
- Clone the repos you'll be working on
- Review [GOVERNANCE.md](GOVERNANCE.md) for branch protection rules

### 2. AWS Credentials

- Request IAM access for the environments you need
- Credentials and secrets are stored in **SSM Parameter Store** under `/<app>/<env>/`
- Terraform state lives in per-app S3 buckets (`<app>-terraform-state`)

### 3. Cursor IDE

- Install [Cursor](https://cursor.com/) as your primary editor
- Install these extensions:
  - **Peacock** — color-code each Cursor window so you can tell multiple instances apart at a glance
  - **Markdown Preview Enhanced** — preview Markdown files with full Mermaid diagram support

### 4. Claude Code + Plugins

- Install [Claude Code](https://claude.ai/code)
- Install org plugins from `SayWhatTech/claude-plugins`
- Each repo has its own `CLAUDE.md` with repo-specific context — Claude Code reads these automatically

---

## Development Workflow

The standard cycle uses skills from the Claude Code plugin marketplace:

1. **`/scaffold`** — Bootstrap a new repo with standard structure, CLAUDE.md, CI, and infra templates
2. **`/start-feature`** — Create a feature branch, link to an issue, set up the working context
3. **`/implement`** — Build the feature with guided implementation
4. **`/review-feature`** — Self-review, run checks, prepare PR for merge

All changes go through pull requests. Direct pushes to `main` are blocked org-wide (see [GOVERNANCE.md](GOVERNANCE.md)).

---

## Key Documents

| Document | Location | Purpose |
|----------|----------|---------|
| [GOVERNANCE.md](GOVERNANCE.md) | `.github` | Branch protection, merge rules, org policies |
| [ARCHITECTURE.md](ARCHITECTURE.md) | `.github` | How repos and infrastructure fit together |
| [CLAUDE.md](CLAUDE.md) | `.github` | Org-level Claude Code context and conventions |
| `CLAUDE.md` | Each repo | Repo-specific Claude Code context |

---

*Last updated: 2026-04-03*
