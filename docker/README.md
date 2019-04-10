# Docker

Docker is a software technology providing operating-system-level virtualization also known as containers.

## Terminology

**Container**

A lightweight and portable executable image that contains software and all of its dependencies.

**Image**

Stored instance of a container that holds a set of software needed to run an application.

**Dockerfile**

A Dockerfile is a text document that contains all the commands a user could call on the command line to assemble an image. Using docker build users can create an automated build that executes several command-line instructions in succession.

**Docker Registry**

Docker Trusted Registry (DTR) is a commercial product that enables complete image management workflow, featuring LDAP integration, image signing, security scanning, and integration with Universal Control Plane. DTR is offered as an add-on to Docker Enterprise subscriptions of Standard or higher.

## Most Commonly Used Commands

### Docker Image

`docker pull IMAGE:TAG` - pulls a new image\
`docker build -t IMAGE_NAME` - build from local Dockerfile\
`docker build -f Dockerfile.dev .` - force building for a specific environment\
`docker images` - shows a list of docker images\
`docker images -a` - shows a list of all docker images\
`docker image prune -a` - removes all unused images\
`docker rmi IMAGE_ID` - removes the image\
`docker tag IMAGE_ID username/container_name:tag` - tags the given image

### Docker Container

`docker push username/container_name:tag` - pushes the container image to Docker Hub (login first)\
`docker ps` - shows a list of running containers\
`docker ps --all` - shows all created containers\
`docker container ls -a` - shows all containers\
`docker run IMAGE_NAME` - runs the container\
`docker run --name NAME` - runs the container with a name\
`docker run -d IMAGE_NAME` - starts the container in the background\
`docker stop ID` - stops the container\
`docker logs ID` - shows the logs

### Other Commands

`docker login` - logs into Docker Hub
`docker system prune` - removes all containers

## Dockerfile

`COPY ./ ./` copies all files from local machine to image path
`WORKDIR path/to/folder` specifies the working directory

## Docker Volumes

TODO

## Docker Compose

TODO
