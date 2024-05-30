<h3>Initialize Manager and Worker Swarm</h3>

- Initialize first manager (on node manager)
    
    ```bash
    docker swarm init --advertise-addr 192.168.2.1
    ```
    

## Add Worker

- Get worker token for manager
    
    ```bash
    docker swarm join-token worker
    *#it will displayed token for worker*
    ```
    
- Add worker node (exec on worker node, not on manager node!)
    
    ```bash
    docker swarm join --token SWMTKN-1-xxxxx 192.168.2.1:2377
    ```
    

## Add New Manager

- Get manager token for add manager
    
    ```bash
    docker swarm join-token manager
    ```
    
- Add new manager node (exec on new manager node, not on old manager node!)
    
    ```bash
    docker swarm join --token SWMTKN-1-2qlcpg9xqzu467tth4xvx2l7d2xudn6luf8o9h29gbrgyk1exf-bi0xkm6m9orn9wew9ay0uizic 192.168.2.1:2377
    ```

