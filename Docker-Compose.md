
# DOCKER-COMPOSE
* Docker compose is a simple yet powerful tool that is used to defining and run multiple containers as a single service. For example, suppose you have an application which requires Nginx as a web server and MySql as a database service. In this case by docker-compose, you can create one single file (docker-compose.yml ) which will create both the containers as a single service without starting each separately
### Docker-Comopse Installation On Ubuntu
* If you are using windows or Mac machine then docker compose is already install
1. First update the repo :

```bash
 sudo apt update
```
2. Run Below command on your terminal :
```bash
 sudo curl -L "https://github.com/docker/compose/releases/download/1.25.5/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```
3.  Apply executable permissions to the binary :
```bash
 sudo chmod +x /usr/local/bin/docker-compose
```
4. Check the Version of docker Compose :
```bash
docker-compose -v 
or 
docker-compose --version 
or 
docker-compose version 
```
### Docker-compose-Commmands
* To create and start containers :
```bash
 docker-compose up
```
* To craete and start containers with detached mode :
```bash
 docker-compose up -d
```
* To start a specific container based on service name :
```bash
 docker-compose up <service-name>
``` 
* To list the available images :
```bash
 docker-compose images
```
* To list the running containers :
```bash
 docker-compose ps
```
* To list all the containers running/non-running :
```bash
 docker-compose ps -a
```
* To stop all the containers :
```bash
 docker-compose stop 
```
* To remove all the containers :
```bash
 docker-comopse down 
```
* To stop specific container based on service name :
```bash
 docker-compose stop <servicename>
```
* To remove specific container based on service name :
```bash
 docker-compose down <servicename>
```
* To scale the container how many we want :
```bash
 docker-compose up -d --scale <service-name>=3
 ```
 ## Sample Docker-Compose File
 * First we need to create a file called docker-compose.yml
```bash
 touch docker-compose.yml
```
* To check the docker-compose file correct or not :
```bash
 docker-compose config
```
* In this case we can run tmcat, nginx, and mysql from this file :
```bash
 version: '3'

services:
    webserver:
        image: nginx:alpine
        container_name: nginx-con
        ports:
        - '8090:80'
        volumes:
            - my-db:/usr/share/nginx/html

    Database:
        image: mysql:5.7
        container_name: mysql-con
        restart: always
        environment:
            MYSQL_DATABASE: 'mydb'
            MYSQL_ROOT_PASSWORD: '123456'
        ports:
        - '3306:3306'
        expose:
        - '3306'
        volumes:
            - my-db:/var/lib/mysql

    tomcat-server:
        image: tomcat
        container_name: tomcat-con
        ports:
        - '8080:8080'
        volumes:
            - my-db:/opt/tomcat/webapps

volumes:
    my-db:

```