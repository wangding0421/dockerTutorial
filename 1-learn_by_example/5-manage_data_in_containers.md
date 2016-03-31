# [Manage Data in Containers](https://docs.docker.com/engine/userguide/containers/dockervolumes/) #

----------

## Data Volumes ##

Add a data volume to a container with the following command:

`$ docker run -v [SEE BELOW]`

* `[directory name]`: Create a data volume
* `[local directory]:[container directory]:([permission(ro)])`: Mount a local volume
* `[local file]:[container file name]`: Mount(Copy) a local file

## Creating and mounting a data volume container ##

Using the following command to create a data volume container, for persistent data:

`$ docker create -v [directory name] --name [volume container name] [username]/[imagename] /bin/true`

Then it can be mounted to containers like:

`$ docker run -d --volumes-from [volume container name]...`

The below 2 command for data volume removing

`$ docker remove -v`: To **REALLY** remove a data volume container
`& docker volume ls -f dangling=true`: Check for dangling volumes

The below 3 command for data volume backup and restore:

`$ docker run --rm --volumes-from [volume container name] -v [local directory for storing backup volume] [image] tar cvf /backup/backup.tar [directory name]`

`$ docker run -v [directory name] --name [new volume container name] [image] /bin/bash`

`$ docker run --rm --volumes-from [new volume container name] -v [local directory for storing backup volume] [image] bash -c "cd [new volume container name] && tar xvf /backup/backup.tar --strip 1"`

The volume container name normally is set to stay the same.
