---
title: Architecture
parent: Architecture
nav_order: 1
---

## Learn to Run - System Architecture - Microservices

### Control Plane Micro-services

| Micro-service             | Function / Business Objects                                                                                             |
|---------------------------|--------------------------------------------------------------------------------------------------------------------------|
| assets-service            | Manages environments, compute resources, data sources and credentials                                                   |
| audit service             | Audit log support                                                                                                       |
| authorization             | Responsible for the RBAC configuration and helps all other services to enforce it.                                     |
| backend (deprecating)     | Manages projects, departments, node pools; backward compatibility (e.g. jobs); all /v1/k8s REST APIs                     |
| cli-exposer (2.18+)       | Responsible for installation, download binaries for CLI (v2) & documentation                                           |
| cluster-service           | Cluster status and configuration                                                                                        |
| data-volume-service       | Manages data volume creation, sharing & deletion                                                                        |
| db-mechanic (deprecating) | Upgrade of database for older “backend” service                                                                         |
| email-service             | Sends notifications                                                                                                     |
| frontend                  | Web UI                                                                                                                  |
| identity-manager          | Manages identities by configuring Keycloak                                                                              |
| k8s-objects-tracker       | Manages the list of objects in the cluster (pvc, secrets, configmaps, storageclasses)                                  |
| metrics-service           | Unified internal API for querying time-series databases (Mimir, Thanos, Grafana Cloud)                                 |
| notifications-service     | Manages notifications configuration & sends notifications via email-service                                            |
| org-unit-service (2.18+)  | Managing projects and departments                                                                                       |
| policy-service            | Manages workload policies                                                                                               |
| presets-loader            | Imports assets for all tenants (environments, models)                                                                   |
| tenants-manager           | Manages tenants from creation to deletion (future)                                                                      |
| trial-service             | Manages trial accounts (uses tenant manager)                                                                            |
| workloads-helper (2.18+)  | Helps workloads perform actions (e.g., hard delete, send notifications)                                                 |
| workloads-service         | Manages workloads from creation to deletion                                                                             |

---

### Cluster Micro-services

| Micro-service                   | Function / Business Objects                                                                                         |
|----------------------------------|----------------------------------------------------------------------------------------------------------------------|
| accessrule-controller           | Manages role bindings to match RBAC rules in the CP                                                                  |
| admission-controller            | Runs Run:ai validation and mutation webhooks on the API server                                                       |
| runai-agent                     | Pulls configuration from the CP and creates matching custom resources                                                |
| assets-sync                     | Creates K8s objects (PVCs, secrets) in cluster matching CP assets                                                    |
| binder                          | Performs scheduling decisions asynchronously                                                                         |
| cluster-api (2.18+)             | Enables CLI v2 features via API (attach, port forward, exec, etc.)                                                  |
| cluster-installer               | Runs installation of the operator                                                                                   |
| cluster-sync                    | Reports resource status from the cluster to CP                                                                       |
| crd-upgrader                    | Updates when CRDs are changed                                                                                        |
| engine-operator                 | Sets up scheduling containers                                                                                        |
| external-workload-integrator   | Detects and interprets non-Run:ai workloads                                                                          |
| go-operator                     | Manages Run:ai components and configuration                                                                          |
| inference workload controller   | Manages inference workloads                                                                                          |
| init-ca                         | Creates credentials for Run:ai                                                                                       |
| metrics-exporter                | Exports Run:ai metrics to Prometheus                                                                                 |
| mig-parted (deprecated)         | Dynamic MIG support                                                                                                  |
| nodepool-controller             | Manages scheduler instances and node pool labeling                                                                   |
| pod-grouper                     | (No description provided)                                                                                            |
| podgroup-assigner               | Assigns workloads to valid nodepools                                                                                 |
| project-controller              | Manages projects/departments, queues, and shared assets                                                              |
| queue-controller                | Publishes queue status, converts between CRD versions                                                                |
| researcher-service              | Handles cluster API, authentication, authorization                                                                   |
| runai-admission-controller      | (No description provided)                                                                                            |
| runai-container-toolkit         | Manages swap, fractions, etc.                                                                                        |
| runai-node-exporter             | Exports fractions-related metrics                                                                                    |
| runai-container-runtime-installer | Installs runtime hooks for fractional pods with PSA restrictions                                                  |
| runai-oauth2-proxy              | Authenticates workspace apps (e.g., Jupyter)                                                                         |
| runaijob-controller             | Manages pods for interactive/training workloads                                                                      |
| scheduler                       | The Run:ai scheduler                                                                                                 |
| shared-objects-controller       | Manages data volume replication in the cluster                                                                       |
| status-updater                  | Updates pod group status                                                                                             |
| workload-controller             | Manages workload jobs, ingress, and authentication                                                                   |
| workload-overseer               | Deletes workloads based on TTL, inactivity, preemption                                                               |
| node-scale-adjuster             | Triggers autoscaler/Karpenter to add nodes for fractions                                                             |
| pod-group-controller            | Publishes podgroup resource status                                                                                   |
