# Installing UrbanCode Velocity with Docker Compose

Install UrbanCode™ Velocity into the Docker Compose container orchestrator.

The ID that you use must be able to make changes to the host environment. The tools required by all installation scenarios include the following items:

-   Docker. The commands used during installation retrieve files and container images from remote locations. If you are unable to access the internet during installation, the install images will need to have been previously downloaded and placed in a Docker repository that the installation commands can access.
-   IBM UrbanCode™ Deploy Version 6.2.3 and later. Although not strictly required, many UrbanCode Velocity features assume integration with UrbanCode Deploy. It doesn't matter which product you install first.

    If you are using an UrbanCode Deploy version prior to V6.2.5, you must install the patch located at the following website: [http://public.dhe.ibm.com/software/products/UrbanCode/plugins/ucsync/patches/ibmucd/](http://public.dhe.ibm.com/software/products/UrbanCode/plugins/ucsync/patches/ibmucd/). Select from the index the appropriate version that is installed on your computer.

    UrbanCode Velocity can connect to an UrbanCode Deploy server on the same network. If you install UrbanCode Velocity with Kubernetes, the Kubernetes cluster must be on the same network as the UrbanCode Deploy server.

-   Git and a GitHub account.

In addition to the requirements for all installation scenarios, the following items are required for Docker Compose systems:

-   Docker Compose version 17.09.0-ce, build afdb6d4 and later
-   CPU with 4+ cores.
-   8GB RAM
-   8GB storage
-   If you are installing the product on Red Hat Enterprise Linux®, you need RHEL 7 or later.

**Get an access key**. The access key enables you to complete installation. [Visit the UrbanCode Velocity web portal to obtain your key](https://uc-velocity.com/). After completing the form, you can copy the access key. Store the key in a readily-available location; you use it during installation.

**Note:** Make sure that you select a key for the product version that you want to install. Keys for the Standard Edition do not work with the Community Edition and vice-versa.

The installation instructions describe installing the product on all supported operating systems. The downloaded executable file steps you through the installation process and sets your installation parameters.

1.    [Download the installation file for you environment](https://public.dhe.ibm.com/software/products/UrbanCode/Velocity/latest/). The download page has installation files for all supported platforms. Select the file appropriate for you environment:

    -   Linux: velocity-install-docker-compose-linux
    -   Windows: velocity-install-docker-compose-win.exe
    -   Mac OS: velocity-install-docker-compose-macos
    You can use a shell command to download the file. For example, if you are installing the product on Linux, you can download the file with a command like this one:

    ```
    wget https://public.dhe.ibm.com/software/products/UrbanCode/Veloc
    ity/latest/velocity-install-docker-compose-linux
    ```

2.   Run the downloaded executable file, and then select your installation scenario. For example, on Linux use the following shell command:

    ```
    ./velocity-install-docker-compose-linux
    ```

3.   At the **Enter the location where the Velocity files will be installed** prompt, specify where to put the installation files. 
4.   Complete installation by responding to the prompts described in the following steps. When the script starts, you are prompted to accept the license. You can explicitly accept the license without viewing it by appending the following parameter to the command:

    ```
    ./velocity-install-docker-compose-linux **--license=accept**
    ```

    1.   At the **Please enter your Velocity access key** prompt, enter your SE version access key. If you previously installed an SE version, the already-configured key is the default value.

        **Note:** Make sure that you enter the key for the right version.

    2.   At the **Please enter the hostname where you will run Velocity** prompt, enter the host name where users can access the Web UI. The default value is `localhost`.

        The host name must resolve to a name on your DNS server, or in the server's hosts file. On Linux, the file location is etc/hosts; on Windows, the location is C:\\Windows\\System32\\drivers\\etc\\hosts.

    3.   At the **Enter the desired port where Velocity will run** prompt, enter the port number for the Web UI. The default value is `443`.
    4.   At the **Enter the location where the Velocity files will be installed** prompt, enter the location where you want to install the product files. 
5.   Complete installation by changing to the directory where you installed the product, and start Docker Compose. For example: 

    ```
    ~/projects/velocity-se/ docker-compose up -d
    ```

    The UrbanCode Velocity images are pulled from Docker Hub and configured for Docker Compose.


Access the UrbanCode Velocity Web UI. The URL is https://hostname:port, where `hostname` and `port` are the values that you set during installation. The initial user name is admin and the default password is admin.

Installation properties are stored in the \[installation\_folder\]/docker-compose/.env file. You can edit the properties appropriate for your environment. The env file contains a description for all installation properties, including the following properties:

-   **Access\_Key**

    The product access key obtained earlier.

-   **NGINX\_HOST**

    The domain of the URL the users will use to access Velocity. The value is usually the hostname of the virtual machine where Docker Compose is running.


To complete installation, replace the supplied SSL public certificate and private key with your own copies. You can use OpenSSL to generate your own key with a command similar to the following example:

```
openssl req -newkey rsa:2048 -nodes -keyout key.pem -x509 -days 365 -out certifcate.pem
```

Place your self-generated key and certificate in the \[velocity-install-folder/docker-compose/conf/ssl folder.

After you purchase the product, you receive a permanent access key, and a license key.

**Parent topic:** [Installation roadmap](../topics/c_install_se_roadmap.md)

