
# Important Docker Commands





* Docker home directory :
```bash
  /var/lib/docker
```
* To check the version of docker :
```bash
  docker --version
```
* To list the images we have locally :
```bash
  docker images
```
* To get get the images from dockerhub :
```bash
  docker pull <imagename>
```
* To upload the images to dockerhub :
```bash
  docker push <username/imagename>
```
* login to dockerhub form cli :
```bash
  docker login
```
* To craete and run a container from the image :
```bash
  docker run -d --name <conname> <imagename>
```
* To list all the running containers :
```bash
  docker ps
```
* To list all running and non-running containers :
```bash
   docker ps -a
```
* Login to container :
```bash
   docker exce -it <conname/Id> /bin/bash
```
* Login to container :
```bash
   docker attach <conname/Id>
```
* To quit/exit from the container :
```bash
   ctrl p+q
```
* To build a custom image from a Dockerfile :
```bash
   docker build -t <yourimgname> <Dockerfilepath>
```
* To know the info of image :
```bash
   docker inpect <imagename/Id>
```
* To know info of container :
```bash
   docker inspect <conname/Id>
```
* To stop a running container :
```bash
   docker stop <conname/Id>
```
* To remove a stopped container :
```bash
   docker rm <conname/Id>
```
* To remove a running container :
```bash
   docker rm -f <conname/Id>
```
* To remove an image :
```bash
   docker rmi <imagename>
```
* To run a container with port mapping :
```bash
   docker run -d --name <conname> -p <ports> <imagename>
   EX: docker run -d --name nginxcon -p 80:80 nginx:latest 
```
* To get an image with a tag :
 ```bash
   docker pull <imagename>:tag

```
