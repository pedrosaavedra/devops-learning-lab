# Learning Roadmap

This roadmap defines the intended order of learning. It is not a rigid calendar. Topics can move faster or slower depending on demonstrated understanding.

# Phase 0 — Lab foundation

Goal: make the local environment predictable and usable for all later labs.

Topics:

- [ ] Verify Minikube cluster health
- [ ] Verify kubectl context and namespace usage
- [ ] Enable and verify metrics-server
- [ ] Practice `kubectl top`
- [ ] Verify Kustomize workflow through `kubectl apply -k`
- [ ] Verify Git workflow for this repository
- [ ] Establish lab namespace conventions

Exit criteria:

- Minikube can run workloads reliably
- metrics can be queried
- Kustomize manifests can be rendered and applied
- learner can commit and push lab work

# Phase 1 — CKAD-focused Kubernetes

Goal: become strong at configuring, deploying, exposing, updating, and troubleshooting Kubernetes application workloads.

## 1. Pods and container execution

- [ ] Pod structure
- [ ] `kubectl run`
- [ ] command vs args
- [ ] container entrypoint behavior
- [ ] interactive temporary Pods
- [ ] restart policies

Target capability: create and inspect Pods quickly using both imperative commands and YAML.

## 2. Environment and configuration

- [ ] environment variables
- [ ] ConfigMaps
- [ ] `env`
- [ ] `envFrom`
- [ ] ConfigMap volume mounts
- [ ] configuration generation with Kustomize

Target capability: choose correctly between direct environment values, ConfigMaps, and mounted configuration files.

## 3. Secrets

- [ ] Secret types
- [ ] `Opaque`
- [ ] `kubernetes.io/service-account-token`
- [ ] `env`
- [ ] `envFrom`
- [ ] Secret volume mounts
- [ ] secret generation with Kustomize
- [ ] security implications of environment variables vs files

Target capability: configure applications without embedding secrets directly into manifests.

## 4. Multi-container Pods

- [ ] sidecar pattern
- [ ] shared volumes
- [ ] init containers
- [ ] container-specific commands
- [ ] container-specific logs and exec

Target capability: reason about lifecycle and shared resources inside one Pod.

## 5. Volumes

- [ ] `emptyDir`
- [ ] ConfigMap volumes
- [ ] Secret volumes
- [ ] persistent volume concepts
- [ ] PVC basics

Target capability: understand ephemeral vs persistent data at application level.

## 6. Health probes

- [ ] livenessProbe
- [ ] readinessProbe
- [ ] startupProbe
- [ ] HTTP probes
- [ ] TCP probes
- [ ] exec probes
- [ ] common misconfiguration scenarios

Target capability: diagnose why a container restarts or why a Pod is removed from Service endpoints.

## 7. Resources

- [ ] CPU requests
- [ ] CPU limits
- [ ] memory requests
- [ ] memory limits
- [ ] CPU throttling
- [ ] OOMKilled
- [ ] Pod resource aggregation
- [ ] init container resource calculation
- [ ] QoS classes
- [ ] `kubectl top`
- [ ] `kubectl describe node`
- [ ] LimitRange
- [ ] ResourceQuota
- [ ] namespace quota failures

Target capability: predict scheduling and runtime behavior from resource configuration.

## 8. Deployments and rollout behavior

- [ ] Deployment structure
- [ ] ReplicaSets
- [ ] replicas
- [ ] rolling updates
- [ ] `maxSurge`
- [ ] `maxUnavailable`
- [ ] rollout status
- [ ] rollout history
- [ ] rollback
- [ ] scaling

Target capability: deploy and safely update stateless applications.

## 9. Jobs and CronJobs

- [ ] Job
- [ ] completions
- [ ] parallelism
- [ ] backoffLimit
- [ ] CronJob scheduling
- [ ] concurrency behavior
- [ ] cleanup behavior

Target capability: choose between long-running workloads and finite tasks.

## 10. Services and application networking

- [ ] ClusterIP
- [ ] NodePort
- [ ] Service selectors
- [ ] targetPort vs port
- [ ] named ports
- [ ] endpoints / EndpointSlices
- [ ] DNS service discovery
- [ ] temporary debug Pods for curl/nslookup

Target capability: troubleshoot a Running Pod that is not reachable.

## 11. Ingress

- [ ] Ingress concepts
- [ ] Minikube ingress addon
- [ ] host/path routing
- [ ] Service integration

Target capability: expose multiple HTTP routes through a shared entry point in the local lab.

## 12. SecurityContext

- [ ] runAsUser
- [ ] runAsNonRoot
- [ ] filesystem permissions
- [ ] readOnlyRootFilesystem
- [ ] Linux capabilities basics

Target capability: identify common workload-level security mistakes.

## 13. ServiceAccounts and application RBAC basics

