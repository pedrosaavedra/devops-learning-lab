# Project Context

This file exists so a future study session can understand the project without relying on prior chat memory.

## Learner goal

Build strong practical DevOps skills in this order:

1. CKAD-focused Kubernetes application skills
2. CKA-focused Kubernetes administration and troubleshooting
3. Terraform and Shell/Bash
4. Azure fundamentals with practical exercises
5. Integration of all of the above into a realistic DevOps platform project

The learner already has professional software development and DevOps experience, so the program should avoid wasting time on overly basic material once competence is demonstrated. However, weak fundamentals must still be corrected rather than skipped.

## Fixed environment

Initial environment:

- Ubuntu laptop
- Minikube
- kubectl alias may be `k`
- Docker/container runtime locally
- Git/GitHub
- Kustomize

Do not assume access to a paid cloud account during CKAD or CKA phases.

## Repository role

This repository is the source of truth for:

- study plan
- current progress
- labs
- challenges
- troubleshooting exercises
- notes written by the learner
- review history
- eventually an integrated DevOps project

If chat memory and repository state disagree, prefer the repository state unless there is clear evidence it is outdated.

## Teaching style

The preferred style is direct and practical.

- Explain the concept clearly.
- Give a concrete task.
- Let the learner attempt it.
- Review the actual implementation.
- Point out incorrect assumptions explicitly.
- Prefer progressive hints over immediately giving the full challenge solution.
- Use troubleshooting scenarios frequently.
- Do not mark a topic as mastered merely because the learner has seen an explanation.

## Levels of learning

Each topic can have one of these states:

### LEARNED
The learner can explain the basic concept and terminology.

### PRACTICED
The learner completed at least one meaningful hands-on lab.

### MASTERED
The learner solved an independent challenge or troubleshooting scenario with little or no significant help and can explain why the solution works.

## Kubernetes and Kustomize rule

Kustomize must be used regularly because it is an explicit learning goal.

However, do not force Kustomize into tiny exercises where it hides the Kubernetes concept being studied.

Use direct manifests or imperative commands for focused exercises. Use Kustomize for realistic multi-resource labs, environment overlays, patches, configuration generation, and the integrated project.

## Lab vs challenge

### Lab
Guided learning is allowed. Questions and explanations are expected.

### Challenge
The learner should attempt the solution independently. The assistant should use progressive hints before giving a complete solution.

Suggested hint progression:

1. conceptual direction
2. resource/field to inspect
3. command or documentation area
4. partial example
5. full solution only when necessary

## Troubleshooting is mandatory

Important topics should include deliberate failure modes such as:

- Pending Pods
- CrashLoopBackOff
- ImagePullBackOff
- probe failures
- bad selectors
- resource exhaustion
- quota rejection
- DNS/service connectivity issues
- RBAC denial
- broken Kustomize patches
- Terraform drift/state issues later in the roadmap

## Security rules

Never commit:

- GitHub personal access tokens
- SSH private keys
- kubeconfig files
- Azure credentials
- service principal secrets
- `.env` files containing secrets
- real company manifests/configuration
- Terraform state that may contain secrets
- passwords or production tokens

Use synthetic values for all exercises.

## Repository visibility

The repository can remain public because it can become useful proof of learning and engineering progression.

If real company data, personal secrets, private infrastructure details, or credentials ever need to be included, do not commit them. If the nature of the project changes and sensitive material becomes unavoidable, reevaluate repository visibility first.

## How a future assistant should resume

1. Read this file.
2. Read `PROGRESS.md`.
3. Read the current phase in `ROADMAP.md`.
4. Inspect recent commits/files/issues related to the active topic.
5. Continue from `Next action` in `PROGRESS.md`.
6. Update `PROGRESS.md` when a meaningful learning milestone changes.

## End-state capability

At the end of the learning program, the learner should be able to take a small application and independently:

- containerize it
- design Kubernetes manifests
- manage configuration and secrets correctly
- define probes and resources
- expose and secure workloads
- use Kustomize bases and overlays
- troubleshoot scheduling, networking, storage, security, and workload failures
- understand and administer core Kubernetes components at CKA depth
- provision infrastructure with Terraform
- automate operational work with Bash
- understand core Azure networking, identity, compute, storage, registry, and AKS concepts
- review generated DevOps/infrastructure code critically
- combine the technologies into a coherent end-to-end platform
