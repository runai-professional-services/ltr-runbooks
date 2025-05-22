[](https://github.com/run-ai/docs/edit/master/docs/Researcher/workloads/training/standard-training/quickstart-standard-training.md "Edit this page")

This article provides a step-by-step walkthrough for running a standard training workload.

A training workload contains the setup and configuration needed for building your model, including the container, images, data sets, and resource requests, as well as the required tools for the research, all in a single place.

Prerequisites
-------------------------------------------------

Before you start, make sure:

*   You have created a project or have one created for you.
*   The project has an assigned quota of at least 1 GPU.

Step 1: Logging in
----------------------------------------------------------

User InterfaceCLI V2CLI V1 (Deprecated)API

Browse to the provided Run:ai user interface and log in with your credentials.

Run the below --help command to obtain the login options and log in according to your setup:

Log in using the following command. You will be prompted to enter your username and password:

To use the API, you will need to obtain a token. Please follow the API authentication article.

Step 2: Submitting a standard training workload
--------------------------------------------------------------------------------------------------------------------

User InterfaceCLI V2CLI V1 (Deprecated)API

1.  Go to the Workload manager → Workloads
2.  Click **+NEW WORKLOAD** and select **Training**
3.  Select under which **cluster** to create the workload
4.  Select the **project** in which your workload will run
5.  Under **Workload architecture**, select **Standard**
6.  Select a preconfigured template or select the **Start from scratch** to launch a new workload quickly
7.  Enter a **name** for the standard training workload (if the name already exists in the project, you will be requested to submit a different name)
8.  Click **CONTINUE**
9.  Click **+NEW ENVIRONMENT**
    
    a. Enter **quickstart** as the name
    
    b. Enter **runai.jfrog.io/demo/quickstart** as the **Image URL**
    
    c. Click **CREATE ENVIRONMENT**
    
10.  Select the **‘one-gpu’** compute resource for your workload (GPU devices: 1)
    
    *   If the ‘one-gpu’ is not displayed in the gallery, follow the step-by-step guide:
    
    Create a one-gpu compute resource
    
    1.  Click **+NEW COMPUTE RESOURCE**
    2.  Enter a **name** for the compute resource. The name must be unique.
    3.  Set **GPU devices per pod - 1**
    4.  Set **GPU memory per device**
        
        *   Select **% (of device)** - Fraction of a GPU device’s memory
        *   Set the memory **Request** - 100 (The workload will allocate 100% of the GPU memory)
    5.  Optional: set the **CPU compute per pod** - 0.1 cores (default)
        
    6.  Optional: set the **CPU memory per pod** - 100 MB (default)
    7.  Click **CREATE COMPUTE RESOURCE**
    
    *   The newly created one-gpu compute resource will be selected automatically
11.  Click **CONTINUE**
    
12.  Click **CREATE TRAINING**
    
    After the standard training workload is created, it is added to the workloads table.
    

Copy the following command to your terminal. Make sure to update the below with the name of your project and workload:

```
runai project set "project-name"
runai training submit "workload-name" -i runai.jfrog.io/demo/quickstart -g 1

```


This would start a standard training workload based on a sample docker image, runai.jfrog.io/demo/quickstart, with one GPU allocated.

Copy the following command to your terminal. Make sure to update the below with the name of your project:

```
runai config project "project-name"  
runai submit "workload-name" -i runai.jfrog.io/demo/quickstart -g 1

```


This would start a standard training workload based on a sample docker image, runai.jfrog.io/demo/quickstart, with one GPU allocated.

Copy the following command to your terminal. Make sure to update the below parameters according to the comments. For more details, see Trainings API reference:

```
curl -L 'https://<COMPANY-URL>/api/v1/workloads/trainings' \ 
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <TOKEN>' \
-d '{ 
    "name": "workload-name", 
    "projectId": "<PROJECT-ID>",
    "clusterId": "<CLUSTER-UUID>",
    "spec": {  
       "image": "runai.jfrog.io/demo/quickstart", 
       "compute": { 
       "gpuDevicesRequest": 1
       } 
    } 
}

```


1.  `<COMPANY-URL>` is the link to the Run:ai user interface.
2.  `<TOKEN>` is the API access token obtained in Step 1.
3.  `<PROJECT-ID>` is #The ID of the Project the workload is running on. You can get the Project ID via the Get Projects API Get Projects API.
4.  `<CLUSTER-UUID>` is the unique identifier of the Cluster. You can get the Cluster UUID by adding the "Cluster ID" column to the Clusters view.

This would start a standard training workload based on a sample docker image, runai.jfrog.io/demo/quickstart, with one GPU allocated.

Note

The above API snippet will only work with Run:ai clusters of 2.18 and above.

Next Steps
-------------------------------------------

*   Manage and monitor your newly created workload using the workloads table.
*   After validating your training performance and results, deploy your model using inference.