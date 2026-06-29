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
sudo usrmod -aG docker $USER
newgrp docker  
```
* clone the github repo to ec2 
* copy all the files and past to /var/www/html 
* In security group give port number to access or allow all traffic [0.0.0.0/0]
* Access through [ EC2 public-ip ]
* create a Docker file for the apache application
* build the docker file 
``` 
docker build -t stack:latest . 
```
* Run the docker file 
``` 
docker run -d -p 90:80 <container-id> 
```
* access through the [ ec2-public-id:90 ]