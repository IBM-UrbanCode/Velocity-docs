# Installation roadmap

The installation roadmap is a description of the high-level steps for installing UrbanCode™ Velocity.

Each of these tasks must be performed to complete the install process. However, the actual process is different depending on whether you are installing in a Kubernetes cluster or as a Docker Compose application.

1.  **Obtain an access key**

    An access key is required to start the install process. If you have not already requested an access key, visit the [Request access key](https://www.uc-velocity.com/) website page to complete a customer profile. The access key will be sent to your email. The key will expire in seven days. If the key expires, you will need to complete the registration form information and request another key.

    You'll also be required to read the Terms and Conditions agreement from the registration page. The license must be accepted to complete the install process.

2.  **Verify requirements**

    Verify that your computer meets the[minimum hardware and software requirements](c_install_requirements.md) for installing the product.

    Make sure that your user ID meets the requirements for installing and configuring the product. The user ID being used must be able to make changes to the computer.

3.  **Verify internet connection**

    The installation process requires internet connection. The commands used during the install process pull the install images to be placed into containers. If you are unable to access the internet during the installation, the install images will need to have been previously downloaded and placed in a docker repository that the installation commands have accessed.

4.  **Verify the container management system**

    Verify that one of the supported container management systems is available. The installation process is different depending on the management system that you use. If you do not currently have a system, follow the Docker Compose installation instructions because it includes installing a Docker Compose system.

    If using the Kubernetes cluster management system, verify that a MongoDB is included.

5.  **Install UrbanCode Velocity into your environment.**

    The install process depends on whether the container management system is Kubernetes or Docker Compose. If you do not have either available, follow the installation instructions for installing as a Docker Compose application which includes installing Docker Compose.

    -   [Installing into a Kubernetes cluster](t_install_kubernetes.md)
    -   [Installing as a Docker Compose application](t_install_docker.md)
6.  **Integrate with source repository and authenticate users**

    After the installation is complete, you can access the configuration pages to integrate with UrbanCode Deploy and authenticate users. The integration process is required. No report data is available until the integration process is complete. Authenticating users to access reports is not required. However; until users are authenticated only the administrator user has access.


**Parent topic:** [Installation roadmap](../../com.uvelocity.doc/topics/c_install_se_roadmap.md)

