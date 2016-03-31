# Docker Introduction and Common Facts #

----------

## Docker Commands ##

### General ###
* `docker inspect`: Inspect status

### Container ###
* `docker run [SEE BELOW] [image:latest(can modify tag)] [command]`: run a docker container in a given image
  * `-i`: Make this container interactive
  * `-t`: Make a terminal with the container
  * `-d`: Make this container daemonized(detached)
  * `-P`: Tells Docker to map any required network ports inside our container to our host
  * `--name [name]`: Give a name to the container
  * `--net [net_name]`: Link container to network
  * `-v [SEE BELOW]`: Mount a data volume to a container
      * `[volume name]`: Create a data volume
      * `[local volume]:[container volume]:([permission(ro)])`: Mount a local volume
      * `[local file]:[container file name]`: Mount(Copy) a local file
* `docker ps [SEE BELOW]`: List current running containers (mainly detached containers)
  * `-l`: Return only the infos of the _last_ container
* `docker logs [container name]`: Get STDOUT from a given container name
* `docker start/stop/rm [container name]`: Start/Stop/Remove a given container
* `docker port [container name] [container port]`: Get local listening port
* `docker top [container name]`: Check container running process
* `docker attach [OPTIONS] CONTAINER`: Attach to a running container

### Images ###
* `docker images`: List the downloaded images
* `docker pull [imagename]`: Download an image
* `docker search [anything]`: Search for images
* `docker tag [imageID] [username]/[imagename]:[newtag]`: Give tag to a image
* `docker push [username]/[imagename]`: Push image to Hub
* `docker rmi [username]/[imagename]`: Remove a local image

### Networks ###
* `docker network ls`: List networks
* `docker network disconnect [net name] [container name]`: To dislink a container from a network
* `docker network create [SEE BELOW] [net name]`: To create a new network
  * `-d [origin net name]`: Refer from the net [origin net name] (bridge/overlay)

### Data Volumes Containers ###
* `docker create -v [directory name] --name [volume container name] [username]/[imagename] /bin/true`: Create a dat volume container
* `docker remove -v`: To **REALLY** remove a data volume container

## Docker Images ##

* **Ubuntu** 
* **training/webapp**: A pre-built image that contains a simple Python Flask web application









