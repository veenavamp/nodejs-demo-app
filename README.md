# Docker Compose Nodejs and MongoDB example

## Run the System
We can easily run the whole with only a single command:
```bash
docker-compose up
```

Docker will pull the MongoDB and Node.js images (if our machine does not have it before).

The services can be run on the background with command:
```bash
docker-compose up -d
```

## Stop the System
Stopping all the running containers is also simple with a single command:
```bash
docker-compose down
```

If you need to stop and remove all containers, networks, and all images used by any service in <em>docker-compose.yml</em> file, use the command:
```bash
docker-compose down --rmi all
```

### Docker docker containers without compose

#### Build the docker image 

```
cd nodejs-app

docker build -t app .

docker network create myapp

docker container run -d --network myapp --env-file ./.env -p 7017:27017 --name mongodb mongo

docker container run -d --network myapp --env-file ./.env  -p 8081:8080 --name app app

```
