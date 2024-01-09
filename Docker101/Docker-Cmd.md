## 1. Docker CMD Cheatsheet: [More](https://www.hostinger.in/tutorials/docker-cheat-sheet?ppc_campaign=google_search_generic_hosting_all&bidkw=defaultkeyword&lo=9062084&gclid=Cj0KCQjwiIOmBhDjARIsAP6YhSWZqeUH50uOmMi2B7_78afHw_bQ0jBjWj9pfZgDoRwvnuZJ0Ca6grQaApuBEALw_wcB#Docker_Architecture)

## 2. Basic Cmds: [Official Guide](https://docs.docker.com/guides/get-started/)
### Info Level Commands:
- `docker ps`: List all containers (including stopped ones) on your system. eg. `docker ps -a`
- `docker version`:	Show the Docker version information. eg. `docker --version [OPTIONS]`
- `docker info`: Display system-wide information about Docker Image, Configuration, Containers, etc.
- `docker images`: Displays all the available downloaded docker Images on the system.
- `docker logs CONTAINER_ID`: View the logs of a running or stopped container.

### 3. Container Interaction Commands:
- `docker search <Image-Name>`: Search the Image-Name in the Docker Registry.
- `docker pull`: Pull an image or a repository from a registry. eg. `docker pull ubuntu:latest`
- `docker push`: Push an image or a repository to a registry. eg. `$ docker image push dockerimage`
- `docker update`:	Update the configuration of one or more containers. eg. `docker update --cpus 2 --memory 512m <container_id>`
- `docker exec`: To run a command inside a running Docker container. eg. `docker exec -it my_container bash` (-it: enter an interactive terminal inside the container & Use BASH shell)
> Note: By default, the docker containers will exit immediately if you do not have any task running on the container. (echo > Exit)
> To keep the container running in the background, try to run it with --interactive (or -i) argument or --tty (or -t) or -it directly

### 4. Container Build/Run Commands:
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

- `docker build`: Initiates the process of building a Docker image from a Dockerfile (Need a configured Dockerfile to build an image)
```
Syntex: docker build -t IMAGE_NAME:TAG Dockerfile_Path`

Example: docker build -t my-node-app:Latest . (here it's current Directory_Path)

IMAGE_NAME: Name of the Image which will be built from Dockerfile
TAG: Latest or anything, just for tagging the image
-t my-node-app:Latest : Assigns the name "my-node-app" & "Latest" tag for the built image.
.(Dot): Specifies the Dockerfile Location, indicating that the Dockerfile is in the current directory.
```
> Note: The docker build command assumes a default filename of Dockerfile if you don't specify a different filename. So, if your Dockerfile is named Dockerfile in the current directory, you don't need to explicitly mention the filename. If your Dockerfile has a different name, you can specify it using the -f option: docker build -t IMAGE_NAME:TAG -f CustomDockerfile .

### 5. Clean Up Commands:
- `docker stop/start/restart/rm CONTAINER_ID`: stop/start/restart/remove a running container by its ID.

- `docker rmi image_id_or_name`:	Remove a Docker image from the local system. (Make sure to `stop and remove the associated container`)
> docker stop CONTAINER_ID >> docker rm CONTAINER_ID >> docker image rm IMAGE_ID

- `docker image prune [OPTIONS]`: used to remove unused or dangling Docker images
```
Options:
-a, --all: Remove all unused images, not just dangling ones, AND -f, --force: Do not prompt for confirmation.
```
> Note: Dangling Docker images refer to images that have no associated containers and are not tagged with any name. These images are typically created during the build process or when intermediate layers are produced. Since they have no explicit name or tag, they are considered "dangling" or untagged.

- `docker swarm leave`:	Leaves a swarm
- `docker kill $(docker ps -q)`:	Stops all running containers

### 6. Registry Commands:
- <img width="500" alt="image" src="https://github.com/IOxCyber/CyberDev/assets/40174034/f7f44782-d3ab-4786-bc19-e9bf0c19471f">
