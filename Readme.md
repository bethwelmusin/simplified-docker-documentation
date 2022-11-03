<!-- Components of Docker -->

The main components of Docker include – Docker clients and servers, Docker images, Dockerfile, Docker Registries, and Docker containers.

Docker Clients and Servers– Docker has a client-server architecture. The Docker Daemon/Server consists of all containers. The Docker Daemon/Server receives the request from the Docker client through CLI or REST APIs and thus processes the request accordingly.



Docker Images– Docker images are used to build docker containers by using a read-only template. The foundation of every image is a base image eg. base images such as – ubuntu14.04 LTS, and Fedora 20. 

Docker File– Dockerfile is a text file that contains a series of instructions on how to build your Docker image. This image contains all the project code and its dependencies. 

Docker Registries– Docker Registry is a storage component for Docker images. We can store the images in either public/private repositories so that multiple users can collaborate in building the application. Docker Hub is Docker’s cloud repository. 

Docker Containers– Docker Containers are runtime instances of Docker images. Containers contain the whole kit required for an application, so the application can be run in an isolated way.


Docker Compose is a tool with which we can create a multi-container application. It makes it easier to configure and 
run applications made up of multiple containers. For example, suppose you had an application that required WordPress and MySQL, you could create one file which would start both the containers as a service without the need to start each one separately. We define a multi-container application in a YAML file.



step by step to dockerize a project


1. first step is to install docker in your machine
The most important step to be successful is to actually install Docker. The Docker website has getting started guides for Mac, Windows, and Linux.

    Linux - https://docs.docker.com/linux/started/
    Mac - http://docs.docker.com/mac/started/
    Windows - http://docs.docker.com/windows/started/



2. create a project or clone an existing application


3. confirm if docker is installed , run "docker version" in your command line



 creating docker image

4. create a dockerfile in your project called "Dockerfile"

5. To your Dockerfile, add:

FROM — image name.

WORKDIR - project directory

COPY - requirements file

RUN — running file with all the requirements file

EXPOSE — Set a specific port to listen by Docker Container.

ADD /COPY .. — uses for copy all files.



 i.e 

dockerfile for django application

FROM python:3.6

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /usr/src/app
COPY requirements.txt ./
RUN pip install -r requirements.txt
COPY . .

EXPOSE 8000
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]


building image

Now we need to build our Docker image and run it. This can be done by the following command :

to build image:

sudo docker build -t image_name .


     to see if image exit use and you can see all your images.

sudo docker images


running docker application

to run docker application use:

sudo docker run -p 8000:8000 image_name





