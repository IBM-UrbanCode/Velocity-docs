# Installing as an OpenShift application

The ID that you use to install the product must be able to make changes to the host environment. The tools required by all installation scenarios include the following items:

-   Docker installed on the host system.
-   Internet connection. During installation, files and container images are retrieved from remote locations. If you are unable to access the internet during installation, you can download the files beforehand and perform an offline installation.

    **Note:** The installation files used for offline installation are not the same as those used for internet-connected installation. Ensure that you download the right file for you installation environment.

-   IBM UrbanCode™ Deploy Version 6.2.3 and later. Although not strictly required, many UrbanCode™ Velocity features assume integration with UrbanCode Deploy. It doesn't matter which product you install first.

    If you are using an UrbanCode Deploy version prior to V6.2.5, you must install the patch located at the following website: [http://public.dhe.ibm.com/software/products/UrbanCode/plugins/ucsync/patches/ibmucd/](http://public.dhe.ibm.com/software/products/UrbanCode/plugins/ucsync/patches/ibmucd/). Select from the index the appropriate version that is installed on your computer.

    UrbanCode Velocity can connect to an UrbanCode Deploy server on the same network. If you install UrbanCode Velocity with Kubernetes, the Kubernetes cluster must be on the same network as the UrbanCode Deploy server.


In addition to the requirements for all installation scenarios, you need the following items:

-   Configured OpenShift client instance. This topic uses Minishift for local instance installations.
-   OpenShift command line tool, OC, installed on the client.
-   Access to the PEM-format certificate and private key that you can use to configure an OpenShift route.
-   Master node: 2 vCPU, 8 GB RAM, 30 GB storage.
-   Other nodes: 1vCPU, 8 GB RAM, 15 GB storage.

Several service containers require the root user. From the OpenShift client command line, run the following commands:

```
oc login -u system:admin -n default 
oc adm policy add-scc-to-group anyuid system:authenticated
```

**Get an access key**. The access key enables you to complete installation. [Visit the UrbanCode Velocity web portal to obtain your key](https://uc-velocity.com/). After completing the form, you can copy the access key. Store the key in a readily-available location; you use it during installation.

**Note:** Make sure that you select a key for the product version that you want to install. Keys for the Standard Edition do not work with the Community Edition and vice-versa.

You will install UrbanCode Velocity into a OpenShift project. During installation, you configure a MongoDB for your project, add the UrbanCode Velocity service to your OpenShift project catalog, and create a route that makes the UrbanCode Velocity application publicly accessible.

1.   Download the installation file for your environment. [Visit the FlexNet download center and select the file for your environment.](https://www.hcltech.com/products-and-platforms/contact-support-sales) 
2.   Run the downloaded executable file. 
3.   At the **Enter the location where the Velocity files will be installed** prompt, specify where to put the installation files. 
4.   From the OpenShift dashboard, create a project for UrbanCode Velocity. When the project is created, in the **My Projects**area, select the project, and then click **Browse Catalog**.
5.   Install the UrbanCode Velocity service template in the project catalog by completing the following steps:. 
    1.   If it isn't already extracted, extract the yaml file from the archive, velocity-se-<version number\>-openshift.tar.gz, that you installed earlier. The name of the yaml is velocity-se-<version number\>-openshift.yaml.
    2.   From OpenShift project catalog, use the **Add to Project** \> **Import YAML/JSON** command to import the velocity-se-<version number\>-openshift.yaml file. The service is added to the catalog.
    3.   Select **Create**, and then uncheck **Process the Template**and check **Save Template**. After refreshing the browser, you see the UrbanCode Velocity service in the OpenShift project catalog.
6.   Create a MongoDB service for the project by completing the following steps: 
    1.   From the OpenShift project catalog, select **MongoDB**. 
    2.   On the MongoDB configuration page, click **Next**, and then, in the **MongoDB Admin Password** field, enter a password for admin user. You can accept the default values for the other parameters.

        **Note:** The user must be the admin user, not user the MongoDB user.

    3.   Click **Create**. 
    4.   On the MogoDB has been created page, copy the `Connection URL` string and store it in a readily-accessible location, then close configuration window. You use the connection string to configure your UrbanCode Velocity project.
7.   Create an UrbanCode Velocity service by completing these steps. 
    1.   From project catalog, select **Velocity** ![OpenShift Catalog](../images/OpenShiftCatalog.PNG). The Velocity configuration window is displayed.
    2.   Click **Next**, and then, in the **Name** field, enter a service name. 
    3.   In the **Hostname** field, enter the service host name. 

        The host name must resolve to a name on your DNS server, or in the server's hosts file. On Linux, the file location is etc/hosts; on Windows, the location is C:\\Windows\\System32\\drivers\\etc\\hosts.

    4.   In the **Access Key** field, paste the UrbanCode Velocity access key received earlier. 
    1.   In the **Mongo URL** field, paste MongoDB connection string for the MongoDB service. Do not use the default user or database name. Use the admin user and password you created for the admin. For example:

        ```
        mongo://admin:password@mongodb
        ```

        **Note:** When you copy the sample connection code, make sure that you delete the `sampleDB` part from the copied code.

        If you do not want to use the admin user, log on to the MongoDB and use a command similar to this one to grant admin permissions to the user:

        ```
        
        db.grantRolesToUser( "mongo", ["readWriteAnyDatabase", "dbAdminAnyDatabase", "clusterAdmin"]  )
        ```

    1.   Accept the default values for the other parameters and click **Create**. 
8.   Create a route by completing the following steps: 

    1.   From project dashboard, click **Applications** \> **Routes** \> **Create Route**. 
    2.   In the **Name** field, provide a name for the route. 
    3.   In the **Hostname** field, enter the host name you specified earlier for UrbanCode Velocity. 
    4.   In the **Service** field, select the `velocity-router` service. 
    5.   Check **Secure route**. 
    6.   From the **TLS Termination** list, select `Edge`. 
    7.   Upload your PEM-format certificate or, on the **Insecure Traffic** list, select `Allow`. 
    8.   Click **Create**. 
    The new route is listed on the Routes page.


After the installation is complete, access UrbanCode Velocity by clicking the route name link. The default user name is admin and the default password is admin.

**Parent topic:** [Installation roadmap](../topics/c_install_se_roadmap.md)

