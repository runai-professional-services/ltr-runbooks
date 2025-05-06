---
title: Upgrading Run AI
nav_order: 1
parent: Installs and Upgrades
---

# Upgrading The Cluster

<span class="fs-3">
  <a href="https://docs.run.ai/latest/admin/runai-setup/self-hosted/k8s/upgrade/" class="btn" target="_blank" rel="noopener">Docs</a>
</span>

*Note - Always refer to documentation - this is just a students' guide*

## Pre-Reqs

### Set some ENVs for your cluster

- Set your domain

```bash
export MY_DOMAIN="[your_name].runailabs-cs.com"
```

### Connect to your lab

- SSH into your lab with the provided key

```bash
ssh -i /my/key $MY_DOMAIN
```

- Change to the Artifacts directory

```bash
cd Artifacts
```

### Back up your `runai-backend` values

- Recover values with helm:

```bash
helm get values runai-backend -n runai-backend > runai_control_plane_values.yaml
```

- Run the upgrade to the new version

```bash
helm upgrade runai-backend -n runai-backend runai-backend/control-plane \
    --version "~2.21" -f runai_control_plane_values.yaml --reset-then-reuse-values
```

## Observe the Backend Pods

- In your terminal, launch K9S

```bash
k9s
```

- Set the namespace

```bash
:ns # [enter]
# use arrow keys to select runai-backend [enter]
```

### Install the Cluster

- When all pods are healthy in the `runai-backend` namespace:
  - Go to the Resources / Clusters page
  - Check the box next to the cluster you want to upgrade and select "GET INSTALLATION INSTRUCTIONS"
  - Deploy to the same cluster as the control plane and set relevant matching version
  - Copy the installation instructions to deploy
  - Click "done"

## Observe the Cluster Pods

- In your terminal, launch K9S

```bash
k9s
```

- Set the namespace

```bash
:ns # [enter]
# use arrow keys to select runai [enter]
```

### Check for the correct nodes and GPUs

- Check the Resources / Clusters tab to ensure both the backend and cluster are at the correct version
- Visit the nodes and page to ensure that all expected GPUs are registered
- View the dashboards to ensure that metrics are working as expected
