# Azure Kubernetes Service — 40-Hour Training Program
### Table of Contents

> **Format:** Instructor-Led + Hands-on Labs | **Total Duration:** 40 Hours (5 Days × 8 Hours)

---

## Program Overview

| Day | Theme | Hours |
|-----|-------|-------|
| Day 1 | Containerisation Foundations — Docker & ACR | 8 hrs |
| Day 2 | Kubernetes Core — Concepts, Workloads & kubectl | 8 hrs |
| Day 3 | AKS Deep Dive — Provisioning, Networking & Storage | 8 hrs |
| Day 4 | Observability, Security & Autoscaling | 8 hrs |
| Day 5 | CI/CD, GitOps & Capstone Project | 8 hrs |

---

## Day 1 — Containerisation Foundations: Docker & Azure Container Registry

### Module 1.1 — Introduction to Containers (1 hr)
- 1.1.1 Evolution from VMs to containers
- 1.1.2 Container vs image vs registry
- 1.1.3 OCI standards and container runtimes (Docker, containerd, CRI-O)
- 1.1.4 Overview of the Azure container ecosystem
- *Lab:* Install Docker Desktop and verify installation

### Module 1.2 — Docker Architecture & Core Commands (1.5 hrs)
- 1.2.1 Docker daemon, client, and REST API
- 1.2.2 Managing images: pull, tag, list, inspect, remove
- 1.2.3 Running containers: detached, interactive, port mapping, environment variables
- 1.2.4 Container lifecycle: start, stop, restart, kill, rm
- 1.2.5 Inspecting containers: logs, exec, stats, top
- *Lab:* Run, inspect, and interact with pre-built containers

### Module 1.3 — Writing Effective Dockerfiles (1.5 hrs)
- 1.3.1 Dockerfile instruction reference: FROM, RUN, COPY, ADD, EXPOSE, ENV, ARG, CMD, ENTRYPOINT
- 1.3.2 Layer caching and build optimisation strategies
- 1.3.3 Multi-stage builds for production-grade images
- 1.3.4 Non-root users and least-privilege principles
- 1.3.5 Using .dockerignore effectively
- 1.3.6 Image scanning basics with `docker scout`
- *Lab:* Write a multi-stage Dockerfile for a Node.js/Python/Java application

### Module 1.4 — Docker Compose for Local Development (1 hr)
- 1.4.1 docker-compose.yml structure and syntax
- 1.4.2 Defining services, networks, and volumes
- 1.4.3 Environment files and variable substitution
- 1.4.4 Running multi-container local stacks
- *Lab:* Stand up a full-stack app (API + database) with Docker Compose

### Module 1.5 — Azure Container Registry (ACR) (2 hrs)
- 1.5.1 ACR SKUs: Basic, Standard, Premium — feature comparison
- 1.5.2 Provisioning ACR with Azure CLI and Bicep
- 1.5.3 Authentication methods: admin account, service principal, managed identity, ACR tokens
- 1.5.4 Pushing and pulling images; repository management
- 1.5.5 ACR Tasks: automated builds on code commit and base image updates
- 1.5.6 Geo-replication and zone redundancy (Premium)
- 1.5.7 ACR vulnerability scanning with Microsoft Defender for Containers
- *Lab:* Create ACR, configure managed-identity auth, build and push images using ACR Tasks

### Module 1.6 — Day 1 Review & Q&A (1 hr)
- Recap of key concepts
- Common mistakes and how to avoid them
- Day 1 assessment quiz

---

## Day 2 — Kubernetes Core: Concepts, Workloads & kubectl

### Module 2.1 — Kubernetes Architecture & Design Philosophy (1 hr)
- 2.1.1 The problem Kubernetes solves
- 2.1.2 Control plane components: API Server, etcd, Scheduler, Controller Manager, Cloud Controller Manager
- 2.1.3 Worker node components: kubelet, kube-proxy, container runtime
- 2.1.4 Declarative model and the reconciliation loop
- 2.1.5 Kubernetes API versioning and resource groups

### Module 2.2 — kubectl Mastery (1 hr)
- 2.2.1 Installing and configuring kubectl
- 2.2.2 kubeconfig: contexts, clusters, users
- 2.2.3 Imperative vs declarative workflows
- 2.2.4 Output formats: wide, json, yaml, jsonpath, custom-columns
- 2.2.5 Using `kubectl explain` and API discovery
- 2.2.6 Aliases, plugins (krew), and productivity tips
- *Lab:* Configure multi-cluster kubeconfig and write complex jsonpath queries

