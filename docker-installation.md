<h3>This installation is from Arue Repository</h3>

- Update package index for repository use over HTTPS
    
    ```bash
    sudo apt-get update
    ```
    
    ```bash
    sudo apt-get install \
        ca-certificates \
        curl \
        gnupg \
        lsb-release
    ```
    
- Add Docker's official GPG key
    
    ```bash
    sudo mkdir -p /etc/apt/keyrings
    ```
    
    ```bash
    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
    ```
    
- Add repos
    
    ```bash
    echo \
      "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
      $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
    ```
    

<h4>Install Docker Engine**</h4>

- Update repository
    
    ```bash
    sudo apt-get update
    ```
    
- Install docker engine
    
    ```bash
    sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin -y
    ```
    
- Check docker version for make sure docker already installed on your OS
    
    ```bash
    docker -v
    ```