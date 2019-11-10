### Section 4.1 - Docker Images

---

##### How to create my own image?

1. OS - Ubuntu
2. Update apt repo
3. Install dependencies using apt
4. Install Python dependencies using pip
5. Cpy source code to /opt folder
6. Run the web server using "flask" command



##### Create Image

```shell
docker build <src_directory> -t <image_name>
```

```shell
docker build . -t simple-python-web-app
```

```shell
docker run -d simple-python-web-app -p 8888:8888
```



##### Push new Image to Docker Hub

```
docker login
```

```
docker docker build <src_directory> -t <account_name>/<image_name>
```



----

