# Docker Cheat Sheet

### Installation
* [Docker CE]
* [Docker Machine]
* [Docker Compose]

Note: To prevent to type sudo all the time. You have to add your linux user to docker group.
* [Non-Root-User]

#### Version
Lists version of Docker
```sh
$ docker version
```

#### Info
Lists detailed information of Docker environment.
```sh
$ docker info
```

#### Help
Lists all Docker commands. Docker commands usually work like this "docker command subcommand".
```sh
$ docker --help
```

#### Container Run
This command download the nginx image and run container with given port information. First port is hosts ports you can think its your local machine port. Second port is container's port. Ex. if the port configuration was like 8888:80 you have to navigate "localhost:8888" from your browser.
```sh
$ docker container run --publish 80:80 nginx
```

--detach or -d command lets container to run in background.
```sh
$ docker container run --publish 80:80 --detach nginx
```

You can name your container by --name command.
```sh
$ docker container run --publish 80:80 --detach --name webhost nginx
```

Assign environment variables by --env or -e parameter.
```sh
$ docker container run --publish 3306:3306 --detach --name db --env MYSQL_RANDOM_ROOT_PASSWORD=yes mysql
```

#### Container List
Lists running containers.
```sh
$ docker container ls
```

Lists all containers including stopped ones.
```sh
$ docker container ls -a
```

#### Container Logs
Lists container logs by container name.
```sh
$ docker container logs webhost
```

#### Container Process
List container processes by container name.
```sh
$ docker container top webhost
```

#### Container Stats
List container performance, memory etc. stats by container name or blank*. Blank name shows every running container stats.
```sh
$ docker container stats webhost*
```

#### Container Inspect
Inspect container processes by container name.
```sh
$ docker container top webhost  
```

#### Container Stop
Stop container by container id.
```sh
$ docker container stop 3 0 b
```

#### Container Delete
Delete containers by ids. You can use first letters of container ids if they are unique. Running containers will not delete by this command.
```sh
$ docker container rm f15 cf4 b8f d7b f9f
```

Deletes containers with force. Running containers will be deleted by this command.
```sh
$ docker container rm -f f15
```





[Docker CE]: <https://docs.docker.com/install/linux/docker-ce/ubuntu/>
[Docker Machine]: <https://docs.docker.com/machine/install-machine/>
[Docker Compose]: <https://docs.docker.com/compose/install/>
[Non-Root-User]: <https://docs.docker.com/install/linux/linux-postinstall/#manage-docker-as-a-non-root-user>
