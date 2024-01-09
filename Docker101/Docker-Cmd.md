## 1. Docker CMD Cheatsheet: [More](https://www.hostinger.in/tutorials/docker-cheat-sheet?ppc_campaign=google_search_generic_hosting_all&bidkw=defaultkeyword&lo=9062084&gclid=Cj0KCQjwiIOmBhDjARIsAP6YhSWZqeUH50uOmMi2B7_78afHw_bQ0jBjWj9pfZgDoRwvnuZJ0Ca6grQaApuBEALw_wcB#Docker_Architecture)
- <img width="498" alt="image" src="https://github.com/IOxCyber/CyberDev/assets/40174034/2d675895-dc22-4919-bc3f-0b863097fda9">

## 2. Basic Cmds: [Official Guide](https://docs.docker.com/guides/get-started/)
### Info Commands:
- `docker ps`: List all containers (including stopped ones) on your system. eg. `docker ps -a`
- `docker version`:	Show the Docker version information. eg. `docker --version [OPTIONS]`
- `docker info`: Display system-wide information about Docker Image, Configuration, Containers, etc.
- `docker images`: Displays all the available downloaded docker Images on the system.
- `docker logs CONTAINER_ID`: View the logs of a running or stopped container.
- `docker build`: Builds an image from a Dockerfile in the current directory. `eg. docker build -t IMAGE_NAME:TAG(eg. my-python-app) Dockerfile_Path`

### Container Interaction Commands:
- `docker search <Image-Name>`: Search the Image-Name in the Docker Registry.
- `docker pull`: Pull an image or a repository from a registry. eg. `docker pull ubuntu:latest`
- `docker run (options) image (command) (arg...)`: used to create and start a new Docker container from provided images.
```
eg. docker run -d -p 8080:80 --name web_app -v /path/on/host:/app/data web_app_image:latest

Options:
-d: Runs the container in the background (detached mode).
-p 8080:80: Maps port 8080 on the host to port 80 on the container.
--name web_app: Assigns the name "web_app" to the container.
-v /path/on/host:/app/data: Mounts the host directory **/path/on/host** into the container at **/app/data.**
web_app_image:latest: Specifies the Docker image "web_app_image" with the tag "latest" to create the container.
```
- `docker push`: Push an image or a repository to a registry. eg. `$ docker image push dockerimage`
- `docker update`:	Update the configuration of one or more containers. eg. `docker update --cpus 2 --memory 512m <container_id>`
- `docker exec`: To run a command inside a running Docker container. eg. `docker exec -it my_container bash` (-it: enter an interactive terminal inside the container & Use BASH shell)


### Clean Up Commands:
- `docker image prune`:	Clears an unused image.
- `docker rmi image_id_or_name`:	Remove a Docker image from the local system.
- `docker stop/start/restart/rm CONTAINER_ID`: stop/start/restart/remove a running container by its ID. 
- `docker swarm leave`:	Leaves a swarm
- `docker kill $(docker ps -q)`:	Stops all running containers

### Registry Commands:
- <img width="500" alt="image" src="https://github.com/IOxCyber/CyberDev/assets/40174034/f7f44782-d3ab-4786-bc19-e9bf0c19471f">
