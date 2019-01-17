# Getting started

The administrator must complete several tasks before users can access and run reports.

Making UrbanCode™ Velocity available to you environment involves three tasks:

-   **Installation**

    Install the UrbanCode™ Velocity installation image into the appropriate containers and ensure that requirements are met in the environment.

-   **Integration**

    Define credentials to communicate with one or more UrbanCode™ Deploy servers. You’ll need the server location and an UrbanCode™ Deploy token to complete the integration. The token must be an administrator user token.

    When more than one server is integrated, the data that is gathered for reports is aggregated from all servers. The data is not displayed by server.

-   **Authentication**

    Provide access to users who are defined in UrbanCode™ Deploy to the UrbanCode™ Velocity user interface. Users can be authenticated using either LDAP, OAuth, or SSO.


After the administrator authenticates and completes the integration with UrbanCode Deploy, the administrator can map environments and applications at the business level by using a pattern to create logical groupings that provide a focus to report data.

1.   Install UrbanCode Velocity. Start the installation by running installation commands for the container manager system that is being used to download the product image into containers on your computer. For details about requirements and install process, see [Installation roadmap](c_install_roadmap.md).
2.   Integrate with a source repository. Access the administrator console to complete integration with the UrbanCode Deploy server. The location and administrator credentials are provided at the end of the installation process. This task must be completed to continue with the user interface. After the integration is complete, synchronization between the repository and the MongoDB starts. Additional integrations can be added at any time by any user with administrator access.
3.   Authenticate users to access reports. Users who are defined to UrbanCode Deploy can be authenticated. You can complete this step now or later. If you complete the step later, only the administrator ID has access to the reports. This situation may be desirable providing the administrator time to verify and explore reports before giving access to other users.

    Authenticated users access the user interface with the URL that the administrator provides.


**Parent topic:** [Setup the environment](../../com.uvelocity.doc/topics/c_node_setup.md)

