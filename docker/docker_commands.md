# Docker Examples

## Pulling images and viewing docker containers

- To obtain docker **images** run
 
  ```sh
  docker pull <container-name>
  ```

- To **view all** docker **images** run
  
  ```sh
  docker images
  ```
  - Example output
    
    ```sh
    REPOSITORY               TAG         IMAGE ID       CREATED        SIZE
    redis                    latest      604d80444252   3 days ago     117MB
    ubuntu                   latest      27941809078c   10 days ago    77.8MB
    mysql                    5.7         2a0961b7de03   2 weeks ago    462MB
    ```   
  - REPOSITORY : name of the image
  - TAG : The version of the image
  - IMAGE ID: The ID attached to the image that can be referenced to
  - CREATED: When the image itself was created (not pulled)
  - SIZE: Self Explanatory

- To **run** a docker **image** run

  ```sh
  docker run <image-name>
  ```

- To **run** a docker **image** in a **detached** state

  ```sh
  docker run -d <image-name> 
  ```

- **List all** running **containers** run
  
  ```sh
  docker ps
  
  # To view stopped containers
  docker ps -a
  ```

- **Stop** a container from running
  
  ```sh
  docker stop <container-id>
  ```

- **Start** a container that has been stopped (remembers the configs for the container)
  
  ```sh
  dockers start <container-id>
  ```

- **Remove** a container after stopping it

  ```sh
  docker rm <container-id>
  
  # Can also stop and remove in one line
  docker rm -f <container-id>
  ```

- **Binding** a **port** to a container when running

  ```sh
  docker run -p<host-port>:<container-port>
  ```

- **Assign** a **name** to container

  ```sh
  docker run --name <name> <image-name>
  ```

- Show **logs** for a container

  ```sh
  docker logs <container-name>
  ```

- Go into the **terminal** for the container
- `-it` : Interactive Terminal

  ```sh
  docker exec -it <container-id>
  ```