---
title: Backup and Restore Configuration
nav_order: 3
parent: Installs and Upgrades
---

# Backup & Restore

### Backup cluster configurations

To backup Run:ai cluster configurations:

1. Run the following command to inspect our configuration:  

    ``` bash
    kubectl get runaiconfig runai -n runai -o yaml
    ```

2. Create a backup of the spec as follows:

    ```bash
    kubectl get runaiconfig runai -n runai -o yaml -o=jsonpath='{.spec}' > runaiconfig_backup.yaml
    ```

3. Once the `runaiconfig_back.yaml` back-up file is created, save the file externally, so that it can be retrieved later.

### Restore

The restore complex requires the existing cluster to be disconnected and uninstalled before backup. The process of cluster install must take place afresh, using the values saved to pass to the helm command. Refer to the documentation regarding how to do this. This is beyond the scope of today's training.

## Run:ai Control Plane

### Database Storage

Run:ai uses an internal PostgreSQL database. The database is stored on a Kubernetes *Persistent Volume* (PV). The 3 options available are to 

1. Create a pgdump of the PostgreSQL database as follows:

    ```bash
    kubectl -n runai-backend exec -it runai-backend-postgresql-0 \
      -- env PGPASSWORD=password \
      pg_dump \
      -U postgres \
      backend  \
      > cluster_name_db_backup.sql
    ```

2. Create a backup of the persistent volume itself

3. Use a 3rd party solution such as Velero

### Metrics Storage

Run:ai stores metric history using [Thanos](https://github.com/thanos-io/thanos). Thanos is configured to store data on a persistent volume. The recommendation is to back up the PV.

### Backing up Control-Plane Configuration

1. We will now back up the configuration of the control plane by saving the original values we used to install. In our case we did not modify much but we can back up those values by running:

    ```bash
    helm get values runai-backend -n runai-backend > cp_values.yaml
    ```

### Recovery

To recover Run:ai

* Re-create the Kubernetes cluster.
* Recover the persistent volumes for metrics and database.
* Re-install the Run:ai control plane. Use the additional configuration previously saved and connect to the restored PostgreSQL PV. Connect Prometheus to the stored metrics PV.
* Re-install the cluster. Add additional configuration post-install.  
