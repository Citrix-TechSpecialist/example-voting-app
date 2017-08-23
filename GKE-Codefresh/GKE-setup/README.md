### Quickstart for Google Container Engine

logon to GCE console from [https://console.cloud.google.com](https://console.cloud.google.com). 

Use Google Cloud Shell to interact with `kubectl` immediately, use the Google Cloud Shell, which comes preinstalled with the `gcloud` and `kubectl` command-line tools. Follow these steps to launch the Google Cloud Shell:

![Google Cloud Shell](img/shell_icon.png?raw=true)

Go to [Google Cloud Platform Console](https://console.cloud.google.com/?_ga=1.126719242.621469569.1491942438). Click the **Activate Google Cloud Shell** button at the top of the console window. A Cloud Shell session opens inside a new frame at the bottom of the console and displays a command-line prompt.

![Google Cloud Platform console](img/new-console.png?raw=true)


Set a default [Compute Engine zone](https://cloud.google.com/compute/docs/zones#available). The following command sets the default zone as `us-central1-b`: 

    gcloud config set compute/zone us-central1-b

You can view your defaults in the `gcloud` command-line tool by running the following command: 

    gcloud config list

### Provision a Kubernetes Cluster
First Set a default [Compute Engine zone](https://cloud.google.com/compute/docs/zones#available). The following command sets the default zone as `us-central1-b` in Google Cloud Shell. 

    gcloud config set compute/zone us-central1-b

 Next, create a new project named `cpx-project` by y clicking "CREATE PROJECT" under "All Projects"

![](img/create-project.png?raw=true)
 
 Under **Home**   
![](img/home.png?raw=true) 

click on **Go to APIs overview**

![](img/APIs.png?raw=true)  

and click on **Enable API.**

![](img/enable-api.png?raw=true)

and then navigate to **Container Enginer API.**

![](img/container-engine-api.png?raw=true)  

And then click **Enable**

![](img/enable-api-1.png?raw=true)

You may have to wait a few moments until the Google Cloud Shell recognizes the enabled API setting. To create a cluster enter the following in Google Cloud Shell. This step can take a few minutes to complete

    gcloud container clusters create cpx-demo

Under Google Compute Engine, you can see your virtual machines that make up your kube cluster be provisioned. 

![](img/vm-instances.png?raw=true) 

Ensure kubectl has authentication credentials. Agree and follow the instructions to retrieve the validation code. 

    gcloud auth application-default login

Enter the following to validate kubectl is working properly:

    kubectl version   
    kubectl cluster-info  
    kubectl get nodes 

