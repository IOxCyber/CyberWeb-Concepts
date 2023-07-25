## Docker:
- Open-source containerization tool for developing, shipping, and running applications.
- Containerization: the process of packaging an application and its dependencies, runtime libraries, and settings into a single standardized unit called a container.
- Docker is written in the Go programming language.
- Docker uses a technology called `namespaces to provide the isolated workspace called the container.`

## Architecture:
- Docker uses a client-server architecture.
-  
- <img width="500" alt="image" src="https://github.com/IOxCyber/CyberDev/assets/40174034/20493b86-e341-4157-a93b-1c743d1e8ead">

### Components:
## 1. Docker Images: 
- a `read-only template that contains the application code, runtime, libraries`, environment variables, and any other dependencies to run the App.
- `built based on a Dockerfile` (which defines the instructions to create the image) & `stored in Docker Registry.`

## 2. Docker Containers:
- `a running instance of a Docker image.`
- a separate process on your machine that is isolated from all other processes on the host machine.
- This isolation leverages kernel namespaces and cgroups.
- Each container has its filesystem, network stack, and process space.
- <img width="500" alt="image" src="https://github.com/IOxCyber/CyberDev/assets/40174034/1f418ebd-47b5-4b2a-9534-98de573a3b86">


## 3. Docker Engine:
- 




## Docker Deamon:
- The Docker client talks to the Docker daemon.
- The Docker client and daemon communicate using a REST API,

## Docker client:
- 

- a container is a running instance of an image.
- a container is nothing but a running process, with some added encapsulation features applied to it to keep it isolated from the host and other containers.


- Docker VS Virtual Machines
- <img width="519" alt="image" src="https://github.com/IOxCyber/CyberDev/assets/40174034/638e54e7-ef0c-4c4e-8f8c-be844d530493">













