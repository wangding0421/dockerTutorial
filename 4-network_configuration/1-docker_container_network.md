# [Docker Container Network](https://docs.docker.com/engine/userguide/networking/dockernetworks/) #

----------

When you install Docker, it creates three networks automatically. You can list these networks using the `docker network ls` command.

There is mainly nothing to do with these three default networks except the **bridge** network.

More important fact is that you can create your own network.

## The Default Bridge Network ##
 
Use `docker network inspect bridge` to check the status of the **bridge** network.

Containers in the same network are able to communicate with each other using IP addresses. Therefore you can:

1. Attach to a running container in the network
2. check its status (`ifconfig`) (optional)
3. ping to another container in the same network with its IP address

## User Defined Networks ##

The above techniques are cumbersome to set up and prone to error. While they are still available to you as techniques, it is better to avoid them and define your own bridge networks instead.

You can create multiple networks. You can add containers to more than one network. Containers can only communicate within networks but not across networks. A container attached to two networks can communicate with member containers in either network.

You can create either a **bridge** network or a **overlay** network:

### Bridge Network ###

A bridge network is useful in cases where you want to run a relatively small network on a single host.

You can use the below command to create your own bridge network:

`$ docker network create --driver bridge [net name]`

After you create the network, you can launch containers on it using the `docker run --net=<NETWORK>` option.

Each container in the network can immediately communicate with other containers in the network. Though, the network itself isolates the containers from external networks.

![bridge net](https://docs.docker.com/engine/userguide/networking/images/bridge_network.png) 

You can expose and publish container ports on containers in this network. This is useful if you want to make a portion of the bridge network available to an outside network.

![bridge publish](https://docs.docker.com/engine/userguide/networking/images/network_access.png) 

### Overlay Network ###

It is used for multi host environment.

















