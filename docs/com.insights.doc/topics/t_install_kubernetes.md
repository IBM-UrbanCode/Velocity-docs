# Installing into a Kubernetes cluster

You must have the access key to complete the install process. To obtain a key go the [Request access key](https://www.uc-velocity.com/) page and complete information to obtain an access key. The access key is sent to your email.

It is important that you have reviewed the [System requirements](c_install_requirements.md) before starting to ensure all requirements are met.

Install UrbanCode™ Velocity into a Kubernetes cluster using Helm commands. The commands pull the UrbanCode Velocity node images from a GitHub repository and places them into the Kubernetes clusters defined in Helm Charts. Helm v2.6.0 is required.

1.   Verify that both the Helm client and server are at the same version level. Issue the following command to verify. 

    ```
    helm version
    ```

2.   If you do not have a MongoDB database installed, you can install one now. Go to [MongoDB](https://github.com/kubernetes/charts/tree/master/stable/mongodb) GitHub repository to install. 
3.   Issue the following command to obtain the Helm charts used for the installation. 

    ```
    
    helm init
    helm repo add urbancode https://raw.githubusercontent.com/IBM/velocity/master/kubernetes/repo
    helm fetch urbancode/velocity
    ```

4.   Determine the configuration properties to specify. You can customize the installation by specifying configuration properties on the helm install command. Some of the properties that you specify are dependent on your environment, for example if you are using Ingres there are a few related properties. There are several required properties that must be specified. Below are the required properties.

    -   **adminpassword**

        The password for the built-in **admin** user ID used to perform administrator tasks. The default value for this property is admin.

    -   **access.key**

        The access key that was obtain when registering for the product.

    -   **encrypt.key**

        A unique ID that is used to encrypt user names, tokens and any email addresses in the mongoDB. You must decide on and specify a key when you install the product for the first time. If you install again, do not change the key. Changing the key can cause you to lose access to existing data.

    -   **url.domain**

        The hostname of your Kubernetes master node or the Ingress host name. If there is a reverse proxy in front of the Kubernetes cluster, it becomes the domain name.

    -   **mongo.url**

        The URL of the MongDB. Specify the following parameters.

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

    See [Kubernetes configuration properties](c_install_kubernetes_config.md) for the complete list to determine which other properties to specify for your environment.

5.   Run the `helm install` command to install the UrbanCode Velocity images into your Kubernetes cluster. The following example shows the required configuration properties, depending on your environment other might be required. 

    ```
    helm install \
      --set access.key=access\_key \
      --set url.domain=hostname \
      --set mongo.url=mongodb://username:password@service\_name:27017/database\_name \
      --set encrypt.key=encryption\_key \
      --set adminpassword=admin \
      --name my-release urbancode/velocity
    ```


Access the administrator user interface to complete the configuration. Refer to the NOTES section displayed after the `helm install` command completes for the location of the administrator user interface.

