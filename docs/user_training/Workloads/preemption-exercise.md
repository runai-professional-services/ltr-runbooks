---
title: Pre-Emption
nav_order: 7
parent: Workloads
---

# Pre-emption

When a workload is running over-quota, it is liable to pre-emption. We can demonstrate that with this simple exercise

#### Environment

1. Clear the platform of all existing workloads and projects

2. Set up a nodepool on a single node. It should therefore have 8 GPUs allocated to it

3. Set up 2 x projects; project-a and project-b and allocate each a quota of 4 x GPUs but only within the nodepool on the single node

4. Create a new training workload with a request for 8 GPUs

5. Spin up the workload and observe the events and metrics. It should run with a full allocation of 8, even though the project quota is only 4.

**The workload is now said to be running `over quota`**

6. Set up a Jupyter notebook in project-b. Note that project-b has an allocation of 4 GPUs but isn't using anything currently. Out of fairness, that workload should be able to run

7. Observe the training workload go into a `Pending` state as it gets pre-empted

8. Observe the interactive workload now in a running state. The training workload was successfully `pre-empted`.

9. Now shut down the Jupyter notebook and observe how the scheduler now brings the training workload back on load.

10. Explore the dashboards throughout and familiarise yourself with how quotas and utilisation are laid out
    

