
# DOCKER-VOLUMES
 ### Container Persistent Data Problem
*  Containers are immutable : Once deploy never change, only re-deploy.
*  Config Change or version Upgrade need re-deploy.
* By default all files created inside a container are stored on a writable container layer.
*  The data doesn’t persist when that container no longer exists, and it can be difficult to get the data out of the container if another process needs it
### Docker Volumes 
* Volumes : Volumes are stored in a part of the host filesystem which is managed by Docker
* Volumes can be create by Volume Command in Docker File.
* When you create a volume, it is stored within a directory on the Docker host machine.
* Volumes can not be removed when user destroy the containers
* We can assign same volume to multiple container
## Docker-Volume-Commands
* To list the the available Volumes :
```bash
docker volume ls
```
* Home directory of docker volumes/Destination of volumes :
```bash
/var/lib/docker/volumes
```
* To create volume :
```bash
docker volume create <vol-name>
```
* Mount a volume to a container :
```bash
docker run -d --name <con-name> --mount source=<vol-name>,target=<path of the volume storing in container/Any folder path> <img-name>
//and we can attach same volume to another container to persist our data/files when we removed that container//
```
### One Example For Docker volume using mySQL 
```bash
Step 1  Create the volume
        docker volume create DBVOL
        
Step 2  Pull the image of mysql
        docker pull mysql
        
Step 3  Run the containr with named volume 
        docker run -d --name [nameofcontainer] -e [enviourment] -v [volumename]:[destinationpath] [imagename]             
        ex: docker run -d --name myDb1 -e "MYSQL_ROOT_PASSWORD=1234" --mount source=DB,target=/var/lib/mysql mysql
  
Step 4  Download mysql client 
        apt-get install mysql-client
 
Step 5  Inspect the container and get the IP address and port 
        docker inspect [containername]
        
Step 6  login to mysql  
        mysql -u root[password] -h[ipaddress] -P[port]
        ex. mysql -u root -p1234 -h 172.17.0.3 -P 3306
        
Step 7  Create the database
        create database one;  // this command create the database 
        show databases;       // this command show the list of database 
        exit                  // Exit from mysql 
        
Step 8  Stop and Remove the container 
        docker stop [container] 
        docker rm   [container] 

Step 9  create another container with same volume
        docker run -d --name [nameofcontainer] -e [enviourment] -v [volumename]:[destinationpath] [imagename]             
        ex: docker run -d --name myDb2 -e "MYSQL_ROOT_PASSWORD=1234" --mount source=DB,target=/var/lib/mysql mysql
        
Step 10 login to mysql new container 
        mysql -u root[password] -h[ipaddress] -P[port]
        ex. mysql -u root -p1234 -h 172.17.0.3 -P 3306
        
Step 11 We can see the same db is available with new container means db is persistant      
        
```
### Bind Volumes
*  Bind Mounts : Bind mount means a file or directory on the host machine is mounted into a container..
* Bind mounts may be stored anywhere on the host system.
* when we use bind mount for a container we no need to redeploy or change container for our changes in application.
* We specify the path of our build files and creating container... when we made changes in appliaction then we replace our build to new build files.. then automatically changes are applying without redeploy or restarting the container.
### Example For Bind volume

```bash
Step 1  Create folder that you want to share 
        mkdir share
        cd share 
        
Step 2  Pull the Nginx image from docker hub
        docker pull nginx

Step 3  Create the Run the docker container with Bind volume 
        docker run -d --name [nameofcontainer] -p [portoptional] --mount type=bind,source="$(Build files path)",target=[targetpath] [imagename]
        ex: docker run -d --name ng1 -p 80:80 --mount type=bind,source="$(pwd)",target=/usr/share/nginx/html nginx

Step 4  Create the file in your current share folder  
        vi index.html
        
        Put some content in the file
        <html>
        <body>
        <p>this is the example of bind volume</p>
        </body>
        </html>

        save this file .

Step 5  Goto the Browser localhost:8080/index.html
        you can see that your file that you created are available in docker container without stop and login inot the container.
```





