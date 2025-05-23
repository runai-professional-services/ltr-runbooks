---
title: Create an Interactive Workload
nav_order: 5
parent: Workloads
---

# Create an Interactive Workload

1. Now that we created our assets, we can build a robust interactive workload - in this case with jupyter

2. Select `New Workload` `Workspace` and ensure the correct cluster is selected

3. Select the project and use a `Start from Scratch` template

4. Name and continue

5. Select Jupyter-lab as the env't

6. Choose a `small-fraction` compute resource

7. Under `Data Sources`, select both of our data sources we created in previous steps

8. Create the Workspace

9. As the Workload builds, select it and view `SHOW DETAILS` to view events

10. Connect to the workload by selecting it and clicking `CONNECT`

11. Select `Terminal` and navigate to the mountpoint (/mnt) to observe our cloned GitHub data

12. Check to see our PVC is also mounted there

13. Generate a new ipykernel and run some code!
