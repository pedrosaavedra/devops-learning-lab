# DevOps Learning Lab

A long-term, hands-on learning repository for building practical DevOps, Kubernetes, Infrastructure as Code, shell, and Azure skills.

This repository is not meant to be a collection of copied examples. It is the source of truth for an incremental study program based on labs, challenges, troubleshooting, review, and repetition.

## Final objective

The end goal is to be able to design, build, operate, troubleshoot, and review a realistic DevOps platform using the following stack:

- Kubernetes
- Kustomize
- Terraform
- Bash / Shell
- Azure fundamentals
- CI/CD concepts
- GitOps concepts
- basic observability

The learning order is intentionally constrained:

1. CKAD-oriented Kubernetes
2. CKA-oriented Kubernetes administration
3. Terraform + Shell
4. Azure fundamentals with hands-on practice
5. Integrated DevOps project combining the learned skills

The repository should preserve enough context that a future study session can resume by reading the repository instead of relying on chat memory.

## Fixed lab environment

The initial lab environment is intentionally simple:

- one personal Ubuntu laptop
- Minikube as the Kubernetes cluster
- Docker/container runtime available locally
- kubectl
- Kustomize
- Git and GitHub

Do not introduce paid cloud resources, extra VMs, managed Kubernetes, or other infrastructure unless the current learning phase explicitly requires them.

For CKA topics that genuinely benefit from multiple nodes, a multi-node Minikube cluster may be used if the laptop has enough resources.

## Learning principles

### Understand before automating

Do not hide a Kubernetes concept behind Kustomize, Terraform, scripts, or CI/CD before the underlying Kubernetes resource is understood.

### Kustomize is part of the Kubernetes practice

Use Kustomize for realistic multi-resource labs and applications. Small exercises may use a single manifest or imperative kubectl command when that makes the concept clearer.

### Build, break, troubleshoot

A topic is not considered mastered because a manifest successfully applied once. Labs should include broken configurations and troubleshooting whenever practical.

### The learner writes the solution

The assistant should teach concepts, assign tasks, review work, and give progressive hints. It should avoid producing the complete challenge solution before the learner has made a real attempt.

### Git is the learning history

Meaningful learning steps should be committed. Git history should show progression from Kubernetes fundamentals through infrastructure and cloud topics.

## Repository documents

- `PROJECT_CONTEXT.md` — durable context and rules for future sessions
- `ROADMAP.md` — complete learning path and target capabilities
- `PROGRESS.md` — current state, completed work, weaknesses, and next step
- `STUDY_METHOD.md` — how labs, challenges, review, and mastery work
- `.gitignore` — prevents common secrets and local state from being committed

## Planned repository structure

Directories should be added gradually as they become necessary. The intended structure is:

```text
devops-learning-lab/
├── README.md
├── PROJECT_CONTEXT.md
├── ROADMAP.md
├── PROGRESS.md
├── STUDY_METHOD.md
├── ckad/
│   ├── labs/
│   ├── challenges/
│   └── notes/
├── cka/
│   ├── labs/
│   ├── challenges/
│   └── notes/
├── terraform/
│   ├── labs/
│   ├── challenges/
│   └── notes/
├── shell/
│   ├── labs/
│   ├── challenges/
│   └── notes/
├── azure/
│   ├── labs/
│   └── notes/
└── project/
```

Do not create empty directories purely to match this tree. Add them when the first real exercise needs them.

## How to resume a future session

A future assistant should read, in this order:

1. `PROJECT_CONTEXT.md`
2. `PROGRESS.md`
3. the relevant section of `ROADMAP.md`
4. recent files/commits for the active topic

Then continue from the `Next action` recorded in `PROGRESS.md`.

## Security rule

Never commit real credentials, tokens, SSH private keys, kubeconfig files, Terraform state containing secrets, `.env` files, cloud credentials, or proprietary company configuration.

This repository may remain public as long as that rule is respected and all examples use synthetic learning data.