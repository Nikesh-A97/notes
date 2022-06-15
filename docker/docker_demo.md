 # A docker demo
This is the demo that shows up when you first install docker

## Getting started

The following command runs the container
```sh
  docker run -d -p 80:80 docker/getting-started
```

- `-d` 
  - run the container in detached mode (in the background)
- `-p 80:80` 
  - map port 80 of the host to port 80 in the container
- `docker/getting-started` 
  - is the image to use

## Getting an app
Dockerfile example for the current demo

```dockerfile
FROM node:12-alpine
# Adding build tools to make yarn install work on Apple silicon / arm64 machines
RUN apk add --no-cache python2 g++ make
WORKDIR /app
COPY . .
RUN yarn install --production
CMD ["node", "src/index.js"]
```

After downloading the app folder, it can be built by using the following command in the location of the app

```sh
docker build -t getting-started .
```

- `-t`
  - Tags the image
- `.`
  - Tells Docker to look for the Dockerfile in the current directory 

After building the container is then started by using

```sh
docker run -dp 3000:3000 getting-started
```

## Replacing Old containers
After updating app code and re-building trying to launch container again will cause an error

1. To get the ID's of currently running containers the following command can be used
    ```sh
    docker ps
    ```

2. The next command stops the container
    ```sh
    docker stop <the-container-id>
    ```

3. Finally to remove the container after stopping it run
    ```sh
    docker rm <the-container-id>
    ```

4. Can do both steps 2. and 3. using a sing command
    ```sh
    docker rm -f <the-container-id>
    ```

Alternatively if using the Docker Dashboard, then just press the bin icon
