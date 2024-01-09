## 1. Docker CMD Cheatsheet: [More](https://www.hostinger.in/tutorials/docker-cheat-sheet?ppc_campaign=google_search_generic_hosting_all&bidkw=defaultkeyword&lo=9062084&gclid=Cj0KCQjwiIOmBhDjARIsAP6YhSWZqeUH50uOmMi2B7_78afHw_bQ0jBjWj9pfZgDoRwvnuZJ0Ca6grQaApuBEALw_wcB#Docker_Architecture)
- <img width="498" alt="image" src="https://github.com/IOxCyber/CyberDev/assets/40174034/2d675895-dc22-4919-bc3f-0b863097fda9">

## 2. Basic Cmds: [Official Guide](https://docs.docker.com/guides/get-started/)
### Build Commands:
- `docker ps`: List all containers (including stopped ones) on your system. eg. `docker ps -a`
- `docker version`:	Show the Docker version information. eg. `docker --version [OPTIONS]`
- `docker info`: Display system-wide information about Docker Image, Configuration, Containers, etc.
- `docker images`: Displays all the available downloaded docker Images on the system. 
- `docker build`: Builds an image from a Dockerfile in the current directory. `eg. docker build -t IMAGE_NAME:TAG(eg. my-python-app) Dockerfile_Path`

### Container Interaction Commands:
- `docker search <Image-Name>`: Search the Image-Name in the Docker Registry.
- `docker pull`: Pull an image or a repository from a registry. eg. `docker pull ubuntu:latest`
- `docker run (options) image (command) (arg...)`: to create containers from provided images.
- `docker push`: Push an image or a repository to a registry. eg. `$ docker image push dockerimage`
- `docker update`:	Update the configuration of one or more containers. eg. `docker update --cpus 2 --memory 512m container_id`
- `docker exec`: To run a command inside a running Docker container. eg. `docker exec -it my_container bash` (-it: enter an interactive terminal inside the container & Use BASH shell)
- `docker logs CONTAINER_ID`: View the logs of a running or stopped container.

### Clean Up Commands:
- `docker image prune`:	Clears an unused image.
- `docker rmi image_id_or_name`:	Remove a Docker image from the local system.
- `docker stop/start/restart/rm CONTAINER_ID`: stop/start/restart/remove a running container by its ID. 
- `docker swarm leave`:	Leaves a swarm
- `docker kill $(docker ps -q)`:	Stops all running containers

### Registry Commands:
- <img width="500" alt="image" src="https://github.com/IOxCyber/CyberDev/assets/40174034/f7f44782-d3ab-4786-bc19-e9bf0c19471f">
