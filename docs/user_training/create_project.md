---
title: Configuring Projects
nav_order: 1
parent: User Training
---

# Creating a New Project in Run: Step-by-Step Guide


1\. Navigate to the login page and log in with your credentials

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-03-14/d82e4b06-c98f-41b5-a05d-301349048a15/ascreenshot.jpeg?tl_px=206,497&br_px=1924,1458&force_format=jpeg&q=100&width=1120.0)


2\. The platform defaults to loading the analytics page. The first thing that we're going to do is look at our organization by clicking on this button in the left-hand menu.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-03-14/fa7c83d8-2368-4e5d-a68e-5777552b44dd/ascreenshot.jpeg?tl_px=0,0&br_px=2064,1153&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=1&wat_gravity=northwest&wat_url=https://colony-recorder.s3.amazonaws.com/images/watermarks/22C55E_standard.png&wat_pad=-4,208)


3\. You'll see here that we don't have any projects currently, so let's create one by clicking 'New Project.'

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-03-14/d7e5036a-a693-45f8-bcb3-7f589d831737/ascreenshot.jpeg?tl_px=0,0&br_px=2064,1153&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=1&wat_gravity=northwest&wat_url=https://colony-recorder.s3.amazonaws.com/images/watermarks/22C55E_standard.png&wat_pad=281,31)


4\. As for most operations in the platform, we need to select the "scope". In our case we'll select a cluster wide scope.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-03-14/83c596dc-c44e-45eb-8d20-d2885533a5c7/ascreenshot.jpeg?tl_px=799,0&br_px=2863,1153&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=1&wat_gravity=northwest&wat_url=https://colony-recorder.s3.amazonaws.com/images/watermarks/22C55E_standard.png&wat_pad=709,138)


5\. We need to add a name, which we'll call Project 1.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-03-14/863a51b1-59ab-4404-aeb2-b4fea9e4364b/ascreenshot.jpeg?tl_px=236,15&br_px=2301,1168&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=1&wat_gravity=northwest&wat_url=https://colony-recorder.s3.amazonaws.com/images/watermarks/22C55E_standard.png&wat_pad=524,276)


6\. A description is optional but useful for a busy environment.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-03-14/0dc4cd23-a7e1-4991-92d5-0e915edecf27/ascreenshot.jpeg?tl_px=452,153&br_px=2517,1306&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=1&wat_gravity=northwest&wat_url=https://colony-recorder.s3.amazonaws.com/images/watermarks/22C55E_standard.png&wat_pad=524,276)


7\. We'll allocate a quota of GPUs to that particular project. We've got plenty in our cluster, so we're going to add 4.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-03-14/fb40dc34-d435-4ceb-bef1-a582d9b79677/ascreenshot.jpeg?tl_px=634,762&br_px=2698,1916&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=1&wat_gravity=northwest&wat_url=https://colony-recorder.s3.amazonaws.com/images/watermarks/22C55E_standard.png&wat_pad=524,355)


8\. You'll see here that we have some scheduling rules which we can apply.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-03-14/8a502947-a252-4a49-a4be-bd2c04fc6d6c/ascreenshot.jpeg?tl_px=573,762&br_px=2637,1916&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=1&wat_gravity=northwest&wat_url=https://colony-recorder.s3.amazonaws.com/images/watermarks/22C55E_standard.png&wat_pad=268,417)


9\. The options are as follows:

- **Workload Duration (Time Limit):** Limits the total runtime of a workload, calculated from when it enters the *Running* state, with one rule allowed per workload type (Preemptive Workspaces, Non-preemptive Workspaces, and Training).
- **Idle GPU Time Limit:** Restricts the total idle GPU time of a workload based on the `runai_gpu_idle_seconds_per_workload` metric, requiring a shorter timeout than the workload duration rule for the same workload type.
- **Node Type (Affinity):** Specifies which nodes a workload can run on based on predefined labels (e.g., `run.ai/type = dgx200`), ensuring scheduling aligns with hardware or network requirements.

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-03-14/9e964359-03a1-4050-b231-65ec8d004a0e/ascreenshot.jpeg?tl_px=552,762&br_px=2616,1916&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=1&wat_gravity=northwest&wat_url=https://colony-recorder.s3.amazonaws.com/images/watermarks/22C55E_standard.png&wat_pad=524,515)


10\. Click "create project"

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-03-14/c6a5192f-aeb8-404e-ac60-3a98295a43da/ascreenshot.jpeg?tl_px=1154,762&br_px=3219,1916&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=1&wat_gravity=northwest&wat_url=https://colony-recorder.s3.amazonaws.com/images/watermarks/22C55E_standard.png&wat_pad=524,487)


11\. You'll notice here that the status goes to 'Creating.' And once complete, you can see that the status is 'Ready.'

![](https://ajeuwbhvhr.cloudimg.io/colony-recorder.s3.amazonaws.com/files/2025-03-14/60ae1774-1ed2-48e6-9e00-24b37c6c0e58/ascreenshot.jpeg?tl_px=0,0&br_px=2064,1153&force_format=jpeg&q=100&width=1120.0&wat=1&wat_opacity=1&wat_gravity=northwest&wat_url=https://colony-recorder.s3.amazonaws.com/images/watermarks/22C55E_standard.png&wat_pad=435,127)
#### [Made with Scribe](https://scribehow.com/shared/Creating_a_New_Project_in_Run_Step-by-Step_Guide__prpLaxZaQMO8MgU0VtXzcA)


