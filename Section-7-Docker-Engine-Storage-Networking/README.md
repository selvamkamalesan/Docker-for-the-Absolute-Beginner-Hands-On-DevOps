### Section-7-Docker-Engine-Storage-Networking

---

#### Docker Engine - Machine Resources

##### Assign CPUS

```shell
docker run --cpus=.5 <image>
```

##### Assign Memory

```shell
docker run --memory=<memory_size> <image>
```

##### Docker PID

> Show docker pid

```shell
docker exec <container_name> ps -eaf
```

> Show local pid

```shell
ps -eaf | grep <Docker_CMD>
```



#### Docker Storage

##### Volume structure

```
/var/lib/docker
└───volumes
│   └───data_volume
│       │   <docker_data_volume>
```

##### Create Volume

```shell
docker volume create <data_volume>
```

##### Run Docker with Volume

```shell
docker run -v <data_volume>:<local_directory> <image>
```

##### The new way to mount

```shell
docker run \
  --mount type=bind \
  ,source=<data_volume> \
  ,target=<local_irectory> \
  <image>
```

##### Docker info command

```shell
docker info | more
```

##### Docker history

```shell
docker history <image>
```

##### Docker System command

```shell
docker system df
```

> Show more info

```shell
docker system df -v
```



#### Docker Networking

##### Network Types

- bridge (172.17.0.1)

```shell
docker run <image>
```

- none

```shell
docker run <image> --network=none
```

- host

```shell
docker run <image> --network=host
```

##### User defined networks

```shell
docker network create \
  --driver bridge \
  --subnet <x.x.x.x\xx> \
  <network-name>
```



----

