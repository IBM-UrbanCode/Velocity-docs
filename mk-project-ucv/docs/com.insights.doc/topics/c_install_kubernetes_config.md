# Kubernetes configuration properties

There are a number of configuration properties that can be specified during the install process.

Configuration properties can be specified on the helm install command.

|Property|Default|Description|
|--------|-------|-----------|
|adminpassword|admin|Required. The password for the built-in **admin** user ID used to perform administrator tasks.|
|access.key| |Required. The access key that was obtain when registering for the product. To obtain a free key go the [Request access key](https://www.uc-velocity.com/) page|
|encrypt.key| |Required. A unique ID that is used to encrypt user names, tokens and any email addresses in the mongoDB. You must decide on and specify a key when you install the product for the first time. If you install again, do not change the key. Changing the key can cause you to lose access to existing data.|
|mongo.url| |Required. The URL and login credentials for the MongoDB container, specified in the following format:```
mongodb://username:password@service\_name/URL:port/database\_name
```

|
|url.domain| |Required. The hostname of your Kubernetes master node or the Ingress host name. If there is a reverse proxy in front of the Kubernetes cluster, it becomes the domain name.|
|consumer.image.repository|velocity-conusmer|The name of the consumer node image.|
|consumer.image.tag|latest|The tag of the consumer node image.|
|consumer.image.pullPolicy|Always|Pull the consumer node image before starting the container.|
|consumer.service.type|NodePort|The Kubernetes service type for the consumer node.|
|consumer.service.nodePort|32004|Maps the Kubernetes internal service port \(internalPort\) to the Kubernetes service node port \( NodePort\).|
|consumer.service.externalPort|6004|Maps the Kubernetes internal service port \(internalPort\) to the Kubernetes external service port \( externalPort\).|
|ingress.enabled|false|Specify whether Ingress is enabled or not.|
|loglevel|error|The level of logging. Values for this property are: all, debug, info, warn, error, fatal, and off.|
|prefixname|velocity|The prefix to be added to all pods, services and Ingress names. The value is limited to 20 characters.|
|ui.image.repository|velocity-ui|The name of the user interface image.|
|ui.image.tag|latest|The user interface image tag.|
|ui.image.pullPolicy|Always|Pull the user interface node image before starting the container.|
|ui.service.type|NodePort|The type of service of the user interface node.|
|ui.service.nodePort|32080|Maps the user interface node internal port to the NodePort.|
|ui.service.nodeSSLPort|32443|Maps the user interface node internal SSL port to the NodePort.|
|ui.service.externalPort|6005|Maps the user interface node internalPort to the externalPort.|
|ui.service.externalSSLPort|6443|Maps the user interface node internal SSL port to the external SSL port.|
|url.protocol|https|The type of protocol.|

**Parent topic:** [Installing into a Kubernetes cluster](../../com.insights.doc/topics/t_install_kubernetes.md)

