### Section 5 - Demo - Example Voting Application

---

Demo based on [dockersamples-github](https://github.com/dockersamples/example-voting-app)

##### Clone project.

```shell
git clone https://github.com/dockersamples/example-voting-app.git
```



##### [Install Docker Compose](https://docs.docker.com/compose/install/)

```shell
sudo curl -L "https://github.com/docker/compose/releases/download/1.24.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

sudo chmod +x /usr/local/bin/docker-compose

sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose

docker-compose --version
```

##### 

##### docker-compose.yml

```yml

version: "3"

services:
  vote:
    build: ./vote
    command: python app.py
    volumes:
     - ./vote:/app
    ports:
      - "5000:80"
    networks:
      - front-tier
      - back-tier

  result:
    build: ./result
    command: nodemon server.js
    volumes:
      - ./result:/app
    ports:
      - "5001:80"
      - "5858:5858"
    networks:
      - front-tier
      - back-tier

  worker:
    build:
      context: ./worker
    depends_on:
      - "redis"
      - "db"
    networks:
      - back-tier

  redis:
    image: redis:alpine
    container_name: redis
    ports: ["6379"]
    networks:
      - back-tier

  db:
    image: postgres:9.4
    container_name: db
    volumes:
      - "db-data:/var/lib/postgresql/data"
    networks:
      - back-tier

volumes:
  db-data:

networks:
  front-tier:
  back-tier:
```



##### Run Docker Compose

```shell
docker-compose up
```



##### Delete Images and Containers to free space in your PC

```shell
docker stop \
  example-voting-app_worker_1 \
  example-voting-app_result_1 \
  example-voting-app_vote_1 \
  db \
  redis
&
docker rm \
  example-voting-app_worker_1 \
  example-voting-app_result_1 \
  example-voting-app_vote_1 \
  db \
  redis
&
docker rmi \
  example-voting-app_worker \
  example-voting-app_result \
  example-voting-app_vote \
  postgres:9.4 \
  redis:alpine \
  microsoft/dotnet:2.0.0-sdk \
  node:10-slim
```



----

