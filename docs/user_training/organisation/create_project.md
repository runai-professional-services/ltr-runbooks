---
title: Configuring a Project
nav_order: 1
parent: Organisation
---

<span class="fs-3">
[Docs](https://docs.run.ai/v2.20/platform-admin/aiinitiatives/org/projects/?h=projects){: .btn }
</span>

<iframe src="https://scribehow.com/embed/Set_up_a_Project__prpLaxZaQMO8MgU0VtXzcA" width="100%" height="640" allowfullscreen frameborder="0"></iframe>
# Create organizational structure

*Hint - Use the official run:ai documentation 

## Create Departments

- Create two departments, each with a quota of 8 GPUs. 

## Create Projects

- Under Department A create three projects
- Divide the quota as you wish
- Under Department B create two projects


## Create Nodepools

- Create nodepool named h100 from one node
- Create nodepool named h200 from two nodes

## Edit the projects

The quotas are set only to default nodepool, we need to redistrbiute them.
- Allocate Quota for Department A's projects to nodepool h100
- Allocate Quota for Department B's projects to nodepool h200

*Note - Try using APIs to do it!
