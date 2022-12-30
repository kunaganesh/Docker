
# DOCKER-NETWORKING
* Docker networking is basically used to establish communication between the docker containers and the outside world via host machine or you can say it is a communication passage through which all the isolated containers communicate with each other in various situations to perform the required actions. I
* When Docker is installed, a default VPN is created called bridge. bridge. This is default Network driver of Docker

*  When Docker is installed, a default VPN is created called bridge. bridge. This is default Network driver of Docker


* All Containers on same bridge can communicate each other with-out -p (port)
* Attach Multiple Containers to One Network, and Attach single container to more than One Network or no need to attach any network to container

## Default networks provided by Docker
1. Bridge
2. None
3. Host

## Bridge Network -
Docker provides the bridge network by default. A docker container created on the host is connected to this network by default. The bridge network maps to the docker0 bridge of the host.
## None Network -
The none is used to attach a Docker container to a no-network network! This means that the Docker container will have its own network stack but it will not be configured. Containers attached to the none network will not have an IP address and will be stand-alone.
## Host Network -
When a container is connected to the host network, it gets the same network configuration as in the host OS.

## Docker-Networking-Commands
* List of Available networks :







```bash
docker network ls
```
* To create new network :
```bash
docker network create --driver <driver-name> <network-name> 

Example : docker network create --driver bridge my_network 

If the option –driver is not given then the network will be created as a bridge network. Else, the specified driver will be used.

```
* To know the info of network :
```bash
docker network inspect <network-name>
```
* Filter in inspect command. Ex. want to see the only container info
```bash
docker network inspect -f '{{.Containers}}' <network-name>
```
* To attach a network to a Container :
```bash
docker network connect <network-name> <con-name>
```
* to detach a network to a Container :
```bash
docker network disconnect <network-name> <con-name>
```
* To remove a network :
```bash
docker network rm <network-name>
```
* To create a new container on a specific container :
```bash
docker run -d --name <con-name> --network <network-name/Id> <img-name> 
```
## Docker Network DNS
* DNS stands for Domain Name System.
* DNS makes it possible for us to use easy to remember domain names in place of complex IP addresses.
* Containers uses DNS to communicate. Containers don’t use IP address to Communicate.
* Example . Ping Nginx container from another container

```bash
Step 1: launch 2 nginx container 
 
docker run -d --name nginx_01 --network my_netwrork nginx 
docker run -d --name nginx_02 --network my_netwrork nginx 
 
Step 2: Login to Nginx server and install ping command 
 
docker exec -it nginx_01 /bin/bash  // After executing this command you are login into nginx and execute below command 
 
apt-get update
apt-get install inetutils-ping

Step 3: ping nginx_02 from nginx_01 

docker exec -it nginx_01 ping nginx_02

```



