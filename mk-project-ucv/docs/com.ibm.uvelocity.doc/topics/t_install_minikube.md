# Installing on Minikube

You can install UrbanCode Velocity onto a Minikube cluster on your local machine.

The ID that you use must be able to make changes to the host environment. The tools required by all installation scenarios include the following items:

-   Docker. The commands used during installation retrieve files and container images from remote locations. If you are unable to access the internet during installation, the install images will need to have been previously downloaded and placed in a Docker repository that the installation commands can access.
-   IBM UrbanCode™ Deploy Version 6.2.3 and later. Although not strictly required, many UrbanCode™ Velocity features assume integration with UrbanCode Deploy. It doesn't matter which product you install first.

    If you are using an UrbanCode Deploy version prior to V6.2.5, you must install the patch located at the following website: [http://public.dhe.ibm.com/software/products/UrbanCode/plugins/ucsync/patches/ibmucd/](http://public.dhe.ibm.com/software/products/UrbanCode/plugins/ucsync/patches/ibmucd/). Select from the index the appropriate version that is installed on your computer.

    UrbanCode Velocity can connect to an UrbanCode Deploy server on the same network. If you install UrbanCode Velocity with Kubernetes, the Kubernetes cluster must be on the same network as the UrbanCode Deploy server.

-   Git and a GitHub account.

In addition to the requirements for all installation scenarios, the following items are required for Minikube installation:

-   Minikube installed onto a hypervisor appropriate for your operating system. On Linux you might use Oracle Virtual Box; on Windows you might use Hyper-V.
-   The CLI that is used for both Minkube and Kubernetes, Kubectl, installed and configured.
-   Helm v2.6.0 or later.
-   MongoDB database installed on your Minikube instance with a persistent volume. Instructions for installing MongoDB are provided below.
-   Add the Minikube IP address to your hosts file and assign a host name to it. Kubernetes requires a host name rather than a simple IP address. On Linux, the file location is etc/hosts; on Windows, the location is C:\\Windows\\System32\\drivers\\etc\\hosts.

You will install the product into MiniKube cluster using Helm commands. The commands pull the UrbanCode Velocity node images from a GitHub repository and places them into the cluster defined in Helm charts.

1.   Get an access key. 

    The access key enables you to complete installation. [Visit the UrbanCode Velocity web portal to obtain your key](https://uc-velocity.com/). After completing the form, you can copy the access key. Store the key in a readily-available location; you use it during installation.

    **Note:** Make sure that you select a key for the product version that you want to install. Keys for the Standard Edition do not work with the Community Edition and vice-versa.

2.   [Download the helm chart](https://github.com/IBM/velocity-se/releases/). The file name is velocity-1-1-0-helm.tgz 

    You can use a shell command to download the file. For example, if you are installing the product on Linux®, you can download the file with a command like this one:

    ```
    wget https://github.com/IBM/velocity-se/releases/velocity-1-1-0-helm.tgz
    ```

    .

3.   If you do not have a MongoDB database installed, install one now. Follow the instructions at the [MongoDB](https://github.com/kubernetes/charts/tree/master/stable/mongodb) GitHub repository. Below is a sample command for installing the MongoDB:

    ```
    
    helm install   \
       --set database.password=mongo \
       --set database.user=mongo \
       --set database.name=velocity \
       --name velocity-mongo ibm-stable/ibm-mongodb-dev
    ```

    If you use the default IBM MongoDB, grant the user admin permissions. Log on to the MongoDB and use a command similar to this one to grant admin permissions to the user:

    ```
    
    db.grantRolesToUser( "mongo", ["readWriteAnyDatabase", "dbAdminAnyDatabase", "clusterAdmin"]  )
    ```

4.   Create an SSL certificate and key and store them in the velocity-secret.yml file. 
    1.   Create the velocity-secret.yml file. Paste the following code fragment into you file:

        ```
        apiVersion: v1
        data:
          tls.crt: <BASE64 Encoded>
          tls.key: <Base64 Encoded>
        kind: Secret
        metadata:
          name: velocitytls
          namespace: default
        type: Opaque
        ```

    2.   Generate a public key and a private certificate. You can use [OpenSSL to generate the certificate and key](https://www.ibm.com/support/knowledgecenter/en/SSWHYP_4.0.0/com.ibm.apimgmt.cmc.doc/task_apionprem_gernerate_self_signed_openSSL.html). The following example creates a certificate named certificate.pem:

        ```
        openssl req -newkey rsa:2048 -nodes -keyout key.pem -x509 -days 365 -out certifcate.pem
        ```

    3.   Encrypt the certificate. The following code fragment illustrates how to encrypt the certificate on Linux:

        ```
        cat certificate.pem | base64
        ```

    4.   Copy the encrypted certificate and then paste it into the tls.crt field in the velocity-secret.yml file. 
    5.   Encrypt the private key and paste it into the `tls.key` field in the velocity-secret.yml file. 
    6.   Apply velocity-secret.yml file to your Minikube installation. You can use the kubectl command to apply your secret:

        ```
        kubectl apply -f velocity-secret.yml
        ```

        If the process is successful, you will see a message similar to the following one:

        ```
        secret/velocitytls created
        ```

5.   Enable your ingress and ensure that it points to your host by completing these steps: 
    1.   Use the following command to enable the ingress: `minikube addons enable ingress`. 

        **Note:** This step is required by Minikube but not a full Kubernetes installation.

    2.   In the /velocity/templates/ingress.yaml file, change the `host:` property to point to your host, and then save the file. 
    3.   Use the following kubectl command to apply the new ingress to Minikube: `kubectl apply -f ingress.yaml`. 
6.   Determine the configuration properties for the helm install command. The following code fragment displays a typical command:

    ```
    
    helm install \
    --set access.key=my\_access\_key \
    --set url.domain=my\_hostname \
    --set mongo.url=mongodb://mongo:mongo@velocity-mongo-ibm-mongodb-dev:27017/admin \
    --name standard ./velocity-1-1-0-helm.tgz
    ```

    Properties depend on your environment. The following properties are required. The optional properties are given later.

    -   **access.key**

        The product access key obtained earlier.

    -   **url.domain**

        The hostname of your node or the Ingress host name.

    -   **mongo.url**

        The URL of the MongoDB. Specify the following parameters.

        -   **username**

            The user ID to authenticate with the MongoDB database.

        -   **password**

            The associated password to authenticate with the MongoDB database.

        -   **port**

            The port number for the MongoDB database. Use the value shown in the example, which is 27017.

        -   **service\_name**

            The MongoDB URL or the MongoDB service name if it is running within the Kubernetes cluster.

        -   **database\_name**

            The name of the database to be used by UrbanCode™ Velocity.

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

7.   Run the `helm install` command to install the UrbanCode Velocity images into your Minikube Kubernetes cluster. After you run the command, Minikube displays status information about the installation.

    Refer to the displayed NOTES section for the location of the Minikube administrator dashboard. You manage your Minikube installation on the admin dashboard.


When all the containers have the status of `running`, the installation is complete and you can access UrbanCode Velocity at the URL you specified in the helm chart. You can refresh the status display by using the following kubectl command: `kubectl get pods`. The default admin user name is admin and the default password is admin.

The following Helm chart parameters are optional:

-   **apitoken**

    A random string or GUID that is used verify the authenticity of API calls and data.

-   **ciphertoken**

    A 32-byte Hex that is used verify the authenticity of API calls and data.

-   **hamackey**

    A 32-byte Hex that is used verify the authenticity of API calls and data.

-   **loglevel**

    The level of logging. Values for this property are: all, debug, info, warn, error, fatal, and off. The default is **all**.


**Parent topic:** [Installation roadmap](../topics/c_install_se_roadmap.md)

