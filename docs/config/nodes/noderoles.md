---
title: Set Node Roles
parent: Nodes and Nodepools
nav_order: 1
---

## Learn to Run - Platform Configuration - Set Node Roles

#### The following node roles can be configured on the cluster:

1. System node: Reserved for Run:ai system-level services.

2. GPU Worker node: Dedicated for GPU-based workloads.

3. CPU Worker node: Used for CPU-only workloads.

#### Pre-reqs

1. Ensure that scheduling restrictions are enabled in the cluster.

Edit the runaiconfig file to set global.nodeAffinity.restrictScheduling to true.

```bash
kubectl edit runaiconfig runai -n runai
# Add the following field:
#     global.affinity.nodeAffinity.restrictScheduling: true
```

1. Label the node to reflect the role:

```bash
# List the nodes
kubectl get nodes
# Choose our node to restrict to CPU only workloads
kubectl label nodes <node-name> node-role.kubernetes.io/runai-cpu-worker=true
```

2. Check the label has stuck:

```bash
kubectl get no <node-name> --show labels
```

3. Reset the label:

```bash
kubectl label node <node-name> node-role.kubernetes.io/runai-cpu-worker-
```
