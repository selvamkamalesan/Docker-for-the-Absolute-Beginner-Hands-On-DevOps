### Section 5 - Docker Compose

---

#### Without Docker Compose

```shell
docker run -d name= redis redis
docker run -d name= db
docker run -d --name=vote -p 5000:80 --link redis:redis
docker run -d --name=result -p 5001:80 --link db:db
docker run -d --name=worker -p 5001:80 --link db:db

```

#### With Docker Compose

##### docker-compose.yml

```yml
redis: 
	image:redis
db:
	image: postgres:9.4
vote:
	#image: vote
	build: ./vote
	ports: 
		- 5000:80 
	links: 
		- redis
result:
	#image: result
	build: ./result
	ports:
		- 5001:80
	links:
		- db
worker:
	#image: worker
	build: ./worker 
	links:
		- db
		- redis
```



----

