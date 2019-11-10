### Section 4.1 - Docker Images

---

##### How to create my own image?

1. OS - Ubuntu
2. Update apt repo
3. Install dependencies using apt
4. Install Python dependencies using pip
5. Copy source code to /opt folder
6. Run the web server using "flask" command



##### Create Image Command

```shell
docker build <src_directory> -t <image_name>
```



##### Create Image

```shell
docker build . -t simple-python-web-app
```

```shell
docker run -d \
   --name simplePythonWebApp \
   --network=host \
   simple-python-web-app
```



##### Push new Image to Docker Hub

```
docker login
```

```
docker docker build <src_directory> -t <account_name>/<image_name>
```



----

