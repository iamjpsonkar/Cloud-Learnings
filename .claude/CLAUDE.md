# Cloud-Learnings — Claude Project Context

This file gives Claude Code complete project context for the Cloud-Learnings repository.
Read this before doing any work. It is the fastest path to correct context.

---

## Project Identity

| | |
|---|---|
| **Repo** | https://github.com/iamjpsonkar/Cloud-Learnings.git |
| **Local path** | `/Users/jsonkar/iamjpsonkar/AWS-Learnings` (directory name kept from before rename) |
| **Branch** | `main` (single-branch workflow) |
| **Purpose** | Comprehensive cloud engineering knowledge base — beginner to advanced — covering AWS, Azure, GCP, Kubernetes, Terraform, CI/CD, SRE, security, FinOps, and more |
| **Migration history** | Originally `aws-learnings` (AWS-only). Renamed and expanded to Cloud-Learnings. All old AWS-only branding replaced. |

---

## Current State (as of last update)

All content is complete. Do NOT regenerate files that already exist unless the user asks.

| Area | Status | Key commit |
|------|--------|-----------|
| Documentation (00-foundations → 28-references) | **All 29 directories complete** | multiple batches |
| `docker/` lab platform (297 files, 14 profiles, 19 labs) | **Complete** | `e35697a` |
| `40-local-cloud-lab-platform/` (FastAPI + React + Makefile) | **Complete** | `738e09f` |
| `assets/` (images, diagrams, attributions) | Complete | — |
| `scripts/` (validate-repo.sh, etc.) | Complete | — |
| `templates/` | Complete | — |
| `.github/` (workflows, issue templates, PR template) | Complete | — |

**Before starting any task:** run `git log --oneline -10` and `git status` to confirm current state.

---

## Prompt Files

Three specialized prompt files live at `/Users/jsonkar/iamjpsonkar/` (outside the repo):

| File | Purpose |
|------|---------|
| `cloud_prompt_master.md` | Master orchestration prompt — repo structure, conventions, coordinates the other two |
| `cloud_prompt_documentation.md` | Documentation generation prompt — generates/extends Markdown docs in 00–28 directories |
| `cloud_prompt_docker.md` | Docker lab platform prompt — extends/rebuilds the `docker/` directory |

Use the appropriate sub-prompt when doing large-scale generation tasks.

---

## Repository Structure

