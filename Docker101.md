## Docker: [More](https://medium.com/@saschagrunert/demystifying-containers-part-i-kernel-space-2c53d6979504)
- `Open-source containerization[^1] tool` for developing, shipping and running applications.
- Docker is `written in the Go` programming language.
- Docker uses a technology called `namespaces to provide the isolated workspace called the container.`
- `Platform as a service products` that `use OS-level virtualization` to deliver software in packages called containers.
- <img width="500" alt="image" src="https://github.com/IOxCyber/CyberDev/assets/40174034/f607d639-6fcb-4557-abaf-a2d9beab7c19">


## Architecture:
- Docker uses a client-server architecture & Docker Client uses REST-API to communicate with Docker Deamon.
- <img width="500" alt="image" src="https://github.com/IOxCyber/CyberDev/assets/40174034/20493b86-e341-4157-a93b-1c743d1e8ead">

### Components:
## 1. Docker Images: `like recipe book`
- `a read-only template used to create containers.`
- `built based on a Dockerfile` (which defines the instructions to create the image) & `stored in Docker Registry.`
- Dockerfile: `A Textfile specifies the application code, runtime, libraries, environment variables, and other dependencies` needed to run the application.
- <img width="500" alt="image" src="https://github.com/IOxCyber/CyberDev/assets/40174034/a580f605-1017-451d-97e0-ae2cc46b0749">


## 2. Docker Containers: 
- `a running instance of a Docker image.`
- a separate process on your machine that is isolated from all other processes on the host machine.
- This isolation leverages the host system's kernel namespaces and cgroups.
- Each container has its own isolated filesystem, network stack, and process space.
- <img width="500" alt="image" src="https://github.com/IOxCyber/CyberDev/assets/40174034/1f418ebd-47b5-4b2a-9534-98de573a3b86">

## 3. Docker Engine:
- `Manages containers, used for building, running, and distributing Docker images.`
- `runs as a daemon on the host system` and provides a `command-line interface (CLI) and a REST API` for interacting with containers and images.

## 4. Docker Registry:
- a `centralized repository for storing Docker images.`
- `Docker Hub is the default public registry provided by Docker`, containing a vast collection of pre-built images.

## 5. Docker Deamon:
- `background service that runs on the host operating system and manages Docker objects` such as containers, images, volumes, networks
- The Docker client talks to the Docker daemon.
- The Docker client and daemon communicate using a REST API.

## 6. Docker client:
- AKA Docker CLI (Command-Line Interface) is a command-line tool.
- performs “build” and “run” operations for the purpose to connect with Docker Host.
- `allows users to interact with the Docker Daemon and manage Docker objects` like containers, images, volumes, and networks.

## 7. Docker Compose:
- a YAML file consisting of all the details regarding various services, networks, and volumes that are needed for setting up the Docker-based application.

## 8. docker namespace:
- Linux feature that ensures OS resources partition in a mutually exclusive manner.
- ensure that the containers are portable and they don't affect the underlying host.
- eg. PID, Mount, User, Network, IPC

## Docker VS Virtual Machines
- <img width="519" alt="image" src="https://github.com/IOxCyber/CyberDev/assets/40174034/638e54e7-ef0c-4c4e-8f8c-be844d530493">


## Lifecycle:
- <img width="500" alt="image" src="https://github.com/IOxCyber/CyberDev/assets/40174034/430f951a-8c90-41fb-be4c-cd08769de2b8">


## Interview Questions:
1. Hypervisor is a software that makes virtualization happen eg. Virtual Box, VMware:  
- <img width="502" alt="image" src="https://github.com/IOxCyber/CyberDev/assets/40174034/d07adaa6-5502-4b52-9dc2-ae1d6f714911">

2. https://www.interviewbit.com/docker-interview-questions/







[^1]: Containerization: the `process of packaging an application and its dependencies, runtime libraries`, and settings into a single standardized unit called a container.
A containerization is a form of virtualization through which applications are run in containers (isolated user spaces) all using a shared OS.