- [ ] ServiceAccounts
- [ ] projected service account tokens
- [ ] Role
- [ ] RoleBinding
- [ ] `kubectl auth can-i`

Target capability: understand how a workload authenticates and receives Kubernetes API permissions.

## 14. NetworkPolicy

- [ ] default allow behavior
- [ ] ingress policy
- [ ] egress policy
- [ ] podSelector
- [ ] namespaceSelector
- [ ] deliberate connectivity failure labs

Target capability: implement and troubleshoot basic network isolation.

## 15. Horizontal Pod Autoscaler

- [ ] metrics-server dependency
- [ ] resource requests and HPA
- [ ] CPU utilization targets
- [ ] generate load
- [ ] observe scaling behavior

Target capability: understand why HPA works, not just how to create one.

## 16. Kustomize in depth

Kustomize is practiced throughout CKAD, but this section consolidates it.

- [ ] bases/resources
- [ ] overlays
- [ ] patches
- [ ] strategic merge concepts/history
- [ ] JSON6902 concepts where relevant
- [ ] modern `patches`
- [ ] namePrefix/nameSuffix
- [ ] commonLabels/labels behavior
- [ ] images
- [ ] configMapGenerator
- [ ] secretGenerator
- [ ] replacements
- [ ] components where useful
- [ ] rendering/debugging generated manifests

Target capability: maintain dev/prod variations without duplicating entire manifests.

## 17. CKAD troubleshooting and mixed challenges

- [ ] CrashLoopBackOff
- [ ] ImagePullBackOff
- [ ] Pending
- [ ] failed probes
- [ ] bad Service selector
- [ ] incorrect command/args
- [ ] missing ConfigMap/Secret
- [ ] ResourceQuota rejection
- [ ] broken Kustomize patch
- [ ] multi-resource timed challenges

CKAD phase exit criteria:

- learner can solve representative application-focused Kubernetes tasks without heavy assistance
- learner is comfortable with imperative generation plus YAML editing
- learner can use Kustomize naturally
- learner can troubleshoot common workload failures
- CKAD certification preparation is complete

# Phase 2 — CKA-focused Kubernetes administration

Goal: move from application configuration to cluster operation, scheduling, storage, security, networking, and troubleshooting.

## 1. Kubernetes architecture

- [ ] API server
- [ ] etcd
- [ ] scheduler
- [ ] controller manager
- [ ] kubelet
- [ ] kube-proxy
- [ ] container runtime
- [ ] static Pods
- [ ] control-plane communication

## 2. Scheduling

- [ ] nodeSelector
- [ ] node affinity
- [ ] pod affinity / anti-affinity
- [ ] taints
- [ ] tolerations
- [ ] requests and allocatable resources
- [ ] manual scheduling concepts
- [ ] scheduling failure troubleshooting

## 3. Multi-node local practice

When useful and hardware permits:

- [ ] multi-node Minikube
- [ ] labels on nodes
- [ ] cordon
- [ ] drain
- [ ] uncordon
- [ ] workload placement

## 4. Cluster networking

- [ ] CNI concepts
- [ ] Pod networking
- [ ] Service networking
- [ ] kube-proxy concepts
- [ ] CoreDNS
- [ ] DNS troubleshooting
- [ ] connectivity troubleshooting

## 5. Storage administration

- [ ] PV
- [ ] PVC
- [ ] access modes
- [ ] reclaim policies
- [ ] StorageClass
- [ ] dynamic provisioning
- [ ] volume binding behavior

## 6. RBAC and authentication

- [ ] users vs ServiceAccounts
- [ ] Roles
- [ ] ClusterRoles
- [ ] RoleBindings
- [ ] ClusterRoleBindings
- [ ] permissions troubleshooting
- [ ] certificates basics

## 7. Cluster maintenance concepts

Some tasks cannot be reproduced exactly by Minikube and may require conceptual study or a temporary local multi-node/kubeadm-style lab if later justified.

- [ ] cluster upgrades
- [ ] version skew
- [ ] node maintenance
- [ ] etcd backup/restore concepts
- [ ] certificate management concepts

## 8. CKA troubleshooting

- [ ] broken kubelet
- [ ] node NotReady concepts
- [ ] DNS failures
- [ ] Service failures
- [ ] scheduling failures
- [ ] storage failures
- [ ] RBAC failures
- [ ] control-plane component diagnosis concepts

CKA phase exit criteria:

- learner understands Kubernetes architecture beyond workload YAML
- learner can troubleshoot common cluster-level failures
- learner understands scheduling, storage, networking, and RBAC at administrator level
- CKA certification preparation is complete

# Phase 3 — Terraform + Shell

Goal: learn Infrastructure as Code and practical Linux automation together.

Shell basics begin earlier whenever Kubernetes labs naturally require them; this phase develops them deliberately.

