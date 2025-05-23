---
title: Configuring Organisational Structure 
nav_order: 2
parent: Organisation
---

# Create Organisational structure

*Hint - Use the official run:ai documentation*

## Create Departments

- In the Admin / Resources dropdown, ensure Departments are enabled
- Create two departments, each with a quota of 8 GPUs.

## Create Projects

- Under Department A create three projects
- Divide the quota as you wish
- Under Department B create two projects

## Create access rules

- Create a Department Admin role for each department - the username is your nvidia email and another name (can be whatever you wish)
- Create Researcher L1 that has a permission to one project - use any name you wish
- Save the first one time password for later

## Create Nodepools

- Create nodepool named h100 from one node
- Create nodepool named h200 from two nodes

## Edit the projects

The quotas are set only to default nodepool, we need to redistrbiute them.
- Allocate Quota for Department A's projects to nodepool h100
- Set the priority of h100 as 1 and h200 nodepool as 2

- Allocate Quota for Department B's projects to nodepool h200
- Set the priority of h200 as 1 and h100 nodepool as 2

*Note - Try using APIs to do it*
