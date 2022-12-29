## DOCKER INSTALLATION ON UBUNTU


1. First we need to update the repos.
              





```bash
  sudo apt-get update
```

2. First run the below commands..

```bash
   sudo apt update
   sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release -y
```
3. Add Docker’s official GPG key:

```bash
  sudo mkdir -p /etc/apt/keyrings
  curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
```
4. Use the following command to set up the repository:


```bash
 echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```
5. Install the Docker Engine.


```bash
  sudo apt-get install docker.io -y
  ```

  ## Docker Installation on Centos

  1. Unistall old versions:

```bash
    sudo yum remove docker \
                  docker-client \
                  docker-client-latest \
                  docker-common \
                  docker-latest \
                  docker-latest-logrotate \
                  docker-logrotate \
                  docker-engine
```
2. Setup the repository:
```bash
  sudo yum install -y yum-utils
  sudo yum-config-manager \
    --add-repo \
    https://download.docker.com/linux/centos/docker-ce.repo      
```
 3. Install the Docker Engine:

```bash
sudo yum install docker.io -y
```

