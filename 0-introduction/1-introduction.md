# Docker Introduction and Common Facts #

----------

## Docker Commands ##

1. `docker run [SEE BELOW] [image:latest(can modify tag)] [command]`: run a docker container in a given image
   * `-i`: Make this container interactive
   * `-t`: Make a terminal with the container
   * `-d`: Make this container daemonized(detached)
   * `-P`: Tells Docker to map any required network ports inside our container to our host
2. `docker ps [SEE BELOW]`: List current running containers (mainly detached containers)
   * `-l`: Return only the infos of the _last_ container
3. `docker logs [container name]`: Get STDOUT from a given container name
4. `docker start/stop/rm [container name]`: Start/Stop/Remove a given container
5. `docker port [container name] [container port]`: Get local listening port
6. `docker top [container name]`: Check container running process
7. `docker images`: List the downloaded images
8. `docker pull [imagename]`: Download an image
9. `docker search [anything]`: Search for images

## Docker Images ##

* **Ubuntu** 
* **training/webapp**: A pre-built image that contains a simple Python Flask web application









