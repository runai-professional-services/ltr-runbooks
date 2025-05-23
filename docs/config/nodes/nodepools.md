---
title: Create Nodepools
parent: Nodes and Nodepools
nav_order: 2
---

## Learn to Run - Platform Configuration - Create Node Pools

#### Generate a new nodepool

1. Create your own custom label on the chosen node / nodes:

```bash
kubectl get nodes --show labels
kubectl label node <node name> my-nodepool=true
```

#### Set up the nodepool

1. Log into the Run AI platform in a web browser

2. Go to Resources / Node pools

3. Click on `CREATE NODE POOL` and assign to the new nodepool with the label

4. Wait for the nodepools to become ready and check which nodes belong to which