```
Cloud-Learnings/
├── README.md                     ← main nav index; Quick Start + structure table + learning paths
├── CONTRIBUTING.md
├── LICENSE                       ← MIT
├── CODE_OF_CONDUCT.md
├── SECURITY.md
├── CHANGELOG.md
├── .gitignore
├── .claude/
│   └── CLAUDE.md                 ← this file
├── .github/
│   ├── workflows/validate-links.yml
│   ├── workflows/lint-markdown.yml
│   ├── ISSUE_TEMPLATE/
│   └── PULL_REQUEST_TEMPLATE.md
├── assets/
│   ├── ATTRIBUTIONS.md
│   └── images/aws/{aws,ec2,s3,dns}/  ← 30 images
├── scripts/
│   ├── validate-repo.sh          ← repo health checker
│   ├── generate-mermaid-diagrams.sh
│   ├── optimize-images.sh
│   ├── download-assets.sh
│   └── check-missing-topics.py
├── templates/
│   ├── service-template.md
│   ├── command-template.md
│   ├── troubleshooting-template.md
│   ├── project-template.md
│   ├── architecture-template.md
│   ├── comparison-template.md
│   └── checklist-template.md
│
│  ── 29 Documentation Directories ──────────────────────────────────────
│
├── 00-foundations/               ← cloud concepts, IaaS/PaaS/SaaS, shared responsibility
├── 01-cloud-fundamentals/        ← cross-cloud compute, storage, networking, IAM, serverless
├── 02-linux/                     ← filesystem, users, processes, shell scripting, SSH
├── 03-networking/                ← OSI, TCP/IP, DNS, TLS, CIDR, NAT, firewalls, VPN
├── 04-git-devops-basics/         ← Git, GitHub, SSH keys
├── 05-aws/                       ← full AWS coverage (IAM → CloudFront → EKS → Lambda → ...)
├── 06-azure/                     ← full Azure coverage (Entra ID → AKS → Key Vault → ...)
├── 07-gcp/                       ← full GCP coverage (IAM → GKE → Cloud Run → BigQuery → ...)
├── 08-other-clouds/              ← OCI, IBM Cloud, Alibaba, DigitalOcean, Cloudflare
├── 09-containers/                ← Docker, Dockerfile, Docker Compose, registries
├── 10-kubernetes/                ← architecture, workloads, networking, RBAC, Helm, Kustomize
├── 11-terraform-opentofu/        ← providers, modules, state, backends, security, testing
├── 12-ansible/                   ← inventory, playbooks, roles, real-world examples
├── 13-cicd-gitops/               ← GitHub Actions, GitLab CI, ArgoCD, FluxCD
├── 14-security/                  ← IAM, zero-trust, KMS, WAF, container/k8s security
├── 15-observability/             ← metrics, logs, traces, Prometheus, Grafana, golden signals
├── 16-sre/                       ← SLI/SLO/SLA, error budgets, incidents, postmortems
├── 17-finops/                    ← pricing, budgets, rightsizing, cost dashboards
├── 18-databases/                 ← SQL vs NoSQL, caching, queues, cross-cloud comparison
├── 19-disaster-recovery/         ← RTO/RPO, backup, multi-region, DR patterns
├── 20-migration/                 ← 6Rs, hybrid connectivity, cutover planning
├── 21-multi-cloud/               ← multi-cloud strategy, vendor lock-in avoidance
├── 22-projects/                  ← real-world end-to-end projects
├── 23-troubleshooting/           ← production readiness, k8s, terraform, network, db issues
├── 24-cheatsheets/               ← AWS, Azure, GCP, Kubernetes, Terraform, Linux quick ref
├── 25-glossary/                  ← terminology for cloud, DevOps, SRE, security
├── 26-roadmaps/                  ← beginner, intermediate, advanced learning paths
├── 27-interview-prep/            ← AWS, k8s, networking, security, scenario questions
├── 28-references/                ← official docs, books, curated links
│
│  ── Lab Platforms ──────────────────────────────────────────────────────
│
├── docker/                       ← simple Docker lab platform
│   ├── docker-compose.yml        ← single file, 14 profiles
│   ├── run.sh                    ← interactive menu + direct commands
│   ├── labs/                     ← 19 lab directories
│   ├── practice/                 ← 14 practice exercises
│   └── infrastructure/           ← Helm, Kustomize, OpenTofu
│
└── 40-local-cloud-lab-platform/  ← advanced lab platform
    ├── Makefile
    ├── docker-compose.yml
    ├── api/                      ← FastAPI backend
    ├── ui/                       ← React dashboard
    ├── lab-runner/
    └── labs/                     ← 30 lab directories
```

---

## Directory Numbering — Critical

The AWS directory is `05-aws/` not `04-aws/`. All internal links must use the correct numbers.

| Section | Correct directory |
|---------|------------------|
| AWS | `05-aws/` |
| Azure | `06-azure/` |
| GCP | `07-gcp/` |
| Other Clouds | `08-other-clouds/` |
| Containers | `09-containers/` |
| Kubernetes | `10-kubernetes/` |
| Terraform | `11-terraform-opentofu/` |
| Ansible | `12-ansible/` |
| CI/CD | `13-cicd-gitops/` |
| Security | `14-security/` |
| Observability | `15-observability/` |
| SRE | `16-sre/` |
| FinOps | `17-finops/` |
| Databases | `18-databases/` |
| DR | `19-disaster-recovery/` |
| Migration | `20-migration/` |
| Multi-cloud | `21-multi-cloud/` |
| Projects | `22-projects/` |
| Troubleshooting | `23-troubleshooting/` |
| Cheatsheets | `24-cheatsheets/` |
| Glossary | `25-glossary/` |
| Roadmaps | `26-roadmaps/` |
| Interview Prep | `27-interview-prep/` |
| References | `28-references/` |

---

## Naming Conventions

