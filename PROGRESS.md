# Progress

## Current phase

Phase 1 — CKAD-focused Kubernetes

## Current environment

- Ubuntu laptop
- Minikube
- kubectl alias: `k`
- metrics-server addon enabled
- GitHub repository initialized

## Current strengths / already practiced

These topics have been discussed or practiced before this repository was created. They should still be validated with hands-on challenges before being marked MASTERED.

- Pods
- `kubectl run`
- imperative YAML generation
- ConfigMaps
- Secrets
- `env` and `envFrom`
- service account token concepts
- Deployments
- Services basics
- Kustomize basics and patches
- resource requests and limits concepts
- `kubectl top`
- metrics-server on Minikube
- multi-container Pod basics
- init container concepts

## Current topic

Kubernetes resources

Focus:

- CPU requests
- CPU limits
- memory requests
- memory limits
- scheduling vs runtime enforcement
- QoS classes
- LimitRange
- ResourceQuota
- metrics and `kubectl top`

## Current confidence

### Resources requests / limits
Status: LEARNED, needs more practical verification

### LimitRange
Status: LEARNED, needs hands-on lab

### ResourceQuota
Status: LEARNED, needs hands-on lab

### QoS
Status: LEARNED, needs challenge

### Metrics server / kubectl top
Status: PRACTICED

Observed troubleshooting history:

- `kubectl top` initially returned `Metrics API not available`
- Minikube `metrics-server` addon was enabled
- immediately querying a newly created Alpine Pod returned `podmetrics.metrics.k8s.io ... not found`, illustrating that metrics collection is not instantaneous

## Known areas to reinforce

- exact distinction between LimitRange and ResourceQuota under pressure
- quota behavior with Deployments/replicas
- QoS classification from manifests
- troubleshooting Pending Pods caused by requests
- memory OOM vs CPU throttling in practice
- service account token behavior and modern projected tokens

## Current learning rules

- Kustomize should be included regularly but not forced into tiny exercises.
- Challenges should not receive a full solution before a genuine attempt.
- Troubleshooting exercises are required.
- Do not skip fundamentals because a certification command can be memorized.

## Next action

Create the first repository-backed CKAD learning batch around Kubernetes resources, starting with a practical requests/limits lab and then moving into LimitRange, ResourceQuota, QoS, and failure scenarios.

The first batch should be small (roughly 3–5 tasks), not the entire CKAD roadmap.

## Last updated

2026-08-18
