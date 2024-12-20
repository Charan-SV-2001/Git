# Docker Cheat Sheet

## Installation
- Install Docker Engine ([Linux](https://docs.docker.com/engine/install/)) or Docker Desktop ([Linux, macOS, and Windows](https://docs.docker.com/desktop/)).

## Container commands
| Command                                      | Description                                  |
|----------------------------------------------|----------------------------------------------|
| `docker run <image>`                         | Create and run a new container               |
| `docker run -p 8080:80 <image>`              | Publish container port 80 to host port 8080  |
| `docker run -d <image>`                      | Run a container in the background            |
| `docker run -v <host>:<container> <image>`    | Mount a host directory to a container        |
| `docker ps`                                  | List currently running containers            |
| `docker ps --all`                            | List all containers (running or stopped)     |
| `docker logs <container_name>`               | Fetch the logs of a container                |
| `docker logs -f <container_name>`            | Fetch and follow the logs of a container     |
| `docker stop <container_name>`               | Stop a running container                     |
| `docker start <container_name>`              | Start a stopped container                    |
| `docker rm <container_name>`                 | Remove a container                           |

## Executing commands in a container
| Command                                      | Description                                  |
|----------------------------------------------|----------------------------------------------|
| `docker exec <container_name> <command>`     | Execute a command in a running container     |
| `docker exec -it <container_name> bash`      | Open a shell in a running container          |

## Image commands
| Command                                      | Description                                  |
|----------------------------------------------|----------------------------------------------|
| `docker build -t <image> .`                  | Build a new image from the Dockerfile in the current directory and tag it |
| `docker images`                              | List local images                            |
| `docker rmi <image>`                         | Remove an image                              |

## Container registry commands
| Command                                      | Description                                  |
|----------------------------------------------|----------------------------------------------|
| `docker login`                               | Login to Docker Hub                          |
| `docker login <server>`                      | Login to another container registry          |
| `docker logout`                              | Logout of Docker Hub                         |
| `docker logout <server>`                     | Logout of another container registry         |
| `docker push <image>`                        | Upload an image to a registry                |
| `docker pull <image>`                        | Download an image from a registry            |
| `docker search <image>`                      | Search Docker Hub for images                 |

## System commands
| Command                                      | Description                                  |
|----------------------------------------------|----------------------------------------------|
| `docker system df`                           | Show Docker disk usage                       |
| `docker system prune`                        | Remove unused data                           |
| `docker system prune -a`                     | Remove all unused data                       |

## Docker Compose
| Command                                      | Description                                  |
|----------------------------------------------|----------------------------------------------|
| `docker compose up`                          | Create and start containers                  |
| `docker compose up -d`                       | Create and start containers in background    |
| `docker compose up --build`                  | Rebuild images before starting containers    |
| `docker compose stop`                        | Stop services                                |
| `docker compose down`                        | Stop and remove containers and networks      |
| `docker compose ps`                          | List running containers                      |
| `docker compose logs`                        | View the logs of all containers              |
| `docker compose logs <service>`              | View the logs of a specific service          |
| `docker compose logs -f`                     | View and follow the logs                     |
| `docker compose pull`                        | Pull the latest images                       |
| `docker compose build`                       | Build or rebuild services                    |
| `docker compose build --pull`                | Pull latest images before building           |

## Dockerfile instructions
| Instruction                                  | Description                                  |
|----------------------------------------------|----------------------------------------------|
| `FROM <image>`                               | Set the base image                           |
| `FROM <image> AS <name>`                     | Set the base image and name the build stage  |
| `RUN <command>`                              | Execute a command as part of the build process |
| `RUN ["exec", "param1", "param2"]`           | Execute a command as part of the build process |
| `CMD ["exec", "param1", "param2"]`           | Execute a command when the container starts |
| `ENTRYPOINT ["exec", "param1"]`              | Configure the container to run as an executable |
| `ENV <key>=<value>`                          | Set an environment variable                  |
| `EXPOSE <port>`                              | Expose a port                                |
| `COPY <src> <dest>`                          | Copy files from source to destination        |
| `COPY --from=<name> <src> <dest>`            | Copy files from a build stage to destination |
| `WORKDIR <path>`                             | Set the working directory                    |
| `VOLUME <path>`                              | Create a mount point                         |
| `USER <user>`                                | Set the user                                 |
| `ARG <name>`                                 | Define a build argument                      |
| `ARG <name>=<default>`                       | Define a build argument with a default value |
| `LABEL <key>=<value>`                        | Set a metadata label                         |
| `HEALTHCHECK <command>`                      | Set a healthcheck command                    |

## Example compose.yaml
```yaml
services:
  service1:
    image: <image>
    build: .
    volumes:
      - .:/code:ro
    ports:
      - "8000:80"
    environment:
      KEY: value
