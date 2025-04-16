---
title: Submit Various Workloads
nav_order: 2
parent: workloads
---

*Hint - Use the official run:ai documentation*

# Create environment
Create an environment for the following images

- quay.io/opendatahub-contrib/workbench-images:vscode-datascience-c9s-py311_2023c_latest

Check the port (Docker documentation)

- http://gcr.io/run-ai-demo/quickstart-fake

- gcr.io/run-ai-demo/quickstart-fake

## Launch interactive workloads

Under project A launch two interactive workloads

- VScode
- Jupyter

Which one is working as expected?

## Trainig workloads

- Edit the quota of project B to 2 gpus for nodepool h200
- Under Project B launch two training workloads with a single GPU (make sure they are using nodepool h200)
- Check the log of the workload, make sure they are running

- Launch an interactive workload with a single GPU on nodepool h200

*What will happen?*

- Launch an interacive workload with two GPUs

*What will happen?*

## CLIv2

Launch the same workloads using CLIv2. At least 

- Jupyter notebook
- Training workload with two GPUs

*Note - make sure you're using CLIv2!*


