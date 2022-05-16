# app
docker started.

### dockerfile

refer:[Run a Simple .jar Application in a Docker Container](https://dzone.com/articles/run-simple-jar-application-in-docker-container-1)
#### as simple .jar app dockerfile
```
FROM openjdk:8-jre-alpine3.9

WORKDIR /app

COPY rabbitmq.jar /app/rabbitmq.jar
COPY config /app/config

CMD ["java","-jar","/app/rabbitmq.jar"]
```

### docker build

#### as simple .jar app docker build

```
docker build -t helloworld
docker images
docker tag 4b795844c7ab /hello-world
docker push /hello-world:latest

```



### docker run
<img width="1379" alt="截屏2022-03-21 22 55 52" src="https://user-images.githubusercontent.com/37278360/159289620-4d9d1721-0b49-4144-97c9-c9463bcb3151.png">

#### as simple .jar app docker run
```
docker run /hello-world
```


#### Container Volumes

#####  named volumes
create a volume by `docker volume create` command.

docker choose.

##### Bind Mounts
you control.

`docker run -dp 3000:3000 \
    -w /app -v "$(pwd):/app" \
    node:12-alpine \
    sh -c "apk add --no-cache python2 g++ make && yarn install && yarn run dev"
`

- -dp 3000:3000 - same as before. Run in detached (background) mode and create a port mapping
- -w /app - sets the container's present working directory where the command will run from
- -v "$(pwd):/app" - bind mount (link) the host's present working directory to the container's /app directory
- node:12-alpine - the image to use. Note that this is the base image for our app from the Dockerfile
- sh -c "yarn install && yarn run dev" - the command. We're starting a shell using sh (alpine doesn't have bash) and running yarn install to install all dependencies and then running yarn run dev. If we look in the package.json, we'll see that the dev script is starting nodemon.

<img width="674" alt="image" src="https://user-images.githubusercontent.com/37278360/161106695-5617e478-51c6-41fd-b837-3f4fbbc7241a.png">

#### 



### docker command
```
# see docker container
docker ps 
docker ps -a

# see container logs
docker logs container-id
docker logs -t -f --tail=number container-id
# -t show timestamp
# -f fellow recent logs
# --tail show recent number line logs

```

### docker compose 
create `docker-compose.yml` file,Run the application
```
# up yml,start,see logs
docker-compose up -d
docker-compose logs -f 
docker-compose logs -f app

# tear all down
docker-compose down
```
