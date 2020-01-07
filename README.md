# Docker for local development
Cheatsheet and explanation how to use docker for local development

## Goal :
- Know how to use docker for local development purpose

## Inspired by : 
- [Hackernoon - Dont install postgres docker pull postgres](https://hackernoon.com/dont-install-postgres-docker-pull-postgres-bee20e200198).


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
```bash
docker run --rm \
   --name local_mysql \
   -v mysql_data:/var/lib/mysql \
   -e MYSQL_ROOT_PASSWORD=secret \
   -p 3306:3306 \
   -d mysql
```
or in oneline command
```
docker run --rm --name local_mysql -v mysql_data:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=user123 -p 3306:3306 -d mysql
```
to stop container run
```
docker stop local_mysql
```

Official Images : https://hub.docker.com/_/mysql

### Postgresql
```
docker run --rm \
   --name local_postgres \
   -e POSTGRES_PASSWORD=secret \
   -v postgres_data:/var/lib/postgresql/data \
   -p 5432:5432 \
   -d postgres
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
docker run --rm -p 6379:6379 --name local_redis -d redis
```
Official images of  redis : https://hub.docker.com/_/redis


