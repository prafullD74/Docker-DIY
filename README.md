# Docker-DIY
Docker commands and info in short

- **Docker** is a platform and tool that allows developers to easily create, deploy, and run applications in a consistent, isolated environment called a container.
- The **Container** is a lightweight, standardized, and sealed box that holds your application and everything it needs to run (code, libraries, dependencies, and settings).
- A **container** is a standalone, executable package that includes your application and all its dependencies..
- **Docker Image** is a read-only template used to create a container. It's a static blueprint.
- **Dockerfile** is a simple text file that contains a series of instructions for how to build a Docker image. It's a recipe that tells Docker what to do, step by step, to package your application correctly.
- A **Docker Registry** is a place to store and share Docker images.
- **Docker Hub** is the largest public registry, acting as a kind of app store for Docker images.

<img width="292" height="289" alt="image" src="https://github.com/user-attachments/assets/5134db53-2002-4e2b-8778-3110726976cf" />

[DockerImage](https://learn.microsoft.com/en-us/dotnet/architecture/microservices/container-docker-introduction/docker-terminology)

## The Problem Docker Solves
1. The biggest problem Docker addresses is the "It works on my machine!" issue.

## Docker architecture
- Docker uses a client-server [architecture](https://docs.docker.com/get-started/docker-overview/#docker-architecture).
- The Docker daemon (dockerd) listens for Docker API requests and manages Docker objects such as images, containers, networks, and volumes. A daemon can also communicate with other daemons to manage Docker services.
- The Docker client can communicate with more than one daemon.

## [Docker objects](https://docs.docker.com/get-started/docker-overview/#docker-objects)
- Docker Desktop includes the Docker daemon (dockerd), the Docker client (docker), Docker Compose, Docker Content Trust, Kubernetes, and Credential Helper.
- An image is a read-only template with instructions for creating a Docker container.
- Each instruction in a Dockerfile creates a layer in the image. When you change the Dockerfile and rebuild the image, only those layers which have changed are rebuilt. This is part of what makes images so lightweight, small, and fast, when compared to other virtualization technologies.
- When a container is removed, any changes to its state that aren't stored in persistent storage disappear.
- By default, containers can connect to external networks using the host machine's network connection.

- Docker is written in the Go programming language.
- Docker uses namespaces to create isolated workspaces called containers, with each container receiving its own set of namespaces upon creation.
- These namespaces provide a layer of isolation. Each aspect of a container runs in a separate namespace and its access is limited to that namespace.
