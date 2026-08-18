# Study Method

This repository is designed around active practice, not passive note collection.

## Standard learning cycle

For most topics, use this sequence:

1. Concept explanation
2. Small guided lab
3. Learner implementation
4. Review
5. Independent challenge
6. Deliberate failure / troubleshooting scenario
7. Recap in learner's own words
8. Progress update

## Lab format

A lab may include guidance and examples.

Each lab should contain:

- objective
- prerequisites
- task
- commands/resources allowed
- verification steps
- questions to answer
- cleanup steps where relevant

The learner may ask implementation questions during a lab.

## Challenge format

A challenge is intended to test independent understanding.

Each challenge should contain:

- objective
- scenario
- requirements
- constraints
- success criteria

The challenge should avoid embedding the solution.

## Hint policy

If help is needed during a challenge, prefer progressive hints:

### Hint 1 — Concept
Explain which Kubernetes/Terraform/Linux concept is relevant without naming the exact solution.

### Hint 2 — Area to inspect
Point to the resource, field, command family, log, or documentation section.

### Hint 3 — Tactical command
Suggest a diagnostic command or partial syntax.

### Hint 4 — Partial implementation
Show only the difficult portion.

### Hint 5 — Full solution
Provide the complete answer only after enough attempts or when the learner explicitly chooses to stop solving independently.

## Review policy

Reviews should check more than syntax.

For Kubernetes, inspect:

- validity
- selectors/labels
- lifecycle behavior
- resources
- security
- configuration handling
- availability
- troubleshooting implications
- maintainability
- whether Kustomize is being used appropriately

For Terraform, later inspect:

- provider/resource correctness
- dependencies
- state implications
- repeatability
- idempotence
- module design
- security
- maintainability

For Shell, later inspect:

- quoting
- exit handling
- error handling
- readability
- portability where relevant
- dangerous destructive behavior

## Mastery levels

### LEARNED
The learner can explain the core idea correctly.

Evidence examples:

- explains requests vs limits
- explains ConfigMap vs Secret
- explains readiness vs liveness

### PRACTICED
The learner completed a meaningful hands-on task and verified the result.

### MASTERED
The learner independently solves a new task/troubleshooting scenario and can explain the reasoning.

Do not promote a topic to MASTERED simply because a copied manifest worked.

## Notes policy

Notes should be concise and preferably written by the learner.

Good note:

```text
CPU request is used by the scheduler when deciding whether a Pod fits on a node. CPU limit is a runtime ceiling and excess CPU is throttled.
```

Bad note:

A 4-page assistant-generated explanation copied verbatim without demonstrating understanding.

## Kustomize policy

Use Kustomize regularly but intentionally.

Use a simple direct manifest when the lesson is about one Kubernetes field or resource.

Use Kustomize when practicing:

- multiple related resources
- dev/prod variants
- patches
- generated ConfigMaps/Secrets
- image changes
- shared bases
- replacements
- realistic application configuration

## Git workflow

Normal learner workflow:

```bash
git pull
# work on task
git status
git diff
git add <files>
git commit -m "learn: <topic>"
git push
```

Commit messages should describe the learning step, for example:

```text
learn: practice pod resource requests and limits
lab: add ResourceQuota failure scenario
fix: correct service selector challenge
refactor: move dev differences into kustomize overlay
```

## GitHub Issues

Issues may represent learning tasks and challenges.

Suggested naming:

```text
CKAD-001: Pod command and args
CKAD-010: Resource requests and limits
CKA-004: Taints and tolerations
TF-006: Understand Terraform state
SH-004: Pipes and exit codes
AZ-003: VNet and subnet fundamentals
```

Do not create the entire curriculum as hundreds of issues at once. Create a small upcoming batch based on current progress.

## Session resume protocol

At the beginning of a future session:

1. Read `PROJECT_CONTEXT.md`.
2. Read `PROGRESS.md`.
3. Check the active roadmap section.
4. Review the most recent relevant implementation or issue.
5. Continue from the recorded next action.

At the end of a meaningful milestone:

- update progress
- record remaining confusion
- define next action

## Failure-first learning

Once a concept is understood normally, deliberately break it.

Examples:

- wrong image name -> ImagePullBackOff
- wrong command -> CrashLoopBackOff
- impossible request -> Pending
- memory limit violation -> OOMKilled
- incorrect readiness probe -> Service receives no endpoint
- bad selector -> Service cannot reach Pods
- missing ConfigMap -> Pod startup failure
- quota exceeded -> admission rejection
- broken Kustomize patch -> build/apply failure

The learner should diagnose from observable symptoms rather than being told the cause first.
