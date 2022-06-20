# Demo Project
This demo will have a js and nodejs application & a mongoDB docker container attached

## Step 1
- Have a nodejs app with express backend

## Step 2
- Pull both mongo and mongo-express containers from docker

  ```sh
  docker pull mongo
  #
  docker pull mongo-express
  ```

## Step 3
- Create a network for both containers

  ```sh
  docker network create mongo-network
  ```

## Step 4
- Configure the parameters for the images

  ```ps1
  docker run -d `                                    
  -p 27017:27017 `                                                 
  -e MONGO_INITDB_ROOT_USERNAME=admin `       
  -e MONGO_INITDB_ROOT_PASSWORD=password `
  --name mongodb `
  --network mongo-network `
  mongo    
  ```

  ```ps1
  docker run -d `
  -p 8081:8081 `
  -e ME_CONFIG_MONGODB_ADMINUSERNAME=admin `
  -e ME_CONFIG_MONGODB_ADMINPASSWORD=password `
  -e ME_CONFIG_MONGODB_SERVER=mongodb `
  --network mongo-network `
  --name mongo-express `
  mongo-express
  ```
   
- Note that you would not directly set environment variables like this, they would be in separate location

## Step 5
- After checking logs for a successful connection
- Can connect to the mongodb DB in localhost
- Can connect to the mongodb DB in nodejs app (with relevant code)

## Step 6
- Tedious to run docker commands in CLI
- Use Docker Compose 

## Step 7 
- Mongo Compose .yaml setup

```yaml
version: '3'
services:
  mongodb :
    image: mongo
    ports:
      - 27017:27017
    environment:
      - MONGODB_...
  mongo-express:
    image: mongo-express
    ports:
      - 8080:8080
    environment:
      -ME_CONFIG...
```
