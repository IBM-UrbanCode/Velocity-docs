# Installing as a Docker Compose application

You must have an access key to complete the install process. To obtain a key go the the [Request access key](https://www.uc-velocity.com/) page and complete information. The access key is sent to your email.

It is important that you have reviewed the [System requirements](c_install_requirements.md) before starting to ensure all requirements are met.

UrbanCode™ Velocity is installed as a Docker Compose application using the command line. You will use commands to pull the UrbanCode Velocity images from Dock Hub and a configuration files from a GitHub repository over an internet connection. Commands are also used to places the container image in the containers defined in the docker-compose.yml file.

The installation instructions are specific to the Linux™ operating system.

1.   Ensure that the computer system software is current. Open a command line and issue the following commands. The commands fetches a list of available updates and any updates needed for the machine to be current are installed.

    ```
    sudo apt-get update 
    sudo apt-get upgrade 
    sudo apt-get dist-upgrade
    ```

2.   If you do not have Docker installed, install it now. Go to the [Install Docker](https://docs.docker.com/engine/installation/) website to download and install Docker. If Docker is already installed, proceed to the next step. 
3.   Verify that your Docker installation is at the required level, by issuing the following command. 

    ```
    docker-compose --version
    ```

    The response should indicated Docker version 17.09.0-ce, build afdb6d4 or later is installed.

4.   If you do not have Docker Compose installed, install it now. Go to [Install Docker Compose](https://docs.docker.com/compose/install/#install-compose) website to download and install Docker Compose . If Docker Compose is already installed, proceed to the next step. 
5.   Verify that your Docker installation is at the required level, by issuing the following command. Issue the following command.

    ```
    docker-compose
    ```

    The response should indicated that version 1.8.0 or later is installed.

6.   Prepare the docker volume 

    A docker volume is required for the MongoDB. Create a docker volume with name **velocity-mongo**.

    ```
    docker volume create velocity-mongo
    ```

7.   Download the docker-compose.yml. 

    ```
    wget https://raw.githubusercontent.com/IBM/velocity/master/docker-compose/docker-compose.yml
    ```

8.   Issue the following commands to set the required environment variables. 

    ```
    export ACCESS_KEY=access\_key
    export URL_DOMAIN=hostname
    export ENCRYPT_KEY=encryption\_key
    ```

    -   **access\_key**

        The access key that was obtain when registering for the product.

    -   **hostname**

        The hostname of computer the product is installed. Specify only the host name and not the URL.

    -   **encryption\_key**

        Specify a unique ID that is used to encrypt user names, tokens and any email addresses in the mongoDB. You must decide on a key when you install the product for the first time. If you install again, do not change the key. Changing the key can cause you to lose access to existing data.

    Optionally, you can edit the docker-compose.yml file to change the administrator password and other configuration properties.

9.   Run the following command to install the UrbanCode Velocity container images into containers. 

    ```
    docker-compose up -d
    ```


After the installation is complete, access the administrator user interface to complete the configuration. The default URL is https://hostname/admin, where hostname is the host name of the computer where the server is running. The user name is admin and the default password is admin. A different password can be specified in the docker-compose.yml file.

