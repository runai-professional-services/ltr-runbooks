---
title: Configure The Admin CLI
nav_order: 2
parent: Platform Configuration
---

# Configuring the Administrator CLI

<span class="fs-3">
[Docs](https://docs.run.ai/latest/admin/config/cli-admin-install/){: .btn }
</span>

*Note - Always refer to documentation - this is just a students' guide*

## Pre-Reqs

Ensure the following pre-reqs are met

- Operating system: The CLI is supported on Mac and Linux
- Kubectl: The Kubernetes command-line interface must be installed and configured to access your cluster
- Cluster administrative permissions: The CLI requires a Kubernetes profile with administrative privileges

## Installation

Install the Admin CLI as follows:

```bash
# Download the binary
wget --content-disposition https://app.run.ai/v1/k8s/admin-cli/linux
# Make it executable
chmod +x runai-adm
# Move it to the path
sudo mv runai-adm /usr/local/bin/runai-adm
```

## Generate a logs tarball for Run AI support

```bash
runai-adm collect-logs
```