- **Directories:** `NN-lowercase-kebab-case/` (always two-digit prefix)
- **Files:** `lowercase-kebab-case.md`
- **Images:** `assets/images/{provider}/{service}/filename.png`
- **No spaces** in any file or directory name

Image path references:
- From `05-aws/04-compute/ec2.md` → `../../assets/images/aws/ec2/`
- From `05-aws/README.md` → `../assets/images/aws/aws/`

---

## Navigation Footer Rule

Every `.md` file in directories `00-foundations/` through `28-references/` must end with:

```markdown
---

← [Previous: Label](relative/path/to/file.md) | [Home](../../README.md) | [Next: Label →](relative/path/to/file.md)
```

- Use **relative paths only** — no absolute paths
- Home for top-level section files: `../README.md`
- Home for sub-section files (e.g., `05-aws/01-account-setup/`): `../../README.md`
- Support files in `assets/`, `scripts/`, `templates/` do NOT get footers

---

## validate-repo.sh

Run to check repo health:
```bash
bash scripts/validate-repo.sh
```

Checks: broken image links, missing READMEs, missing attributions, old branding.

Known exceptions (will not cause failures):
- Skips `.claude/`, `.github/`, `assets/images/`, `assets/diagrams/`, `assets/prompts/`
- Skips template `{placeholder}` paths and fenced code blocks
- Excludes CHANGELOG.md, validate-repo.sh, PULL_REQUEST_TEMPLATE.md from branding check

---

## Commit Style

```
feat: batch-N section-name description       # new content
fix: batch-fix-N what-was-fixed              # bug/link fix
docs: batch-N section-name description       # documentation improvement
chore: batch-N description                   # non-content maintenance
```

Stage specific files — never `git add -A` or `git add .` to avoid accidentally staging `.env` files.

---

## Safety Rules

1. Never commit `.env` — it is gitignored. Always commit `.env.example`.
2. Never commit real credentials, tokens, or secrets of any kind.
3. No hotlinked images in Markdown — all images must be in `assets/images/` with local paths.
4. `.terraform.lock.hcl` is **not** gitignored — this is correct per Terraform best practices.
5. `scripts/validate-repo.sh` must pass with no failures after any batch.
6. Never use `--no-verify` on commits unless explicitly asked.

---

## Anti-Hallucination Rule

This applies to all work in this repo:

- Never invent AWS/Azure/GCP service names, CLI commands, API names, Terraform resource names.
- Never state a service supports a feature unless verified from official documentation.
- Never fabricate service limits or quotas — say "check official docs for current limits" if unsure.
- If uncertain about any capability: `> **Needs verification from official docs**`
- Use only real Docker image names with verified tags.
- Do not fake command output — show representative realistic output or omit it.

---

## What NOT to Do

- Do NOT regenerate existing complete files unless the user asks to improve or fix them.
- Do NOT add features, refactors, or "improvements" beyond what was asked.
- Do NOT use `04-aws/` — the correct path is `05-aws/`.
- Do NOT use absolute paths in Markdown links.
- Do NOT hotlink external images.
- Do NOT commit `.claude/settings.local.json` (it is gitignored).
- Do NOT push to remote unless explicitly asked.
- Do NOT amend published commits.

---

## Extending the Repo

All batches 0–28 are complete. Future work patterns:

| Type | Commit prefix | Example |
|------|--------------|---------|
| Add missing doc topic | `feat: batch-doc-N` | `feat: batch-doc-aws add CodeBuild documentation` |
| Fix content gaps | `feat: batch-doc-gap` | `feat: batch-doc-gap fill missing k8s RBAC section` |
| Extend docker/ platform | `feat: docker-batch-N` | `feat: docker-batch-20 add kubernetes-local lab` |
| Extend 40-local-cloud-lab-platform/ | `feat: lab-batch-N` | `feat: lab-batch-5 add azure-blob lab` |
| Fix broken links/footers | `fix: batch-fix-N` | `fix: batch-fix-1 correct broken nav footers in 05-aws` |
| Update scripts | `chore: batch-N` | `chore: batch-scripts-1 update validate-repo.sh` |
