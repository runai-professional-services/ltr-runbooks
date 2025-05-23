---
title: Assets
nav_order: 1
parent: Workloads
---

# Understanding Assets

Assets are the building blocks of any workload

#### Environment

1. Create a new environment for an unsupervised learning workload

2. Set the scope for your project and name the environment

3. Select Standard and Training for the workload types

4. Set the image URL to learntorun/dummy-workload

5. Create the workload

#### Compute Resource

1. Generate a new compute resource to consume 2/10 of a GPU

2. Select cluster wide scope

#### Data Source

##### Create a PVC

1. Create a new PVC data source by naming it and selecting project scope

2. Use our standard storage class 

3. Access mode should be set to RW by 1 node

4. Set the size to 5GB

5. Set the mount path to /mnt/my-data

##### Create a GitHub data source

1. Visit the github repo [here](https://github.com/plotly/datasets)

2. Note the URL of the root repo and copy to the clipboard

3. Configure a new datasource, pasting the URL into the origin section.

4. Choose a container mounting point for the dataset - /mnt/datasets

##### Credentials

If credentials are required for any service interaction they may be added here and referenced in the workload definition pages. Note that this includes generic secrets, username / password, docker registry and key storage.