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

---
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

---

## Data persistence

### Example of how data does not persist between containers
After starting a container from and image, stopping it then restarting, data does not persist after being changed

To see this effect start an ubuntu container and generate a txt file with a random number

```sh
docker run -d ubuntu bash -c "shuf -i 1-10000 -n 1 -o /data.txt && tail -f /dev/null"
```

- The first command generates a random number and writes it
- The second command watches a file to keep the container running

To see the data you run the following command in the ubuntu shell

```sh
cat /data.txt
```

Another way using your own terminal is

```sh
docker exec <container-id> cat /data.txt
```

When starting another ubuntu container

```sh
docker run -it ubuntu ls/
```

There is no `data.txt` file shown in the list

### Persisting the data
When a container is created we can mount a volume to the container in order to persist data between containers

Create a volume using (only need to remember name, docker deals with location on disk)

```sh
docker volume create todo-db
```

After removing the container (without the persistent volume) start one while mounting the volume

```sh
docker un -dp 3000:3000 -v todo-db:/etc/todos getting-started
```

Adding new data to the application, then terminating, then starting again will have persistent data

### Bind Mounts
With bind mounts control the exact mount-point on the host

In the directory of the application run
```ps1
docker run -dp 3000:3000 `
    -w /app -v "$(pwd):/app" `
    node:12-alpine `
    sh -c "yarn install && yarn run dev"
```

---
## Multi-container apps

### Container networking
- Each container should do one thing, and one thing only
- Allows you to update and version containers in isolation
- Containers run in isolation by default
- If two containers are on the same network they can see each other, if not, they can't

Create a network

```sh
docker network create todo-app
```

Start a MySQL container and attach it to the network and define some environment variables

```ps1
docker run -d `
    --network todo-app --network-alias mysql `
    -v todo-mysql-data:/var/lib/mysql `
    -e MYSQL_ROOT_PASSWORD=secret `
    -e MYSQL_DATABASE=todos `
    mysql:5.7
```

To see if the DB is running connect to the database and verify it connects

```sh
docker exec -it <container-id> mysql -p
```

To show the DB after connecting to the sql terminal...

```sql
SHOW DATABASES;
```

### Connecting to MySQL
To find containers on network, can install 
```sh
docker run -it --network todo-app nicolaka/netshoot
```

Using the next command allows to find the IP address for the hostname `mysql` (the one set by the `--network alias flag`)

```sh
dig mysql
```

Specify all environment variables and connect container to app network

```ps1
docker run -dp 3000:3000 `
  -w /app -v "$(pwd):/app" `
  --network todo-app `
  -e MYSQL_HOST=mysql `
  -e MYSQL_USER=root `
  -e MYSQL_PASSWORD=secret `
  -e MYSQL_DB=todos `
  node:12-alpine `
  sh -c "yarn install && yarn run dev"
```
After adding some items to the list open the MySQL terminal to check the table

```sh
docker exec -it <container-id> mysql -p todos
```

In the terminal run the following command to check the table

```sql
select * from todo_items;
```
---
## Docker Compose
- Docker compose is a tool used to define and share multi-container apps
- Biggest advantage is to define all containers and parameters in a single file
- Makes it easy to start and stop multiple services


### Creating the compose file

The first part of the compose file is the schema version

```yml
version : "3.8"
```

The next part defines the services that will be used for the app.

The first part of the services is the app part

```yml
app :
    image : node:12-alpine
    command : sh -c "yarn install && yarn run dev"
    ports :
      - 3000:3000
    working_dir : /app
    volumes :
      - ./:/app
    environment:
      MYSQL_HOST : mysql
      MYSQL_USER : root
      MYSQL_PASSWORD : secret
      MYSQL_DB : todos
```

The second part is the MySQL DB part, and the volume mount

```yml
    mysql :
      image : mysql:5.7
      volumes :
        - todo-mysql-data:/var/lib/mysql
      environment :
        MYSQL_ROOT_PASSWORD : secret
        MYSQL_DATABASE : todos
```

A volume is also required in the top level section

```yml
volumes:
  todo-mysql-data :
```

Putting it all together you get

```yml
version: '3.8'

services:
  app :
    image : node:12-alpine
    command : sh -c "yarn install && yarn run dev"
    ports :
      - 3000:3000
    working_dir : /app
    volumes :
      - ./:/app
    environment:
      MYSQL_HOST : mysql
      MYSQL_USER : root
      MYSQL_PASSWORD : secret
      MYSQL_DB : todos
  mysql :
    image : mysql:5.7
    volumes :
      - todo-mysql-data:/var/lib/mysql
    environment :
      MYSQL_ROOT_PASSWORD : secret
      MYSQL_DATABASE : todos
  
volumes:
  todo-mysql-data :
```

To run the entire file, in the directory of the app run the command

```sh
docker-compose up
```

On Docker Desktop, the containers for the app are grouped together

To close the containers run

```sh
docker-compose down
# or to delete the volumes as well run
docker-compose down --volumes
```