<!-- Components of Docker -->

The main components of Docker include – Docker clients and servers, Docker images, Dockerfile, Docker Registries, and Docker containers.

Docker Clients and Servers– Docker has a client-server architecture. The Docker Daemon/Server consists of all containers. The Docker Daemon/Server receives the request from the Docker client through CLI or REST APIs and thus processes the request accordingly.



Docker Images– Docker images are used to build docker containers by using a read-only template. The foundation of every image is a base image eg. base images such as – ubuntu14.04 LTS, and Fedora 20. 

Docker File– Dockerfile is a text file that contains a series of instructions on how to build your Docker image. This image contains all the project code and its dependencies. 

Docker Registries– Docker Registry is a storage component for Docker images. We can store the images in either public/private repositories so that multiple users can collaborate in building the application. Docker Hub is Docker’s cloud repository. 

Docker Containers– Docker Containers are runtime instances of Docker images. Containers contain the whole kit required for an application, so the application can be run in an isolated way.


Docker Compose is a tool with which we can create a multi-container application. It makes it easier to configure and 
run applications made up of multiple containers. For example, suppose you had an application that required WordPress and MySQL, you could create one file which would start both the containers as a service without the need to start each one separately. We define a multi-container application in a YAML file.



<!-- step by step to dockerize a project -->


1. first step is to install docker in your machine


2. create a project 

3. confirm if docker is installed , run docker version in your command line

 <!-- creating docker image -->

4. create a dockerfile in your application called "Dockerfile"

5. To your Dockerfile, add:




 





