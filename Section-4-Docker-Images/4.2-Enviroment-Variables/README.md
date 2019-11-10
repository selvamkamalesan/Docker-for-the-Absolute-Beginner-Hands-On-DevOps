### Section 4.2 - Environment Variables

---

##### Inspect Environment Variable

```
docker inspect <docker_container>
```

> Check Section Config.Env



##### Create Image

```shell
docker build . -t simple-python-web-app-color
```

```shell
docker run -d \
   --name simple-python-web-app-color \
   -e APP_COLOR=green
   --network=host \
   simple-python-web-app-color
```



----

