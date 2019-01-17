# UrbanCode Velocity Considerations for GDPR Readiness


## Notice:

This document is intended to help you in your preparations for GDPR readiness. It provides information about features of UrbanCode Velocity that you can configure, and aspects of the product's use, that you should consider to help your organization with GDPR readiness. This information is not an exhaustive list, due to the many ways that clients can choose and configure features, and the large variety of ways that the product can be used in itself and with third-party applications and systems.

**Clients are responsible for ensuring their own compliance with various laws and regulations, including the European Union General Data Protection Regulation. Clients are solely responsible for obtaining advice of competent legal counsel as to the identification and interpretation of any relevant laws and regulations that may affect the clients' business and any actions the clients may need to take to comply with such laws and regulations.**

**The products, services, and other capabilities described herein are not suitable for all client situations and may have restricted availability. HCL does not provide legal, accounting, or auditing advice or represent or warrant that its services or products will ensure that clients are in compliance with any law or regulation.**

### Table of Contents

1.  GDPR
2.  Product Configuration for GDPR
3.  Data Life Cycle
4.  Data Collection
5.  Data Storage
6.  Data Access
7.  Data Processing
8.  Data Deletion
9.  Data Monitoring
10.  Responding to Data Subject Rights

### GDPR

General Data Protection Regulation (GDPR) has been adopted by the European Union ("EU") and applies from May 25, 2018.

#### Why is GDPR important?

GDPR establishes a stronger data protection regulatory framework for processing of personal data of individuals. GDPR brings:

*   New and enhanced rights for individuals
*   Widened definition of personal data
*   New obligations for processors
*   Potential for significant financial penalties for non-compliance
*   Compulsory data breach notification

#### Read more about GDPR

*   [EU GDPR Information Portal](https://www.eugdpr.org/)
*   [ibm.com/GDPR website](https://ibm.com/GDPR)


### Product Configuration - Considerations for GDPR Readiness

The following sections provide considerations for configuring UrbanCode Velocity to help your organization with GDPR readiness.

### Data Life Cycle

#### What is the end-to-end process through which personal data go through when using our offering?

IBM UrbanCode Velocity (UCV) uses a client-server model. The server provides the web-based front-end and core services, such as workflow and security. Services can be consumed by clients and other services. Deployments are orchestrated by the server and, when integrated with UrbanCode Deploy, performed by agents distributed throughout the network. Clients access the server through web browsers, the REST API, or the command-line client.

The core installation of UCV includes a server, database, and a license server.

There are several third-party products that interact with UCV via plug-ins, and might exchange data. Some of these are HCL-owned, and many others are provided by other technology suppliers. The system requirements provide information the requirements for the associated software. For considerations for GDPR readiness of a third-party product, see that product’s documentation.

#### What types of data flow through UCV?

As a software deployment an integration engine, UCV does not require sensitive personal data to be gathered from the client or the client's clients.


##### Personal data used for online contact with IBM

UrbanCode Velocity clients can submit online comments/feedback/requests to contact IBM about product topics in a variety of ways, primarily the comment areas of the following, as applicable:



Typically, only the client name and email address are used, to enable personal replies for the subject of the contact, and the use of personal data conforms to the [IBM Online Privacy Statement] (https://www.ibm.com/privacy/us/en/).


### Data Collection



### Data Storage

Deployments are orchestrated by the server and performed by agents distributed throughout the network. The file store, CodeStation, contains log files, artifacts, and other non-structured data objects. Reporting tools can connect directly to the relational database.

The file store manages artifacts in a secure and and tamper-proof repository that ensures deployed artifacts are identical to those tested in preproduction environments.



#### Protection

UCV uses several technologies to provide security. Some features can be configured to meet client requirements such as Transport Layer Security (TLS). Some features are disabled by default, such as mutual authentication.



### Data Access

The UCV team- and role-based security system manages user interactions and secures product features. Roles control virtually every product area, including the objects that users can create and who can modify the security system itself. User-created objects are managed by teams. Team members can only access objects, such as applications, managed by their team. Team members interact with team-managed objects according to the permissions granted to their role.


#### Logging administration activity:

Administrative activity is kept in the system logs. instances when the admin user adds a user or changes a users role and permissions are tracked in the log.




### Data Processing

Users control the way in which UCV interacts with data passing through it by their definition of task and application processes. A process is commonly constructed by a user acting in the role of “developer” working with the component plug-in toolkit. A process is composed of discrete building blocks (known as steps) that are joined together by the developer.

#### Who has access to the Data?

Most customers import users from external LDAP realms. Clients filter LDAP account data for the information they need, such as user IDs, email addresses, and passwords. Groups that the imported users belong to are also imported.

Permissions are assigned to roles and users and groups are placed into roles when they are placed onto teams. Users without roles have read-only privileges and cannot access data let alone modify it.

#### Encryption:

Communication between server and clients or external systems and can be secured by using SSL and TLS, with optional mutual key-based authentication for each end-point. This communication protocol is stateless and resilient to network outages.


### Data Monitoring

With an external monitoring tools, clients can use Managed Beans (MBeans) to review numerous details about UCV, such as statistics that specify how many tasks are available or see how long it takes for an deployment to run to completion. Clients can use these statistics and details to assess the health of their deployments and deployment processes.

#### Activity monitoring

Audit and diagnostic logs are under user control. Clients control the amount of user activity maintained and the frequency with which it is stored.



### Responding to Data Subject Rights

On premises product managed by the client, please review links provided in earlier sections for configuration information.

