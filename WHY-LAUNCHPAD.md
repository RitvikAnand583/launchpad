# 1. Why I am building LaunchPad

Date: 2026-10-24
Status: Accepted

## Context

I have been working as a DevOps Associate for 6 months. My daily work teaches me
specific tasks, but I want a deeper, end-to-end understanding of how modern platforms
are built — the kind of knowledge engineers usually gain over their first few years.

Constraints:
- **Time:** about 2 hours on weekdays and longer sessions on weekends, for 6 months.
- **Budget:** about $50 of AWS credit, so most work must run locally.
- **Skills:** strong in Node.js/React, new to Go and to building Kubernetes tooling.

Most portfolio projects (e-commerce apps, to-do apps) only show that someone can
*deploy* an app. I want a project where the platform itself is the product.

## Decision

I will build **LaunchPad**, a self-hosted PaaS on Kubernetes, in 24 weekly sprints.

- Start from bare Linux VMs and set up Kubernetes by hand (kubeadm) to learn the internals.
- Run most of the work on a local 3-node lab (Multipass) to save AWS cost.
- Use AWS only for the Terraform/EKS stage and the final demo, and always destroy resources.
- Write the API in Node.js/TypeScript (my strongest language) and learn Go for the operator and CLI.
- Track work on a GitHub Projects board and record important decisions as ADRs.

## Consequences

**Positive**
- Covers the full DevOps lifecycle: Linux, containers, CI/CD, IaC, Kubernetes, GitOps,
  observability, security, reliability and cost.
- Results in a unique, well-documented portfolio project.
- Writing a Kubernetes operator gives experience that few engineers at my level have.

**Negative / risks**
- The timeline is tight alongside a full-time job; there is a risk of burnout.
  → Mitigation: one rest evening per week, and optional "stretch goals" can be dropped.
- The AWS budget is small. → Mitigation: budget alerts, spot instances, no NAT gateway,
  `terraform destroy` after every session.
- Learning Go adds extra work. → Mitigation: start Go in Week 4; fall back to Python (Kopf)
  for the operator if needed.
