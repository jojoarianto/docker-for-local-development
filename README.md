# Docker for local development
Cheatsheet and explanation how to use docker for local development

![image](https://user-images.githubusercontent.com/5858756/72198236-2c6a7a80-345d-11ea-8708-7f460f718478.png)

[Docker for development - Run mysql, postgres, mongodb, redis with docker (Bahasa)](https://www.youtube.com/watch?v=yP4OHzpKjAU)

## Goal :
- Know how to use docker for local development purpose

## Inspired by : 
- [Hackernoon - Dont install postgres docker pull postgres](https://hackernoon.com/dont-install-postgres-docker-pull-postgres-bee20e200198).

## Todo : 
- Mysql
- Postgresql
- Mongodb
- Redis

## Docker command cheatsheet 

### Docker container
- ```docker ps```
	to see docker container (running container only)
- ```docker ps -a```
	to see docker container (running + non active)
- ```docker stop container_id```
  to stop running container
- ```docker kill container_id```
  to stop & remove running container


### Docker images
- ```docker images```
	to see list docker images

### Docker volume
- ```docker volume ls```
   to see list docker volume
- ```docker volume create volume_name```
   to create docker volume
   

## Flags explaination
-   -d : run on background
- --rm : clean up container after stop
-   -v : volume
-   -p : port forwarding
-   -e : docker environment variable

# Script
Cheatsheet
### Mysql 
mysql version 5.7
```bash
docker run --rm \
   --name local_mysql \
   -v mysql_data:/var/lib/mysql \
   -e MYSQL_ROOT_PASSWORD=secret \
   -p 3306:3306 \
   -d mysql:5.7
```

or in oneline command
```
docker run --rm --name local_mysql -v mysql_data:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=secret -p 3306:3306 -d mysql
```

to stop container run
```
docker stop local_mysql
```

connect with db url
```
mysql://root:secret@127.0.0.1
```

Official Images : https://hub.docker.com/_/mysql

### Postgresql
```
docker run --rm \
   --name local_postgres \
   -e POSTGRES_USER=root \
   -e POSTGRES_PASSWORD=secret \
   -p 5432:5432 \
   -v postgres_data:/var/lib/postgresql \
   -d postgres
```

connect with db url
```
postgresql://root:secret@127.0.0.1
```
Official images of postgresql : https://hub.docker.com/_/postgres

### Mongodb
```
docker run --rm \
   --name local_mongodb \
   -e MONGO_INITDB_ROOT_USERNAME=root \
   -e MONGO_INITDB_ROOT_PASSWORD=secret \
   -p 27017:27017 \
   -v mongodb_data:/data/db \
   -d mongo
```
Official Images of mongodb : https://hub.docker.com/_/mongo

### Redis
```
docker run --rm \
   -p 6379:6379 \
   --name local_redis \
   -d redis
```
connect with db url 
```
redis://@127.0.0.1
```
Official images of  redis : https://hub.docker.com/_/redis