### Module 2.3 — Pods & Pod Lifecycle (1 hr)
- 2.3.1 Pod specification anatomy
- 2.3.2 Pod lifecycle phases and conditions
- 2.3.3 Init containers and sidecar containers
- 2.3.4 Resource requests and limits (CPU, memory)
- 2.3.5 Liveness, readiness, and startup probes
- 2.3.6 Pod disruption budgets
- *Lab:* Write pod specs with init containers, probes, and resource constraints

### Module 2.4 — Workload Controllers (1.5 hrs)
- 2.4.1 ReplicaSet — purpose and relationship to Deployments
- 2.4.2 Deployment — rolling updates, rollback, revision history
- 2.4.3 StatefulSet — stable identities and ordered deployment for stateful apps
- 2.4.4 DaemonSet — node-level workloads (logging agents, monitoring)
- 2.4.5 Job and CronJob — batch and scheduled workloads
- *Lab:* Deploy a stateless app with Deployment, perform rolling update and rollback

### Module 2.5 — Services & DNS (1 hr)
- 2.5.1 Service types: ClusterIP, NodePort, LoadBalancer, ExternalName
- 2.5.2 Endpoint slices and kube-proxy modes (iptables vs IPVS)
- 2.5.3 CoreDNS and service discovery within the cluster
- 2.5.4 Headless services for StatefulSets
- 2.5.5 ExternalDNS integration overview
- *Lab:* Expose deployments via different service types and test connectivity

### Module 2.6 — Configuration & Secrets Management (1 hr)
- 2.6.1 ConfigMap: creation patterns, volume mounts, environment injection
- 2.6.2 Secrets: types (Opaque, TLS, docker-registry), base64 encoding
- 2.6.3 Secret security limitations and best practices
- 2.6.4 Azure Key Vault integration with Secrets Store CSI Driver
- 2.6.5 Reloading configuration without pod restarts
- *Lab:* Integrate Azure Key Vault secrets into a running pod via CSI Driver

### Module 2.7 — Namespaces & Resource Quotas (0.5 hr)
- 2.7.1 Namespace design patterns (per-team, per-environment)
- 2.7.2 ResourceQuota and LimitRange objects
- 2.7.3 Default namespace scoping in kubectl

### Module 2.8 — Day 2 Review & Q&A (1 hr)
- Workload controller comparison table
- Exam-style scenario questions
- Hands-on troubleshooting challenge

---

## Day 3 — AKS Deep Dive: Provisioning, Networking & Storage

### Module 3.1 — AKS Architecture & Managed Components (1 hr)
- 3.1.1 AKS control plane management model and SLA
- 3.1.2 System node pools vs user node pools
- 3.1.3 Supported Kubernetes versions and upgrade channels
- 3.1.4 AKS add-ons vs extensions vs open-source integrations
- 3.1.5 AKS pricing model and cost optimisation levers

### Module 3.2 — Provisioning AKS with Azure CLI & Bicep (1.5 hrs)
- 3.2.1 AKS cluster creation parameters walkthrough
- 3.2.2 Managed identity vs service principal
- 3.2.3 Private cluster configuration
- 3.2.4 Node pool configuration: VM sizes, OS disk types, spot instances
- 3.2.5 Infrastructure-as-Code with Bicep templates for AKS
- 3.2.6 Upgrading cluster version and node image
- *Lab:* Provision an AKS cluster via Bicep with a private endpoint

### Module 3.3 — AKS Networking In Depth (2 hrs)
- 3.3.1 Kubenet networking model: routing tables, NAT behaviour
- 3.3.2 Azure CNI: pod IP assignment from VNet subnet
- 3.3.3 Azure CNI Overlay: reduced IP consumption
- 3.3.4 Azure CNI with Cilium dataplane
- 3.3.5 Network policies with Azure Network Policy Manager and Calico
- 3.3.6 Outbound types: Load Balancer, NAT Gateway, UDR
- 3.3.7 Private Link and internal load balancer patterns
- *Lab:* Apply NetworkPolicy to restrict pod-to-pod traffic and test isolation

### Module 3.4 — Ingress Controllers & Application Gateway (1 hr)
- 3.4.1 Ingress resource spec and IngressClass
- 3.4.2 NGINX Ingress Controller: installation via Helm, configuration
- 3.4.3 TLS termination and cert-manager for Let's Encrypt certificates
- 3.4.4 Application Gateway Ingress Controller (AGIC)
- 3.4.5 Azure Front Door integration patterns
- *Lab:* Configure NGINX Ingress with TLS and path-based routing for two services

