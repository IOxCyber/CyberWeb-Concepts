## Docker: [Cheatsheet](https://dockerlabs.collabnix.com/docker/cheatsheet/) [Docker Playground](https://labs.play-with-docker.com/)
- *`Open-source containerization tool`* [^1] for developing, shipping, and running applications.
- Docker `use OS-level/Kernel virtualization` to deliver software in packages called containers.
- `Written in the Go`, uses a technology called `namespaces, cgroups to provide the isolated workspace called the container.`
- Work as an enabler for `Platform as a service products.`

## Namespace & Cgroups (Control Groups):
- Linux Specific (Windows uses either hyperV or LCOW & MacOs archive it thu a Linux VM)


## Architecture:
- Docker uses a client-server architecture & Docker Client uses REST-API to communicate with Docker Deamon.
- <img width="500" alt="image" src="https://github.com/IOxCyber/CyberDev/assets/40174034/20493b86-e341-4157-a93b-1c743d1e8ead">

# Components:

## 0: Dockerfile:
A text file that contains all the commands a user could call on the CLI to assemble an image.
- Image are `built based on a Dockerfile` (which defines the instructions to create the image).

```
Example: Dockerfile
# Use the official Python image as the base image
# Get it from Docker hub

FROM python:3.9


# Set the working directory inside the container
WORKDIR /app


# Copy the application code into the container directory
COPY app.py /app/


# Install the required dependencies for the Python application inside container
RUN pip install Flask


# Expose port 5000 for the Flask web server
EXPOSE 5000


# Set the entry point command to run the Python application using Flask
CMD ["python", "app.py"]
```

## 1. Docker Image: 
- A read only 'blueprint/template to create the containers.'
- An executable package/snapshot with the application code, runtime(Interpreter to execute the code), libraries, environment variables, and other dependencies needed to run the application.

- <img width="500" alt="image" src="https://github.com/IOxCyber/CyberDev/assets/40174034/a580f605-1017-451d-97e0-ae2cc46b0749">

# 2. Docker Containers: `lightweight, standalone, executable package of software.`
- Running instance of a Docker image.
- a separate process on your local machine that is isolated from all other processes on the host machine.
- This isolation leverages the host system's kernel namespaces and cgroups.
- Each container has its own isolated filesystem, network stack, and process space.
- `package that contains all the required prerequisites to run an application.`
- <img width="500" alt="image" src="https://github.com/IOxCyber/CyberDev/assets/40174034/1f418ebd-47b5-4b2a-9534-98de573a3b86">

# 3. Docker Engine or Docker Server: 
- To manage the full lifecycle of Docker objects (images, containers, networks, volumes).
- `Manages containers, used for building, running, and distributing Docker images.`
- Composed of multiple parts:
`Docker Daemon + REST API + Docker CLI (Client).`

- Eg. Docker Engine(Dockerd, Default engine for Docker Desktop), Containerd (used by Docker/k8), CRI-O (k8 specific) ,LXD (Chronicals) or cloud vendor specific OCI Compatible container images.

# 4. Docker Deamon: `Background Service: dockerd`
- background `service that runs on the host operating system and manages Docker containers, images`
- The Docker client and daemon communicate using a REST API.
- Dockerd is responsible for starting, stopping, and managing containers, as well as pulling and pushing Docker images.
- By default, listens on a Unix socket (/var/run/docker.sock)


# 5. Docker Host & Client:
## Docker Host: `where Docker is installed`
- Refers to the `physical or virtual machine where Docker is installed and runs.`
- Runs the Docker Daemon (Dockerd)

## Docker CLI Client: `CLI tool to perform action`
- AKA Docker CLI (Command-Line Interface) is a command-line tool.
- Performs “build” and “run” operations to connect with Docker Host.
- `allows users to interact with the Docker Daemon and manage Docker objects` like containers, images, volumes, and networks.

## 6. Docker Compose: 
- A tool that lets you define and manage multi-container Docker applications using a single YAML file.
- All run together like a single, connected app, in one virtual network, defined in one YAML file.
- `docker-compose up -d`

```
version: '3.8'

services:
  dvwa:
    image: vulnerables/web-dvwa
    ports:
      - "8080:80"
  
  metasploitable:
    image: tleemcjr/metasploitable2
    ports:
      - "8888:80"
  
  juice:
    image: bkimminich/juice-shop
    ports:
      - "3000:3000"
```

## 7. Docker Lifecycle:
- <img width="500" alt="image" src="https://github.com/IOxCyber/CyberDev/assets/40174034/430f951a-8c90-41fb-be4c-cd08769de2b8">

## 8. Docker namespace: `Isolate the process from host kernel`
- Linux feature that `ensures OS resources partition` in a mutually exclusive manner.
- ensure that the containers are portable and they don't affect the underlying host.
- act as `virtual boundaries that separate/isolate the resources/processes of the container` from those of the host system and other containers.
- Filesystem, its unique IP address and network interfaces, process ID (PID) space, different mounted file systems, shared memory and message queues. 
- eg. PID, Mount, User, Network, IPC

## 9. Docker Hub: `default and official repository for Docker images`
- a public cloud-based registry provided by Docker for storing public images of the containers.

## 10. Docker Registry: `Docker Image Store` [Docker-Hub Registry](https://hub.docker.com)
- a `centralized repository for storing Docker images.`
- `Docker Hub is the default public registry` provided by Docker, containing a vast collection of pre-built images.


## 11. Docker Volume:
- A persistent storage mechanism that exists outside the container's lifecycle, used to store and share data between containers and the host system.
- Volumes are stored in /var/lib/docker/volumes/ by default.


## Docker containers advantages:
- including improved security through container isolation, faster deployment times due to the lightweight nature of containers
- consistency across different environments, ensuring that applications run consistently across development, testing, and production environments.
- containerization technology makes it easier to scale applications and manage resources efficiently.
- Containers are immutable → making deployments predictable & rollback-friendly.

- <img width="500" alt="image" src="https://github.com/IOxCyber/CyberDev/assets/40174034/f607d639-6fcb-4557-abaf-a2d9beab7c19">


[^1]: Containerization: the `process of packaging an application and its dependencies, runtime libraries`, and settings into a single standardized unit called a container.
Containerization is a form of virtualization through which applications are run in containers (isolated user spaces) all using a shared OS.
