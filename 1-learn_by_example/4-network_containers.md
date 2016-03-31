# [Network Containers](https://docs.docker.com/engine/userguide/containers/networkingcontainers/) #

----------

There are default networks as well as user-defined networks. Containers run on different networks cannot communicate with each other, therefore networks are used for isolating containers.

Containers will run on the default **bridge** network unless you declare it using `--net`.

## Commands ##
* `docker network ls`: List networks
* `docker network disconnect [net name] [container name]`: To dislink a container from a network
* `docker network create [SEE BELOW] [net name]`: To create a new network
  * `-d [net name]`: Refer from the net [net name]



