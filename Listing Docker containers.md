# [Listing Docker containers](https://docs.docker.com/reference/cli/docker/container/ls/)
1. To lists the actively running containers
```docker
docker ps
```
2. `-a` or `--all` : To list  all the containers that have completed their task, experienced an error, or been stopped by a user.
```docker
docker ps -a
```
3. To list all stopped Docker containers
```docker
docker ps -a --filter "status=exited"
``` 
4. To list all non-running containers (both exited and created)
```docker
docker ps -a --filter "status=exited" --filter "status=created"
```
5. To list the most recently created
```docker
docker ps -l
```
```docker
docker ps -n <>
```
6. To disable truncation, ensuring full container IDs, names, and command lines are displayed.
```docker
docker ps --no-trunc
```
7. `-s` or `--size` to displays the total file size of each container.
```docker
docker ps -s
```
8. [`--format`](https://docs.docker.com/engine/cli/formatting/) flag to customize the output of command. Docker supports Go templates which you can use to manipulate the output format of certain commands and log drivers.
```docker
docker ps --format "table {{.ID}}\t{{.Names}}\t{{.Status}}"
```
9. [`inspect`](https://docs.docker.com/reference/cli/docker/inspect/#examples)To list detailed information about a Docker container
```docker
docker inspect <container_id_or_name>
```
```docker
docker inspect <container_id_or_name> | jq .
```