## Terraform foundations

- [ ] HCL syntax
- [ ] providers
- [ ] resources
- [ ] variables
- [ ] outputs
- [ ] locals
- [ ] data sources
- [ ] references and dependency graph
- [ ] `terraform init`
- [ ] `terraform fmt`
- [ ] `terraform validate`
- [ ] `terraform plan`
- [ ] `terraform apply`
- [ ] `terraform destroy`

## Terraform state

- [ ] state purpose
- [ ] state inspection
- [ ] drift
- [ ] import
- [ ] remote state concepts
- [ ] state locking concepts
- [ ] sensitive state data

## Terraform language and reuse

- [ ] `count`
- [ ] `for_each`
- [ ] conditionals
- [ ] functions
- [ ] modules
- [ ] module inputs/outputs
- [ ] lifecycle
- [ ] `depends_on` and when not to use it

## Shell foundations

- [ ] variables
- [ ] quoting
- [ ] exit codes
- [ ] `$?`
- [ ] positional arguments
- [ ] `$@`
- [ ] stdin/stdout/stderr
- [ ] redirects
- [ ] pipes
- [ ] grep
- [ ] cut
- [ ] sort/uniq
- [ ] sed
- [ ] awk
- [ ] xargs
- [ ] curl
- [ ] jq
- [ ] loops
- [ ] conditions
- [ ] functions
- [ ] `set -euo pipefail`
- [ ] process basics
- [ ] filesystem and permission basics
- [ ] networking/debugging commands

## Integrated Terraform + Shell labs

- [ ] validate Terraform from scripts
- [ ] parse Terraform output
- [ ] automate environment setup
- [ ] check prerequisites
- [ ] safe cleanup scripts
- [ ] deliberately broken scripts and error handling

Phase exit criteria:

- learner can write maintainable small/medium Terraform configurations
- learner understands state rather than treating Terraform as a command generator
- learner can write practical Bash automation without blindly copying scripts

# Phase 4 — Azure fundamentals, hands-on

Goal: gain enough Azure knowledge to understand and operate the infrastructure that Terraform will provision.

Do not attempt deep Azure specialization yet.

## Platform concepts

- [ ] tenant
- [ ] subscription
- [ ] resource groups
- [ ] regions
- [ ] availability concepts

## Identity

- [ ] Entra ID basics
- [ ] Azure RBAC
- [ ] managed identities
- [ ] service principals concepts

## Networking

- [ ] VNet
- [ ] subnet
- [ ] NSG
- [ ] public/private IPs
- [ ] DNS basics
- [ ] load balancing concepts
- [ ] private endpoint concepts

## Compute and storage

- [ ] VM basics
- [ ] storage accounts
- [ ] Blob Storage

## Container platform

- [ ] Azure Container Registry
- [ ] AKS concepts
- [ ] AKS identity/network integration

## Operations and security

- [ ] Azure Monitor basics
- [ ] Log Analytics basics
- [ ] Key Vault basics

## Terraform on Azure

Once the Azure objects are understood manually/conceptually:

- [ ] Azure provider authentication
- [ ] resource group with Terraform
- [ ] networking with Terraform
- [ ] ACR with Terraform
- [ ] selected additional resources
- [ ] AKS only when cost/account constraints make it sensible

Phase exit criteria:

- learner can explain core Azure resource relationships
- learner can read and review Terraform that provisions basic Azure infrastructure
- learner understands identity and networking well enough to troubleshoot common deployment problems

# Phase 5 — Integrated DevOps project

Goal: combine the learned technologies into a realistic platform rather than leaving knowledge isolated.

Possible final architecture:

```text
GitHub
   |
   v
CI/CD
   |
   v
Container image
   |
   v
Registry
   |
   v
Kubernetes / AKS
   |
   v
Application
```

Infrastructure and operations:

```text
Terraform -> Azure infrastructure
Kustomize -> Kubernetes environment configuration
Bash      -> operational automation and diagnostics
Git       -> versioned source of truth
```

The integrated project should include:

- [ ] small application
- [ ] Docker image
- [ ] Kubernetes Deployment
- [ ] Service
- [ ] ConfigMap
- [ ] Secret handling
- [ ] probes
- [ ] resource requests/limits
- [ ] HPA
- [ ] Kustomize base + overlays
- [ ] Infrastructure as Code
- [ ] shell automation
- [ ] CI/CD
- [ ] basic monitoring/observability
- [ ] security review
- [ ] troubleshooting runbook
- [ ] deliberate failure scenarios

## Final engineering capability

Completion means more than passing certifications. The learner should be able to receive a realistic infrastructure task, design a solution, implement it, troubleshoot it, and critically review another implementation—including AI-generated infrastructure code—for correctness, security, operability, maintainability, and reliability.
