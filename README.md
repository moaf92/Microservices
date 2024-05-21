# Microservices
in this project we are going to containerize a microservice application we have four services here. nginx service which is frontend api gateway all the communication between microservices happens through this gateway which will listen for the request and route based on headers'urls' in this app if it comes on root it will routes to client microservices which is written in angular, /api will route to nodejs application which will use mango db,/webapi will route to java application which will also use db mysql db 

# Steps to follow
- First we will set up an ubuntu ec2 instance and in userdata we will install docker engine docker compose and add ubuntu user to the docker group 
- For client dockerfile since angular returns html file so we will run it on nginx but  before we are going to build the artifact using node base image "using multistage dockerfile"
- For nodeapi docker file using node base image in"multistage dockerfile" first one for building the artifact, second copying this artifact to workdir we mention
- For javaapi dockerfile also multistage docker file based on open jdk image because we will use maven to build the artifact after this copying the artifact to the next stage to keep the size of image small 
  as we can 
- for nginx we will use the official image but we will attach our config file as a volume
- after this we will use docker compose and mention our microservices and dbs images to build 
