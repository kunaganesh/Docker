
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

## Feedback

If you have any feedback, please reach out to us at fake@fake.com


## 🚀 About Me
I'm a full stack developer...


# Hi, I'm Katherine! 👋


## 🔗 Links
[![portfolio](https://img.shields.io/badge/my_portfolio-000?style=for-the-badge&logo=ko-fi&logoColor=white)](https://katherineoelsner.com/)
[![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/)
[![twitter](https://img.shields.io/badge/twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/)


## Other Common Github Profile Sections
👩‍💻 I'm currently working on...

🧠 I'm currently learning...

👯‍♀️ I'm looking to collaborate on...

🤔 I'm looking for help with...

💬 Ask me about...

📫 How to reach me...

😄 Pronouns...

⚡️ Fun fact...


## 🛠 Skills
Javascript, HTML, CSS...


## Installation

Install my-project with npm

```bash
  npm install my-project
  cd my-project
```
    
## Lessons Learned

What did you learn while building this project? What challenges did you face and how did you overcome them?


## License

[MIT](https://choosealicense.com/licenses/mit/)


![Logo](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/th5xamgrr6se0x5ro4g6.png)

