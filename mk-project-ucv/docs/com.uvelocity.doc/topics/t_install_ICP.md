# Installing on IBM Cloud Private

Install UrbanCode Velocity into a Kubernetes cluster on IBM Cloud Private \(ICP\).

The ID that you use must be able to make changes to the host environment. The tools required by all installation scenarios include the following items:

-   Docker. The commands used during installation retrieve files and container images from remote locations. If you are unable to access the internet during installation, the install images will need to have been previously downloaded and placed in a Docker repository that the installation commands can access.
-   IBM UrbanCode™ Deploy Version 6.2.3 and later. Although not strictly required, many UrbanCode™ Velocity features assume integration with UrbanCode Deploy. It doesn't matter which product you install first.

    If you are using an UrbanCode Deploy version prior to V6.2.5, you must install the patch located at the following website: [http://public.dhe.ibm.com/software/products/UrbanCode/plugins/ucsync/patches/ibmucd/](http://public.dhe.ibm.com/software/products/UrbanCode/plugins/ucsync/patches/ibmucd/). Select from the index the appropriate version that is installed on your computer.

    UrbanCode Velocity can connect to an UrbanCode Deploy server on the same network. If you install UrbanCode Velocity with Kubernetes, the Kubernetes cluster must be on the same network as the UrbanCode Deploy server.

-   Git and a GitHub account.

Before starting installation, ensure that the following applications are installed in the target environment:

-   Kubectl installed on the client
-   Helm v2.6.0 or later on client
-   [IBM Cloud Private account and a client instance ready to use](https://www.ibm.com/support/knowledgecenter/en/SSBS6K_3.1.1/installing/install_containers.html)

You will install UrbanCode Velocity into a Kubernetes cluster on IBM Cloud Private. The commands pull the UrbanCode Velocity node images from a GitHub repository and places them into the ICP clusters.

1.   Get an access key. 

    **Get an access key**. The access key enables you to complete installation. [Visit the UrbanCode Velocity web portal to obtain your key](https://uc-velocity.com/). After completing the form, you can copy the access key. Store the key in a readily-available location; you use it during installation.

    **Note:** Make sure that you select a key for the product version that you want to install. Keys for the Standard Edition do not work with the Community Edition and vice-versa.

2.   [Download the helm chart](https://github.com/IBM/velocity-se/releases/). The file name is velocity-1-1-0-helm.tgz 

    You can use a shell command to download the file. For example, if you are installing the product on Linux®, you can download the file with a command like this one:

    ```
    wget https://github.com/IBM/velocity-se/releases/velocity-1-1-0-helm.tgz
    ```

    .

3.   On you ICP Dashboard, select **Configure Client**, and then paste the provided Kubectl commands into a command shell on your client and run them. The Kubectl commands define your Kuberbetes context. Test the configuration by running the following commands:

    ```
    kubectl get nodes
            kubectl get pods --all-namespaces
    ```

    If you see messages like the following examples, your configuration is ready to use.

    ```
    10.134.119.132   Ready     <none>    151d      v1.10.0+icp-ee
    10.134.119.24    Ready     <none>    151d      v1.10.0+icp-ee
    10.134.119.65    Ready     <none>    151d      v1.10.0+icp-ee
    10.134.119.9     Ready     <none>    151d      v1.10.0+icp-ee
    ```

4.   On ICP dashboard, click **Manage** \> **Namespaces** \> **Create Namespace** \> ****, and enter a name for the name space. 
5.   Create MongoDB in the new namespace by completing the following steps: 
    1.   On the ICP dashboard, select **Catalog** \> **ibm-mongodb-dev**. 
    2.   On the ibm-mongodb-dev page, select **Configure**, and then, from the **Target namespace** list, select the namespace you created earlier. 
    3.   Complete configuration by entering a release name, and password for the MongoDB admin user, and then click **Install**. This creates a persistent volume claim.
6.   Click **Platform** \> **Storage** \> ****, and then create a persistent volume for your claim by completing the following steps: 
    1.   On Storage page, click **Create Persistent Volume**. 
    2.   On the Create Persistent Volume window, enter a name for the volume. 
    3.   Turn **JSON mode ON**. The underlying JSON file for the persistent volume is displayed. In the JSON script for the `NFS` object, and specify the server's IP address, and the path for the new volume. The following code snippet illustrates a typical example:

        ```
         "nfs": {
              "server": "ip\_address",
              "path": "/volume\_path"
            },
        ```

    4.   Click **Create**. In the Storage window, check for the status of `Bound` for the new volume.
    5.   In a command shell on the client, use the following kubectl command to check pod status: `kubectl get pods -n persistentVolume\_name.` 
7.   Grant additional permissions to the MongoDB user by completing the following steps: 
    1.   Using a client command shell, logon to the pod as the admin user. 
    2.   Use the following command to grant additional permissions: 

        ```
        db.grantRolesToUser( "mongo", ["readWriteAnyDatabase", "dbAdminAnyDatabase", "clusterAdmin"]  )
        ```

        If the command fails, an error message is displayed.

    3.   If no message is displayed, type `exit` to leave the pod. 
8.   Using a client command shell, type `kubectl get services -n namespace` to display the MongoDB service. Te service name is the host name for the MongoDB service.
9.   Determine the configuration properties to specify. You can customize the installation by specifying configuration properties on the helm install command. 

    Some of the properties that you specify are dependent on your environment. However, there are several properties that must be specified. Below are the required properties.

    -   **access.key**

        The product access key obtained from Passport Advantage.

    -   **url.domain**

        The host name must resolve to a name on your DNS server, or in the server's hosts file. On Linux, the file location is etc/hosts; on Windows, the location is C:\\Windows\\System32\\drivers\\etc\\hosts.

    -   **mongo.url**

        The URL of the MongoDB. Specify the following parameters.

        -   **username**

            The user ID to authenticate with the MongoDB database.

        -   **password**

            The associated password to authenticate with the MongoDB database.

        -   **port**

            The port number for the MongoDB database. Use the value shown in the example, which is 27017.

        -   **service\_name**

            The MongoDB service name you retrieved in Step 8.

        **Note:** If you used the install command in the previous step to install the MongoDB, use the following values for the **mongo.url** property.

        ```
        mongodb://mongo:mongo@velocity-mongo-ibm-mongodb-dev:27017/admin
        ```

        If you use the default IBM MongoDB, make sure to grant the MongoDB user full write privileges.

    -   **name**

        The name space where the Helm chart is applied, and the name of Helm chart.

        ```
        --name standard ./velocity-1-1-0-helm.tgz
        ```

10.  Run the `helm install` command to install the UrbanCode Velocity images into ICP. The following example shows the a typical configuration properties: 

    ```
    
    helm install \
    --set access.key=my\_access\_key \
    --set url.domain=my\_hostname \
    --set mongo.url=mongodb://mongo:mongo@mongodb-servicename:27017/admin \
    --set url.protocol=https \
    --set ui.service.externalPort=80 \
    --set ingress.enable=true \
    --name standard ./velocity-1-1-0-helm.tgz
    ```


Access UrbanCode Velocity at the URL you specified in the helm chart. You can refresh the status display by using the following kubectl command: `kubectl get pods`. The default admin user name is admin and the default password is admin.

**Parent topic:** [Installation roadmap](../topics/c_install_se_roadmap.md)

