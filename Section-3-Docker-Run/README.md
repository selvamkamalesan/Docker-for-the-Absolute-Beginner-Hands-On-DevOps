### Section 3 - Docker Run

---

##### run - tag

```shell
docker run <image:TAG>
```

##### run - stdin (provide input)

```shell
docker run -i <image_name>
```

##### run - stdin (interactive)

```shell
docker run -it <image_name>
```

##### run - port mapping

```shell
docker run -p <local_port>:<docker_host_port> <image_name>
```

##### run - volume mapping

```shell
docker run -v <local_dir>:<docker_dir> <docker_image>
```

##### Inspect container

```shell
docker inspect <container_name>
```

##### Container Logs

```shell
docker logs <container_name>
```



----

