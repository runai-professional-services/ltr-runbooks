---
title: Upgrading Run AI
nav_order: 1
parent: Installs and Upgrades
---

# Upgrading The Cluster

<span class="fs-3">
[Docs](https://docs.run.ai/v2.20/admin/runai-setup/self-hosted/k8s/upgrade/){: .btn}
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
        --version "~2.20.0" -f runai_control_plane_values.yaml --reset-then-reuse-values
    ```

- Observe the upgrade to the runai-backend namespace with K9S

### Install the Cluster

- When all pods are healthy in the `runai-backend` namespace:
  - Go to the clusters page
  - Deploy to the same cluster as the control plane and set relevant matching version
  - Copy the installation instructions to deploy
  - Click "done"
  - Wait for the cluster to connect
  - **HINT** Watch the runai namespace using K9S to see the build

### Check for the correct nodes and GPUs

- Visit the nodes and page to ensure that all expected GPUs are registered
- View the dashboards to ensure that metrics are working as expected