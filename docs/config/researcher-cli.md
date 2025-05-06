---
title: Configure The Researcher CLI
nav_order: 4
parent: Platform Configuration
---

# Configuring the Researcher CLI

<span class="fs-3">
  <a href="https://docs.run.ai/latest/Researcher/cli-reference/new-cli/overview/" class="btn" target="_blank" rel="noopener">Docs</a>
</span>

*Note - Always refer to documentation - this is just a students' guide*

## Pre-Reqs

Ensure the following pre-reqs are met

- Kubectl: The Kubernetes command-line interface must be installed and configured to access your cluster
- Cluster administrative permissions: The CLI requires a Kubernetes profile with administrative privileges

Under General settings → Workloads, enable the flag Improved command line interface

## Installing the CLI

- Click the Help (?) icon in the top right corner
- Select Researcher Command Line Interface
- Select the cluster you want the CLI to communicate with
- Select your "Linux" operating system
- Copy the installer command and run it in the terminal
- Follow the installation process instructions
- Click Enter to use the default values (recommended)

## Testing the installation

- Copy the binary to your path, ie:

```bash
sudo cp ~/.runai/bin/runai /usr/local/bin/runai
```

## Log into the platform

```bash
runai login remote-browser
```

- Copy and paste the link into your browser to retrieve the token. Paste back into terminal

## To verify the CLI client was installed properly

- Open the terminal
- Run the command `runai version`
