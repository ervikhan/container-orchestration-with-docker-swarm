<h3>Docker Service</h3>

*docker service is useful for creating and running **only 1 type** of container, the concept is almost the same as when we create a container in docker*

```bash
***docker service*** ..
**create**      Create a new service
**inspect**     Display detailed information on one or more services
**logs**        Fetch the logs of a service or task
**ls**          List services
**ps**          List the tasks of one or more services
**rm**          Remove one or more services
**rollback**    Revert changes to a service's configuration
**scale**       Scale one or multiple replicated services
**update**      Update a service
```

- Create service
    
    ```bash
    docker service create -t --name apache-php81 -p 8080:80 registry.dinus.ac.id/dnt-ubuntu-apache-php81:1.0
    ```
    
    *if registry need auth, put parameter `--with-registry-auth`*
    
    ```bash
    docker service create -t *--with-registry-auth* --name apache-php81 -p 8080:80 registry.dinus.ac.id/dnt-ubuntu-apache-php81:1.0
    ```
    
- Replicas and Scalling
    
    ```bash
    docker service scale apache-php81=3
    ```
    
    ```bash
    *explaning:*
    - apache-php81 = container name
    - 3 = total of worker
    ```
    
    *or you can add using parameter `--replicas 3` when create service*