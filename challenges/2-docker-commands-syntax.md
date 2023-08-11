Sure, here's a list of both basic and advanced Docker commands that you might find useful:

**Basic Commands**:

1. **docker run**: Create and start a new container from an image.
   ```
   docker run [OPTIONS] IMAGE [COMMAND] [ARG...]
   ```

2. **docker ps**: List running containers.
   ```
   docker ps [OPTIONS]
   ```

3. **docker images**: List available images on the system.
   ```
   docker images [OPTIONS]
   ```

4. **docker build**: Build an image from a Dockerfile.
   ```
   docker build [OPTIONS] PATH | URL | -
   ```

5. **docker pull**: Pull an image from a registry.
   ```
   docker pull [OPTIONS] NAME[:TAG|@DIGEST]
   ```

6. **docker push**: Push an image to a registry.
   ```
   docker push [OPTIONS] NAME[:TAG]
   ```

7. **docker exec**: Run a command in a running container.
   ```
   docker exec [OPTIONS] CONTAINER COMMAND [ARG...]
   ```

8. **docker stop**: Stop a running container.
   ```
   docker stop [OPTIONS] CONTAINER [CONTAINER...]
   ```

9. **docker start**: Start a stopped container.
   ```
   docker start [OPTIONS] CONTAINER [CONTAINER...]
   ```

10. **docker rm**: Remove one or more containers.
    ```
    docker rm [OPTIONS] CONTAINER [CONTAINER...]
    ```

**Advanced Commands**:

1. **docker-compose**: Define and run multi-container applications with a YAML file.
   ```
   docker-compose [OPTIONS] [COMMAND]
   ```

2. **docker network**: Manage Docker networks.
   ```
   docker network [OPTIONS] COMMAND
   ```

3. **docker volume**: Manage Docker volumes.
   ```
   docker volume [OPTIONS] COMMAND [ARGS...]
   ```

4. **docker inspect**: Display detailed information about a container, image, or network.
   ```
   docker inspect [OPTIONS] NAME|ID [NAME|ID...]
   ```

5. **docker logs**: Fetch the logs of a container.
   ```
   docker logs [OPTIONS] CONTAINER
   ```

6. **docker commit**: Create a new image from a container's changes.
   ```
   docker commit [OPTIONS] CONTAINER [REPOSITORY[:TAG]]
   ```

7. **docker tag**: Create a tag TARGET_IMAGE that refers to SOURCE_IMAGE.
   ```
   docker tag SOURCE_IMAGE[:TAG] TARGET_IMAGE[:TAG]
   ```

8. **docker system prune**: Remove all unused containers, networks, images, and optionally, volumes.
   ```
   docker system prune [OPTIONS]
   ```

9. **docker events**: Get real-time events from the server.
   ```
   docker events [OPTIONS]
   ```

10. **docker login**: Log in to a Docker registry.
    ```
    docker login [OPTIONS] [SERVER]
    ```

These commands cover a range of Docker operations, from managing containers and images to networking, volumes, and more. The Docker documentation provides detailed information on each command and its available options.
