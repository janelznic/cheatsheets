# Docker cheatsheet


&laquo; [Back to index](https://github.com/janelznic/cheatsheets)

## Table of Contents
- [Docker cheatsheet](#docker-cheatsheet)
  - [Table of Contents](#table-of-contents)
    - [Basic commands](#basic-commands)
    - [Images](#images)
    - [Containers](#containers)
    - [Docker Compose](#docker-compose)
    - [Docker Hub](#docker-hub)
    - [Other](#other)


### Basic commands
* Start docker daemon ```docker -d```
* Display overview with statistics ```docker info```

### Images
* List local images ```docker images```
* Build image from a Dockerfile ```docker build -t frontend```
* Build image from a Dockerfile without cache ```docker build -t frontend . -no-cache```
* Build image from a Dockerfile with environment variables ```docker build -t frontend --build-arg ENV=production```
* Delete image ```docker rmi aaddfa5e87a9```
* Remove all unused images ```docker image prune```

### Containers
Configuration is usually saved in ```Dockerfile``` file in root directory of the project or component.

* List containers (running and stopped) ```docker ps -a```
* Kill container by ID ```docker kill $ID```
* View resource usage stats ```docker container stats```
* Create and run container from the image: ```docker run --name <container_name> <image_name>```
* Run container with publish port to the host ```docker run -p <host_port>:<container_port> <image_name>```
* Run container with specific Linux version and bash shell ```docker run -it debian:buster /bin/bash```
* Run container in the background ```docker run -d <image_name>```
* Create a container from an image

  ```bash
  docker create [options] IMAGE
    -a, --attach               # attach stdout/err
    -i, --interactive          # attach stdin (interactive)
    -t, --tty                  # pseudo-tty
        --name NAME            # name your image
    -p, --publish 5000:5000    # port map (host:container)
        --expose 5432          # expose a port to linked containers
    -P, --publish-all          # publish all ports
        --link container:alias # linking
    -v, --volume `pwd`:/app    # mount (absolute paths needed)
    -e, --env NAME=hello       # env vars
  ```
* Create container from image ```docker create --name app_redis_1 --expose 6379 redis:3.0.2```
* Start or stop container ```docker start|stop <container_name|container_id>```
* Remove container ```docker rm <container_name>```
* Open bash shell inside the running container ```docker exec -it <container_name> sh```
* Fetch and follow the logs ```docker logs -f <container_name|container_id>```
* Inspect running container ```docker inspect <container_name|container_id>```

### Docker Compose
Configuration is usually saved in ```docker-compose.yml``` file in top-root directory of the project.

* Build containers ```docker-compose build```
* List containers ```docker-compose ps```
* Run containers ```docker-compose up```
* Stop containers ```docker-compose down```
* Pause containers ```docker-compose pause```
* Play containers ```docker-compose unpause```

### Docker Hub
* Login into Docker Hub ```docker login```
* Publish image to Docker Hub ```docker push <username>/<image_name>```
* Search for image ```docker search <image_name>```
* Pull an image from Docker Hub ```docker pull <image_name>```

### Other
* Docker configuration including credenatials is saved in ```/~/.docker/config.json```.

