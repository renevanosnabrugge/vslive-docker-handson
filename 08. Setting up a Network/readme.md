# Hands-on labs Introduction to Docker

## Exercise 08: Setting up networks 
When you run multiple containers, they sometimes need to listen to each other. For that we can create networks in Docker. There are multiple types of networks available
 * Bridge - Network isolation. Containers get their own IP
 * Host - Containers share the IP address of the host
 * Overlay - Networks are shared over hosts
 * None - No network facilities
 [More information](https://docs.docker.com/network/) 


## Start a new container in the default network
* Make sure you run Linux containers (check the whale icon) 
* Run the busybox container in interactive mode

```
docker run -ti busybox
```

* Check the ipaddress `ifconfig`
* Ping www.google.com `ping www.google.com`
* Exit the container but not stop it ! (CTRL-P, CTRL-Q)

* Inspect the container and check the IP Address
```
docker inspect <containerid>
```
* Start a new busybox container
* Can they access each other by using ping <ipaddress>

## Setting up your own networks
* Create 2 own networks
```
docker network create -d bridge vslivetest1
docker network create -d bridge vslivetest2
```
* Start 2 new busybox containers. Attach them to different networks
```
docker run -ti --network vslivetest1 busybox
docker run -ti --network vslivetest2 busybox
``` 
* Can they access each other?

## Cleaning up
* Stop and remove all running containers
```
docker stop <containerid>
docker rm <containerid>
```
* Stop and remove all networks 
```
docker network rm <networkname>
```