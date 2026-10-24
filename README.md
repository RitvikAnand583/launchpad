# 🚀 LaunchPad

A self-hosted Platform-as-a-Service (PaaS) built on Kubernetes — my own mini Heroku/Vercel.

## What is LaunchPad?

LaunchPad lets a developer deploy an app just by pushing code to GitHub.
It automatically builds the code into a container image, scans it for security issues,
and deploys it to Kubernetes with its own HTTPS URL, monitoring and logs.
Every pull request gets its own temporary **preview environment**, which is deleted when the PR is closed.

## Why am I building this?

I am a DevOps Associate with 6 months of experience. I want to go deeper than day-to-day tasks
and understand how real platform teams build internal developer platforms.
This is a 24-week learning project (Oct 2026 – Apr 2027) where I build everything step by step —
from bare Linux servers to a production-grade platform — and document every decision.

## Planned features

- **Push-to-deploy** — `git push` → build → scan → deploy, no manual steps
- **Preview environments** — a live URL for every pull request, auto-deleted on close
- **Custom Kubernetes operator** — `PreviewEnv` CRD written in Go
- **GitOps** — Git is the single source of truth (ArgoCD)
- **Progressive delivery** — canary releases with automatic rollback
- **Built-in observability** — metrics, logs, traces and SLO alerts for every app
- **Supply-chain security** — image scanning, signing and policy enforcement
- **Secrets management** — no secrets in Git, ever
- **Autoscaling, chaos testing and disaster recovery**
- **Cost tracking** — see how much each app/environment costs
- **`launchpad` CLI** — deploy, view logs and manage apps from the terminal

## Tech stack

| Area | Tools |
|---|---|
| OS & scripting | Ubuntu, Bash, cloud-init, Multipass |
| Containers & orchestration | Docker, Kubernetes (kubeadm), Helm |
| Build | Kaniko, GitHub Actions |
| Infrastructure as Code | Terraform, Ansible, AWS (VPC, EKS, IAM) |
| Platform code | Node.js/TypeScript (API), Go (operator, CLI) |
| GitOps & delivery | ArgoCD, Argo Rollouts |
| Observability | Prometheus, Grafana, Loki, OpenTelemetry |
| Security | Trivy, Cosign, Kyverno, Vault, Falco |
| Reliability & cost | KEDA, Chaos Mesh, Velero, OpenCost, k6 |

*(Updated as the project grows.)*

## Roadmap

| Week | Sprint | Goal |
|---|---|---|
| 1 | Foundations | Repo, Bash scripting, networking, 3-node lab |
| 2–3 | Kubernetes the hard way | kubeadm cluster, core objects, Ingress, TLS |
| 4–5 | Push-to-deploy v1 | Webhook API, Kaniko builds, Helm, CI pipeline |
| 6–8 | Terraform + AWS | VPC, EKS, IAM/IRSA, remote state, Ansible |
| 9–11 | Kubernetes operator | `PreviewEnv` CRD with Kubebuilder (Go) |
| 12–13 | GitOps | ArgoCD, ApplicationSets, Argo Rollouts |
| 14–16 | Observability | Prometheus, Grafana, Loki, OpenTelemetry, SLOs |
| 17–19 | DevSecOps | Trivy, Cosign, Kyverno, Vault, Falco |
| 20–22 | Scale, reliability & cost | KEDA, Chaos Mesh, Velero, OpenCost, k6 |
| 23–24 | Polish & showcase | CLI, docs, demo video |

## Progress

- [ ] **Week 1 — Foundations** *(in progress)*

## Documentation

- [Architecture Decision Records](docs/adr/)
- [Today I Learned](docs/TIL.md)

---
