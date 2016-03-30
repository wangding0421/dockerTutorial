# [Build Your Own Images](https://docs.docker.com/engine/userguide/containers/dockerimages/) #

----------

There are pre-built images, as well as user-defined images. Pre-built images are downloaded from the **Docker Hub** to the local Docker host.

You can manage images, including:

* Managing and working with images locally on your Docker host
* Creating basic images
* Uploading images to Docker Hub Registry

## Creating Our Own Images ##

### Updating and Commiting an Image ###

The below command could let you to first get a suitable available image, then do your own improvment on it, then commit and make it your own image.

```shell
$ docker commit -m "[comment]" -a "[Author]" [origin container ID] [username]/[imagename]:[tag]
```

### Building an Image from a _Dockerfile_ ###

* Create a `Dockerfile`.
* Add commands into it (See [instructions](https://docs.docker.com/engine/userguide/eng-image/dockerfile_best-practices/), Below is a sample `Dockerfile`:

```shell
# This is a comment
FROM ubuntu:14.04
MAINTAINER Kate Smith <ksmith@example.com>
RUN apt-get update && apt-get install -y ruby ruby-dev
RUN gem install sinatra
```
     
* Run the below command to build the image:
```shell
$ docker build -t [username]/[imagename]:[tag] [Dockfile directory]
```

