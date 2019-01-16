# Types of problems and checks to perform

This topic contains tips for troubleshooting

## Images are not displaying

If there was an error pulling the images, there might be a network issue. Verify that the cluster can pull images from docker-hub and install the product again.

## MongoDB connection error

If there is a MongoDB connection error, verify that the MongoDB is active and accessible from the Kubernetes cluster. This chart does not install MongoDB.

## Domain cannot be accessed

Verify that the value for the **url.domain** is correct in the value file. The value is usually the Ingress host name or the hostname of your Kubernetes master node. If you have any reverse proxy in front of your Kubernetes cluster, that becomes your domain. Do not use the IP address.

**Parent topic:** [Troubleshooting](../../com.uvelocity.doc/topics/c_node_troubleshoot.md)

