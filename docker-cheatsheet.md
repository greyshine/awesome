# Docker Cheatsheet

https://www.digitalocean.com/community/tutorials/how-to-remove-docker-images-containers-and-volumes



* **Image** a template to be run as a _container_
* **Container**: a running *image*

### List Images

````docker images -a````

### Remove image

````docker rmi <imagename> ````

### List Container

````docker ps -a````

###Remove container

````docker rm <ID_or_Name> <ID_or_Name>+````

### Run container

```
docker run [OPTIONS] IMAGE[:TAG|@DIGEST] [COMMAND] [ARG...]
```

_-d_	detached
_-e_	sets environment variable
​	https://docs.docker.com/engine/reference/run/#env-environment-variables

_-p <OUTSIDE_PORT>:<INSIDE_CONTAINER>_	port mapping  

_-v <OUTSIDE_FILE>:<INSIDE_CONTAINER>_	volume mapping
​									https://docs.docker.com/engine/reference/run/#volume-shared-filesystems

### Logs of running a container

````
docker logs <container ID>
````

### Stop container

````docker stop [OPTIONS] CONTAINER [CONTAINER...]````

OPTIONS:
````--time, -t```` default 10, Seconds to wait for stop before killing it

