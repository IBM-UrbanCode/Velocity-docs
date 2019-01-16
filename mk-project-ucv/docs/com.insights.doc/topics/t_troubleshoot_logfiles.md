# Viewing log files

To view the logs in either a Docker or Kubernetes environment, use commands associated with the environment. In either environment you need to know the names of the UrbanCode Velocity containers.

-   velocity-consumer
-   velocity-ui

**Parent topic:** [Troubleshooting](../../com.uvelocity.doc/topics/c_node_troubleshoot.md)

## Viewing logs in a Kubernetes environment

To view the logs in a Kubernets environment, you need to know the pod name that the UrbanCode Velocity containers are located. A pod is a collection of one or more containers that are deployed together, and are started, stopped, and replicated as a group.

The default log level is **error**. The level of logging can be changed on the **log.level** configuration property. Other logging levels are: all, debug, info, warn, error, and fatal. Logging can also be turned off on the configuration property.

1.   From a command line window, run the following command to obtain the pod names containing the UrbanCode Velocity containers. 

    ```
    kubectl get pods
    ```

2.   Run the following command to view the logs. 

    ```
    kubectl logs pod\_name
    ```


## Viewing logs in a Docker Compose environment

To view the logs in a Docker container, you need to know the container ID for the UrbanCode Velocity containers.

1.   From a command line window, run the following command to list containers. 

    ```
    docker ps -a
    ```

    The command output displays the containers and its ID.

2.   To view the logs, use the docker logs command. Run a separate command for each container.

    ```
    docker logs velocity\_userinterface\_container\_id
    docker logs velocity\_consumercontainer\_id
    ```


