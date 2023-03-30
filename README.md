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


## Useful Docker Commands

- Stop the Docker daemon and remove any running Docker containers:
```shell
sudo systemctl stop docker
sudo docker rm -f $(sudo docker ps -aq)
```

- Start a new container from an image
```shell
docker run <image name>
docker run <image name> <command> // this command overrides the default command
```

- List running containers
```shell
docker ps
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
```

- Stop a running container
```shell
docker stop
```

- Remove a stopped container
```shell
docker rm
```

- Remove a locally available image
```shell
docker rmi
```

- Display the logs of a running container
```shell
docker logs
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


## Useful Resources & Links

- Install Docker Desktop on Linux: https://docs.docker.com/desktop/install/linux-install/
- Install on Arch-based distributions: https://docs.docker.com/desktop/install/archlinux/
