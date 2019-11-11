### Section-9-Docker-Orchestration

---

##### Docker Orchestration - Simple Command

```shell
docker service create --replicas=<replicas_number> <image>
```

##### Docker Swarm

```
docker swarm init --advertise-addr <x.x.x.x>
```

> then copy the command to add a worker to this swarm

```shell
docker swarm join --token <TOKEN>
```



#### Kubernetes

##### Simple Run

```shell
kubectl run <container>
```

##### Run with replicas

```shell
kubectl run --replicas=<replicas_number> <container>
```

##### Information

```shell
kubectl cluester-info
```



----

