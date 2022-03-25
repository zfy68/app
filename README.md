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