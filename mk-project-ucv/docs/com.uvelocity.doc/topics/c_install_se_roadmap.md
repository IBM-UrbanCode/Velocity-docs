# Installation roadmap

The installation roadmap is a description of the high-level steps for installing UrbanCode™ Velocity.

UrbanCode Velocity is provided in two versions. The full-featured Standard Edition \(SE\) is free to use for 60 days, at which time you need a license. [You can also install the free-to-use Community Edition \(CE\)](../../com.insights.doc/topics/c_install_roadmap.md#), which contains many UrbanCode Velocity features.

Both editions of consist of services and other tools that are stored in Docker containers. You can install the containers in one of the container orchestrators, such as Docker Compose, Kubernetes, or any environment that supports the container orchestrators, including bare-metal servers and cloud-based platforms, such as the environments listed here:

-   Windows
-   Linux
-   MacOS
-   IBM Cloud Private
-   IBM Cloud services
-   OpenShift

Both editions require an access key. You apply the free access key during installation. When you license the SE version, in addition to you license key, your receive a permanent access key.

If you are evaluating UrbanCode Velocity and are unsure about which versions to install, many users find the Docker Compose installation process to be easiest because it is the most automated.

In outline, the installation process consists of the following general steps:

1.  **Review the system requirements**

    The ID that you use must be able to make changes to the host environment. The tools required by all installation scenarios include the following items:

    -   Docker. The commands used during installation retrieve files and container images from remote locations. If you are unable to access the internet during installation, the install images will need to have been previously downloaded and placed in a Docker repository that the installation commands can access.
    -   IBM UrbanCode™ Deploy Version 6.2.3 and later. Although not strictly required, many UrbanCode Velocity features assume integration with UrbanCode Deploy. It doesn't matter which product you install first.

        If you are using an UrbanCode Deploy version prior to V6.2.5, you must install the patch located at the following website: [http://public.dhe.ibm.com/software/products/UrbanCode/plugins/ucsync/patches/ibmucd/](http://public.dhe.ibm.com/software/products/UrbanCode/plugins/ucsync/patches/ibmucd/). Select from the index the appropriate version that is installed on your computer.

        UrbanCode Velocity can connect to an UrbanCode Deploy server on the same network. If you install UrbanCode Velocity with Kubernetes, the Kubernetes cluster must be on the same network as the UrbanCode Deploy server.

    -   Git and a GitHub account.
    You can dynamically generate a system requirements report using the [Software Product Compatibility Reports \(SPCR\)](https://www.ibm.com/software/reports/compatibility/clarity/index.html) tool.

2.  **Install UrbanCode Velocity for your target environment:**

    [Installing UrbanCode Velocity with Docker Compose](t_install_se_docker.md#).

    [Installing into a Kubernetes cluster](t_install_se_kubernetes.md#).

    [Installing as an OpenShift application](t_install_se_openShift.md#)

    [Installing on IBM Cloud Private](t_install_ICP.md#)

3.  **Integrate with external tools**

    After the installation is complete, you can access the configuration pages to integrate with [UrbanCode Deploy](t_integration_UCD.md#) and other external tools, such as [Jenkins](t_integration_Jenkins.md#). Only sample report data is available until the integration process is complete.

4.  **Authenticate users**

    After the installation is complete, you can [authenticate users](t_admin_authentication.md#). Authenticating users to access reports is not required. However; until users are authenticated, only the administrator user has access to reports and product features.


-   **[Installation roadmap](../topics/c_install_se_roadmap.md)**  
The installation roadmap is a description of the high-level steps for installing UrbanCode Velocity.
-   **[Installing UrbanCode Velocity with Docker Compose](../topics/t_install_se_docker.md)**  
Install UrbanCode Velocity into the Docker Compose container orchestrator.
-   **[Installing on Minikube](../topics/t_install_minikube.md)**  
You can install UrbanCode Velocity onto a Minikube cluster on your local machine.
-   **[Installing on IBM Cloud Private](../topics/t_install_ICP.md)**  
Install UrbanCode Velocity into a Kubernetes cluster on IBM Cloud Private \(ICP\).
-   **[Installing as an OpenShift application](../topics/t_install_se_openShift.md)**  

-   **[Uninstalling the server](../topics/t_install_se_remove_ucv.md)**  
You can uninstall UrbanCode Velocity by stopping the server and removing the product containers.

**Parent topic:** [Installation roadmap](../topics/c_install_se_roadmap.md)

