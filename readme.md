GITHUB LINK : https://github.com/NagaprajwalB/stack_craft.git

AWS EC2 PUBLIC IP: http://18.61.27.253/  

Docker container IP : http://18.61.27.253:90/ 

STEPS for deployment 
* Create an EC2 instance in AWS
* Install the git, apache2, docker 
```
# GIT INSTALLATION
sudo apt install git 
```
```
# APACHE2 INSTALLATION
sudo apt install apache2
```
```
# DOCKER INSTALLATION
sudo apt install docker.io
sudo usrmod -aG docker $USER     # To run commamnds without sudo
newgrp docker  
```
* Clone the github repo to ec2 
* Copy all the files and past to /var/www/html 
* In security group give port number to access or allow all traffic [0.0.0.0/0]
* Access through [ EC2 public-ip ]
* Create a Docker file for the apache application
* Build the docker file 
``` 
docker build -t stack:latest . 
```
* Run the docker file 
``` 
docker run -d -p 90:80 <container-id> 
```
* Intract with docker container 
```
docker exec -it <container-id> bash
```
* Access through [ ec2-public-id:90 ]