### Module 3.5 — Persistent Storage on AKS (1.5 hrs)
- 3.5.1 Kubernetes storage concepts: StorageClass, PV, PVC, access modes
- 3.5.2 Container Storage Interface (CSI) driver architecture
- 3.5.3 Azure Disk CSI driver: LRS, ZRS, Premium SSD, Ultra Disk
- 3.5.4 Azure Files CSI driver: SMB and NFS, ReadWriteMany scenarios
- 3.5.5 Azure Blob storage CSI driver (NFS v3)
- 3.5.6 StatefulSet storage patterns with volumeClaimTemplates
- 3.5.7 Backup and restore with Velero + Azure Blob
- *Lab:* Deploy a PostgreSQL StatefulSet with persistent Azure Disk storage

### Module 3.6 — Day 3 Review & Q&A (1 hr)
- Networking decision flowchart
- Storage tier selection guide
- Architecture design challenge

---

## Day 4 — Observability, Security & Autoscaling

### Module 4.1 — Kubernetes Scheduling & Node Management (1 hr)
- 4.1.1 Scheduler algorithm: filtering and scoring
- 4.1.2 Node selectors and node affinity / anti-affinity
- 4.1.3 Pod affinity and anti-affinity rules
- 4.1.4 Taints and tolerations
- 4.1.5 Priority classes and preemption
- *Lab:* Use affinity rules to spread pods across availability zones

### Module 4.2 — Autoscaling on AKS (1.5 hrs)
- 4.2.1 Metrics Server: installation and metrics pipeline
- 4.2.2 Horizontal Pod Autoscaler (HPA): CPU, memory, custom metrics
- 4.2.3 Vertical Pod Autoscaler (VPA): Recommender, Updater, Admission Controller
- 4.2.4 KEDA: event-driven autoscaling with Azure Service Bus, Event Hubs, and HTTP
- 4.2.5 Cluster Autoscaler: scale-out and scale-in behaviour, expander strategies
- 4.2.6 Node Autoprovision (NAP) with Karpenter on AKS
- *Lab:* Configure HPA + Cluster Autoscaler and generate load to trigger scaling

### Module 4.3 — Monitoring with Azure Monitor & Container Insights (1.5 hrs)
- 4.3.1 Container Insights architecture: Managed Prometheus and Azure Monitor Agent
- 4.3.2 Configuring data collection rules (DCR)
- 4.3.3 Azure Managed Grafana: pre-built AKS dashboards
- 4.3.4 Log Analytics: table schemas (ContainerLog, KubePodInventory, Perf)
- 4.3.5 Writing KQL queries for cluster health, resource usage, and error detection
- 4.3.6 Alerts: metric alerts, log search alerts, and action groups
- 4.3.7 Distributed tracing with Azure Application Insights
- *Lab:* Build a custom Grafana dashboard and configure a pod restart alert

### Module 4.4 — Troubleshooting AKS (1 hr)
- 4.4.1 Systematic troubleshooting methodology
- 4.4.2 Pod failure patterns: CrashLoopBackOff, OOMKilled, Pending, ImagePullBackOff
- 4.4.3 Node-level debugging: node conditions, disk pressure, memory pressure
- 4.4.4 Networking diagnostics: DNS resolution, service endpoints, NetworkPolicy conflicts
- 4.4.5 Using `kubectl debug` with ephemeral containers
- 4.4.6 AKS Diagnostics and the `az aks kollect` command
- *Lab:* Diagnose and resolve a set of deliberately broken deployments

### Module 4.5 — AKS Security (2 hrs)
- 4.5.1 Azure Active Directory (Entra ID) integration and Kubernetes RBAC
- 4.5.2 ClusterRole, Role, ClusterRoleBinding, RoleBinding patterns
- 4.5.3 Workload identity: federated credentials replacing pod-managed identity
- 4.5.4 Pod Security Standards (Privileged, Baseline, Restricted) and Admission
- 4.5.5 Azure Policy for AKS: built-in initiatives and custom constraints
- 4.5.6 Image security: signed images, admission webhook, Notation + Ratify
- 4.5.7 Secrets encryption at rest with customer-managed keys
- 4.5.8 Microsoft Defender for Containers: runtime threat detection
- 4.5.9 CIS AKS Benchmark overview
- *Lab:* Configure Workload Identity for a pod to access Azure Key Vault without secrets

