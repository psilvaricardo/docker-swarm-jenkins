# Docker & Kubernetes
Docker and Kubernetes: The Complete Guide


# Various projects related to Docker & Kubernetes

Here are some projects related to Docker & Kubernetes, some of them are from the Udemy's 2023 versions.

* `Docker + Swarm Jenkins` for the [*Docker from A to Z™: Swarm + Jenkins*](https://www.udemy.com/course/a-practical-guide-to-docker-swarm-and-jenkins/) (Ed. 2023)
* `Docker & Kubernetes` for the [*Docker and Kubernetes: The Complete Guide*](https://www.udemy.com/course/docker-and-kubernetes-the-complete-guide/) (Ed. 2023)


## Installing Docker in Arch Linux

To install Docker on Arch Linux and ensure that your user has the necessary permissions to run it, you can follow these steps:

- Install Docker using the following command: 
```shell
sudo pacman -S docker
```
- Add your user to the docker group using the following command:
```shell
sudo usermod -aG docker $USER
```
- Start the Docker service using the following command:
```shell
sudo usermod -aG docker $USER
```
- Verify that Docker is running correctly by running the following command:
```shell
docker run hello-world
```
- Enable the Docker service to start automatically at boot time using the following command:
```shell
sudo systemctl enable docker
```
By following these steps, you should be able to install and configure Docker on Arch Linux and ensure that your user has the necessary permissions to run it without issues.

- Install docker buildx: https://docs.docker.com/engine/reference/commandline/buildx/
- https://docs.docker.com/desktop/install/linux-install/

## Useful Docker Commands

- Stop the Docker daemon and remove any running Docker containers:
```shell
sudo systemctl stop docker
sudo docker rm -f $(sudo docker ps -aq)
```

- Start a new container from an image
```shell
docker run = docker create + docker start // this should be identical
docker create <image name for this container> // creating a container has to do with creating the file system snapshot
docker start <container id to start> // this is when we actually execute whatever process that is supposed to be executed inside the container, it will not output anything to the console
docker start -a <container id to start> // same as the previous one, the -a parameter will make docker to watch for any output from the container and print it out to your terminal
docker run <image name> <command> // this command overrides the default command
docker run <image name> <command> // this command overrides the default command

// Container Port Mapping
docker run -p <port number of incoming request on localhost>:<port number listening inside the container> <imageId>
```

- List running containers
```shell
docker ps // list all the running containers
docker ps --all // list all the containers regardless of its status
```

- List locally available images
```shell
docker images
```

- Download an image from a registry
```shell
docker pull
```

- Upload an image to a registry
```shell
docker push
```

- Build a new image from a Dockerfile
```shell
docker build
```

- Run a command in a running container
```shell
docker exec
docker exec -it <container id> <command> // execute an additional command in a container attaching to the STDIN
```

- Stop a running container
```shell
docker stop <container id> // a hardware signal SIGTERM is send to the primary process inside that container with a 10 seconds grace period
docker kill <container id> // a hardware signal SIGKILL is send to the primary process inside that container
```

- Remove a stopped container
```shell
docker rm
docker system prune -a --volumes // it will remove all stopped containers, all dangling images and all dangling build cache.
```

- Remove a locally available image
```shell
docker rmi
```

- Manage Docker networks
```shell
docker network
```

- Manage Docker volumes
```shell
docker volume
```

- Manage multi-container applications with Docker Compose
```shell
docker-compose
```

- Retrieving / Get logs from a Container
```shell
docker logs <container id> 
```

- Adding TAGs to the docker images
```shell
docker build -t <your-DockerHub-Id>/<ImageName>:<version> <directory of files or folders used for the build>
```

## Docker Files

- What's a Docker file? 
A Dockerfile is a text file that contains a set of instructions that are used to build a Docker image. The Dockerfile specifies the components and configuration required for the image, including the base image, the software packages to be installed, and any customizations that need to be made. Using a Dockerfile, developers can define a repeatable and consistent process for building Docker images that can be easily shared and deployed across different environments. Docker images built from Dockerfiles are lightweight and portable, making them ideal for use in container-based deployments.


## Useful Resources & Links

- Docker Hub: https://hub.docker.com/
- https://docs.docker.com/develop/develop-images/build_enhancements/
- https://docs.docker.com/engine/reference/commandline/build/#specifying-external-cache-sources
- https://www.docker.com/blog/advanced-dockerfiles-faster-builds-and-smaller-images-using-buildkit-and-multistage-builds/
- Install Docker Desktop on Linux: https://docs.docker.com/desktop/install/linux-install/
- Install on Arch-based distributions: https://docs.docker.com/desktop/install/archlinux/

## Some known issues

- As of April 01, 2023; after installing docker-desktop in arch linux, docker command as user does not connect any more to the docker daemon. For the fix, follow this link: https://github.com/docker/desktop-linux/issues/20#issuecomment-1221529171
