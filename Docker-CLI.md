# [Consolidated Docker CLI Cheat Sheet](https://spacelift.io/blog/docker-commands-cheat-sheet)

>Docker CLI is used end-to-end in DevOps to build images, run and debug containers, manage networking and storage, clean hosts, push images to registries, and enforce security using SBOM and vulnerability scanning.

| **Category**                     | **Command**                            | **Purpose**                        | **Real-World DevOps Use Case**                    |
| -------------------------------- | -------------------------------------- | ---------------------------------- | ------------------------------------------------- |
| **General**                      | `docker version`                       | Show Docker client/server versions | Verify Docker compatibility on build or CI agents |
|                                  | `docker info`                          | Display Docker system details      | Troubleshoot Docker daemon or resource limits     |
| **Image Build & Management**     | `docker build -t app:v1 .`             | Build image from Dockerfile        | Build application image in CI pipeline            |
|                                  | `docker images`                        | List local images                  | Verify image build before deployment              |
|                                  | `docker rmi app:v1`                    | Remove image                       | Clean up old images on build servers              |
| **Container Lifecycle**          | `docker run app:v1`                    | Run container                      | Start application locally for testing             |
|                                  | `docker run -d app:v1`                 | Run container in background        | Run microservices in detached mode                |
|                                  | `docker run -it app:v1`                | Run container interactively        | Debug app issues inside container                 |
|                                  | `docker run -p 8080:80 app:v1`         | Map ports                          | Expose app locally or in test environment         |
|                                  | `docker ps`                            | List running containers            | Check running services on host                    |
|                                  | `docker ps -a`                         | List all containers                | Identify failed or exited containers              |
|                                  | `docker stop app`                      | Stop container                     | Gracefully stop service during maintenance        |
|                                  | `docker start app`                     | Start container                    | Restart app after host reboot                     |
|                                  | `docker rm app`                        | Remove container                   | Clean unused containers in pipelines              |
| **Logs & Exec**                  | `docker logs app`                      | View logs                          | Investigate application crashes                   |
|                                  | `docker exec -it app bash`             | Exec into container                | Live troubleshooting inside container             |
| **File Operations**              | `docker cp file app:/path`             | Copy file into container           | Upload configs or scripts                         |
|                                  | `docker cp app:/path file`             | Copy file out                      | Extract logs or reports                           |
| **Networking**                   | `docker network create mynet`          | Create Docker network              | Enable container-to-container communication       |
|                                  | `docker network ls`                    | List networks                      | Validate network setup                            |
| **Volumes**                      | `docker volume create data-vol`        | Create volume                      | Persist database or app data                      |
|                                  | `docker volume ls`                     | List volumes                       | Audit storage usage                               |
| **Docker Hub / Registry**        | `docker login`                         | Authenticate to registry           | Push images from CI to Docker Hub                 |
|                                  | `docker logout`                        | Logout from registry               | Secure shared systems                             |
|                                  | `docker search nginx`                  | Search public images               | Find base images quickly                          |
| **Cleanup & Maintenance**        | `docker system prune`                  | Remove unused resources            | Free disk space on build agents                   |
|                                  | `docker system prune -a`               | Full cleanup                       | Reset Docker host                                 |
| **SBOM (Supply Chain Security)** | `docker sbom app:v1`                   | Generate SBOM                      | Meet compliance & audit requirements              |
|                                  | `docker sbom app:v1 --output sbom.txt` | Save SBOM                          | Share SBOM with security teams                    |
| **Vulnerability Scanning**       | `docker scan app:v1`                   | Scan for vulnerabilities           | Shift-left security in CI                         |
|                                  | `docker scan app:v1 --severity high`   | High severity only                 | Block critical CVEs in pipeline                   |
|                                  | `docker scan app:v1 --file Dockerfile` | Scan with Dockerfile               | Validate secure image builds                      |