### Module 4.6 — Day 4 Review & Q&A (1 hr)
- Security hardening checklist
- Troubleshooting scenario competition
- Architecture review: multi-tenant AKS design

---

## Day 5 — CI/CD, GitOps & Capstone Project

### Module 5.1 — CI/CD Foundations for Containers (1 hr)
- 5.1.1 CI/CD pipeline stages for containerised workloads
- 5.1.2 Semantic versioning and image tagging strategies (commit SHA, semver, latest)
- 5.1.3 Deployment strategies: Recreate, Rolling, Blue/Green, Canary
- 5.1.4 Feature flags and progressive delivery concepts

### Module 5.2 — GitHub Actions for AKS (1.5 hrs)
- 5.2.1 GitHub Actions architecture: workflows, jobs, steps, runners
- 5.2.2 Azure Login action with OIDC federated credentials (no secrets)
- 5.2.3 Building and pushing images to ACR with `az acr build`
- 5.2.4 Deploying to AKS with `azure/aks-set-context` and `kubectl`
- 5.2.5 Using `KubernetesManifest` action for manifest substitution
- 5.2.6 Environment protection rules, approvals, and deployment history
- 5.2.7 Caching dependencies and parallelising jobs for speed
- *Lab:* Build a full GitHub Actions workflow: lint → build → push → deploy → smoke test

### Module 5.3 — Azure DevOps Pipelines for AKS (1.5 hrs)
- 5.3.1 Azure DevOps pipeline structure: stages, jobs, steps, templates
- 5.3.2 Service connections: Azure Resource Manager and Kubernetes
- 5.3.3 Variable groups, pipeline secrets, and Azure Key Vault linkage
- 5.3.4 Docker@2 and AzureCLI@2 tasks for image build and push
- 5.3.5 KubernetesManifest@1 task for deployment and rollback
- 5.3.6 Multi-stage pipelines with environment gates and approval policies
- 5.3.7 Reusable pipeline templates across repositories
- *Lab:* Create a multi-stage Azure DevOps pipeline with a manual approval gate before production

### Module 5.4 — GitOps with Flux v2 on AKS (1 hr)
- 5.4.1 GitOps principles: declarative, versioned, automated, continuously reconciled
- 5.4.2 Flux v2 architecture: Source, Kustomize, Helm, Notification controllers
- 5.4.3 Enabling Flux as an AKS extension (Azure Arc-enabled GitOps)
- 5.4.4 Bootstrapping Flux with a GitHub repository
- 5.4.5 Managing Helm releases and Kustomize overlays with Flux
- 5.4.6 Image Automation Controller for automated image tag updates
- 5.4.7 Multi-environment GitOps repository structure patterns
- *Lab:* Bootstrap Flux on AKS, commit a manifest change, and observe reconciliation

### Module 5.5 — Advanced Topics & Ecosystem (0.5 hr)
- 5.5.1 Service Mesh overview: Istio and Open Service Mesh on AKS
- 5.5.2 Helm: chart structure, templating, values files, repository management
- 5.5.3 Kubernetes Operators and the Operator pattern
- 5.5.4 Multi-cluster management with Azure Fleet Manager
- 5.5.5 AKS cost management: spot nodes, start/stop, right-sizing

### Module 5.6 — Capstone Project (2.5 hrs)
- **Objective:** Design, deploy, and operate a production-ready multi-tier application on AKS end to end
- 5.6.1 Project briefing and architecture design (teams of 2–3)
- 5.6.2 Containerise all application components with optimised Dockerfiles
- 5.6.3 Push images to ACR using ACR Tasks
- 5.6.4 Write all Kubernetes manifests (Deployments, Services, Ingress, PVC, HPA, Secrets via CSI)
- 5.6.5 Implement RBAC and Workload Identity for service authentication
- 5.6.6 Set up GitHub Actions or Azure DevOps pipeline for automated deployment
- 5.6.7 Configure monitoring alerts and at least one Grafana dashboard panel
- 5.6.8 Team presentations and peer review (10 min per team)

### Module 5.7 — Program Wrap-Up & Certification Guidance (0.5 hr)
- Key takeaways across all five days
- Recommended certifications: AZ-104, AZ-204, AZ-305, CKA, CKAD
- Further learning resources and community links
- Course feedback and close

---

---

*Azure Kubernetes Service — 40-Hour Training Program | Total: 40 hours across 5 days*
