# app
docker started.

### dockerfile

### docker build

### docker run

<img width="1379" alt="截屏2022-03-21 22 55 52" src="https://user-images.githubusercontent.com/37278360/159289620-4d9d1721-0b49-4144-97c9-c9463bcb3151.png">


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

-[] ds 

#### 