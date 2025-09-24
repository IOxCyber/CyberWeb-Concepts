## Docker: [Cheatsheet](https://dockerlabs.collabnix.com/docker/cheatsheet/) (Docker Playground)[https://labs.play-with-docker.com/]
- Open-source containerization[^1] tool for developing, shipping, and running applications.
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
FROM python:3.9

# Set the working directory inside the container
WORKDIR /app

# Copy the application code into the container
COPY app.py /app/

# Install the required dependencies for the Python application
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

# 2. Docker Containers: `running instance of a Docker image.`
- lightweight, standalone, executable package of software.
- a separate process on your local machine that is isolated from all other processes on the host machine.
- This isolation leverages the host system's kernel namespaces and cgroups.
- Each container has its own isolated filesystem, network stack, and process space.
- `package that contains all the required prerequisites to run an application.`
- <img width="500" alt="image" src="https://github.com/IOxCyber/CyberDev/assets/40174034/1f418ebd-47b5-4b2a-9534-98de573a3b86">

# 3. Docker Engine or Docker Server: `Docker Container Management` `core engine of Docker`
- `Manages containers, used for building, running, and distributing Docker images.`
- `runs as a daemon on the host system` and provides a `command-line interface (CLI) and a REST API` for interacting with containers and images.

# 4. Docker Deamon: `Background Service: dockerd`
- background `service that runs on the host operating system and manages Docker containers, images`
- The Docker client and daemon communicate using a REST API.
- Dockerd is responsible for starting, stopping, and managing containers, as well as pulling and pushing Docker images.


# 5. Docker Host & Client:
## Docker Host: `where Docker is installed`
- Refers to the `physical or virtual machine where Docker is installed and runs.`
- Runs the Docker Daemon (Dockerd)

## Docker Client: `CLI tool to perform action`
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

## 7. Docker Compose: `Used to set up the Docker-based app`
- YAML file to specify the services, networks, and volumes needed for your application.
- With Docker Compose, you can start, stop, and scale all the services.
- Can be used JSON file.

## 8. Docker namespace: `Isolate the process from host kernel`
- Linux feature that `ensures OS resources partition` in a mutually exclusive manner.
- ensure that the containers are portable and they don't affect the underlying host.
- act as `virtual boundaries that separate/isolate the resources/processes of the container` from those of the host system and other containers.
- Filesystem, its unique IP address and network interfaces, process ID (PID) space, different mounted file systems, shared memory and message queues. 
- eg. PID, Mount, User, Network, IPC

## 9. Docker Hub: `default and official repository for Docker images`
- a public cloud-based registry provided by Docker for storing public images of the containers.

## 10. Docker Registry: `Docker Image Store` (Docker-Hub Registry)[https://hub.docker.com/]
- a `centralized repository for storing Docker images.`
- `Docker Hub is the default public registry` provided by Docker, containing a vast collection of pre-built images.


## 11. Docker Volume:
- A persistent storage mechanism that exists outside the container's lifecycle, used to store and share data between containers and the host system.

## Docker Lifecycle:
- <img width="500" alt="image" src="https://github.com/IOxCyber/CyberDev/assets/40174034/430f951a-8c90-41fb-be4c-cd08769de2b8">

## Docker containers advantages:
- including improved security through container isolation, faster deployment times due to the lightweight nature of containers
- consistency across different environments, ensuring that applications run consistently across development, testing, and production environments.
- containerization technology makes it easier to scale applications and manage resources efficiently.

- <img width="500" alt="image" src="https://github.com/IOxCyber/CyberDev/assets/40174034/f607d639-6fcb-4557-abaf-a2d9beab7c19">

## Interview Questions:
1. Docker VS Virtual Machines: Problem with VMs > Resource Intensive, Slow to start
- <img width="519" alt="image" src="https://github.com/IOxCyber/CyberDev/assets/40174034/638e54e7-ef0c-4c4e-8f8c-be844d530493">

2. `Hypervisor` is a software that makes virtualization happen eg. Virtual Box, VMware:  
- <img width="502" alt="image" src="https://github.com/IOxCyber/CyberDev/assets/40174034/d07adaa6-5502-4b52-9dc2-ae1d6f714911">

3. `Docker Swarm`
- Container orchestration tool provided by Docker, Inc.
- Allows you to `create and manage a cluster of Docker nodes` (machines) to deploy, scale, and manage containerized applications at scale.
- Provides built-in load balancing for services, distributing incoming traffic across all containers running the service.
- Kubernetes (another container orchestration platform), some users have transitioned to Kubernetes for more complex container orchestration requirements.

4. Short Information:

Dockerfile = Recipe (instructions to build an image).

Docker Image = Baked dish (ready-to-use package).

Docker Container = Served meal (running instance of the image).

[^1]: Containerization: the `process of packaging an application and its dependencies, runtime libraries`, and settings into a single standardized unit called a container.
Containerization is a form of virtualization through which applications are run in containers (isolated user spaces) all using a shared OS.
