# Docker Installation on all OS

[Web Emulator For Practice](https://labs.play-with-docker.com)

--------------------------------------------------------------------------------------------------------

[Docker Installation](https://docs.docker.com/get-docker/)

--------------------------------------------------------------------------------------------------------

# Docker Installation on Ubuntu Machine:

$ uname -a				# Linux kernel version is 4.2.0-27 which is higher than version 3.8, so we are good to go.
$ sudo apt-get update		# This command will connect to the internet and download the latest system packages for Ubuntu.

[Install Docker On Ubuntu 16.04](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-16-04)

[Install Docker On Windows](https://docs.docker.com/docker-for-windows/): Toolbox is necessary

[Install Docker ToolBox For Mac & Windows](https://www.docker.com/products/docker-desktop)

# Play with Docker: Create an AWS Machine 16.04

[Install Docker on AWS Machine](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-16-04)


--------------------------------------------------------------------------------------------------------


# DOCKER ARCHITECTURE DIAGRAM

<img width="508" alt="docker-architecture" src="https://github.com/xavyaly/docker-lab/assets/19641964/6746861e-385f-4071-86e5-3005c64d0d2e">


--------------------------------------------------------------------------------------------------------


# DOCKER ARCHITECTURE COMPONENTS 

Docker's architecture involves several components that work together to enable the creation, distribution, and execution of containerized applications. The key components of Docker's architecture are:

#  Docker Engine:

   Docker Engine is the core component responsible for running containers. It consists of two main parts:
   
   -  # Docker Daemon (dockerd) : 
   This is a background service that manages Docker containers, images, networks, and storage volumes. It listens for Docker API requests and performs actions such as building and running containers.
   
   -  # Docker CLI (docker) : 
   The Docker Command-Line Interface is used to interact with the Docker daemon. It provides users with a command-line interface to manage containers, images, networks, and more.

#  Container :

   A container is a lightweight, standalone executable software package that includes everything needed to run a piece of software, including the code, runtime, system libraries, and settings. Containers are isolated from the host and other containers, making them portable and consistent across different environments.

#  Image :

   An image is a read-only template used to create containers. It contains a set of filesystem layers, application code, runtime libraries, and settings. Images are built from Dockerfiles and can be versioned and shared via Docker registries. Images are the foundation of containers and provide a consistent environment for running applications.

#  Dockerfile :

   A Dockerfile is a plain text configuration file that defines the steps to create a Docker image. It includes instructions to install dependencies, copy files, set environment variables, and more. Dockerfiles are used to automate the image creation process and ensure reproducibility.

#  Registry :

   A Docker registry is a central repository that stores Docker images. The most well-known registry is Docker Hub. Registries allow users to push and pull images, making it easy to share and distribute images among developers and across different environments.

#  Container Orchestration :

   While not a core part of Docker's architecture, container orchestration platforms like Kubernetes and Docker Swarm help manage the deployment, scaling, and management of containerized applications across clusters of machines.

<!-- Docker's architecture allows developers to create, package, and deploy applications as containers, ensuring consistency across development, testing, and production environments. The use of images and containers simplifies application deployment, reduces environment inconsistencies, and increases scalability and portability. -->


--------------------------------------------------------------------------------------------------------


# DOCKER COMMANDS GENERIC SYNTAX

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


--------------------------------------------------------------------------------------------------------


# DOCKER COMMANDS ACTUAL EXECUTION

$ docker --version
Docker version 23.0.5, build bc4487a

---------------------------------------------------------------------------------------------

$ docker version
Client:
 Cloud integration: v1.0.31
 Version:           23.0.5
 API version:       1.42
 Go version:        go1.19.8
 Git commit:        bc4487a
 Built:             Wed Apr 26 16:12:52 2023
 OS/Arch:           darwin/arm64
 Context:           default

Server: Docker Desktop 4.19.0 (106363)
 Engine:
  Version:          23.0.5
  API version:      1.42 (minimum version 1.12)
  Go version:       go1.19.8
  Git commit:       94d3ad6
  Built:            Wed Apr 26 16:17:14 2023
  OS/Arch:          linux/arm64
  Experimental:     false
 containerd:
  Version:          1.6.20
  GitCommit:        2806fc1057397dbaeefbea0e4e17bddfbd388f38
 runc:
  Version:          1.1.5
  GitCommit:        v1.1.5-0-gf19387a
 docker-init:
  Version:          0.19.0
  GitCommit:        de40ad0

---------------------------------------------------------------------------------------------

$ docker info
Client:
 Context:    default
 Debug Mode: false
 Plugins:
  buildx: Docker Buildx (Docker Inc.)
    Version:  v0.10.4
    Path:     /Users/javedalam/.docker/cli-plugins/docker-buildx
  compose: Docker Compose (Docker Inc.)
    Version:  v2.17.3
    Path:     /Users/javedalam/.docker/cli-plugins/docker-compose
  dev: Docker Dev Environments (Docker Inc.)
    Version:  v0.1.0
    Path:     /Users/javedalam/.docker/cli-plugins/docker-dev
  extension: Manages Docker extensions (Docker Inc.)
    Version:  v0.2.19
    Path:     /Users/javedalam/.docker/cli-plugins/docker-extension
  init: Creates Docker-related starter files for your project (Docker Inc.)
    Version:  v0.1.0-beta.4
    Path:     /Users/javedalam/.docker/cli-plugins/docker-init
  sbom: View the packaged-based Software Bill Of Materials (SBOM) for an image (Anchore Inc.)
    Version:  0.6.0
    Path:     /Users/javedalam/.docker/cli-plugins/docker-sbom
  scan: Docker Scan (Docker Inc.)
    Version:  v0.26.0
    Path:     /Users/javedalam/.docker/cli-plugins/docker-scan
  scout: Command line tool for Docker Scout (Docker Inc.)
    Version:  v0.10.0
    Path:     /Users/javedalam/.docker/cli-plugins/docker-scout

Server:
 Containers: 1
  Running: 1
  Paused: 0
  Stopped: 0
 Images: 3
 Server Version: 23.0.5
 Storage Driver: overlay2
  Backing Filesystem: extfs
  Supports d_type: true
  Using metacopy: false
  Native Overlay Diff: true
  userxattr: false
 Logging Driver: json-file
 Cgroup Driver: cgroupfs
 Cgroup Version: 2
 Plugins:
  Volume: local
  Network: bridge host ipvlan macvlan null overlay
  Log: awslogs fluentd gcplogs gelf journald json-file local logentries splunk syslog
 Swarm: inactive
 Runtimes: io.containerd.runc.v2 runc
 Default Runtime: runc
 Init Binary: docker-init
 containerd version: 2806fc1057397dbaeefbea0e4e17bddfbd388f38
 runc version: v1.1.5-0-gf19387a
 init version: de40ad0
 Security Options:
  seccomp
   Profile: builtin
  cgroupns
 Kernel Version: 5.15.49-linuxkit
 Operating System: Docker Desktop
 OSType: linux
 Architecture: aarch64
 CPUs: 4
 Total Memory: 3.841GiB
 Name: docker-desktop
 ID: 81681c6a-7a9f-4342-952a-885477f642f1
 Docker Root Dir: /var/lib/docker
 Debug Mode: false
 HTTP Proxy: http.docker.internal:3128
 HTTPS Proxy: http.docker.internal:3128
 No Proxy: hubproxy.docker.internal
 Registry: https://index.docker.io/v1/
 Experimental: false
 Insecure Registries:
  hubproxy.docker.internal:5555
  127.0.0.0/8
 Live Restore Enabled: false

---------------------------------------------------------------------------------------------

# PULL A DOCKER IMAGE FROM DOCKER HUB WITHOUT SIGNUP AND REMOVE THE IAMGE:

# PLAY IN LOCAL 

$ docker images
REPOSITORY   TAG       IMAGE ID   CREATED   SIZE

$ docker pull ubuntu
Using default tag: latest
latest: Pulling from library/ubuntu
5af00eab9784: Pull complete 
Digest: sha256:0bced47fffa3361afa981854fcabcd4577cd43cebbb808cea2b1f33a3dd7f508
Status: Downloaded newer image for ubuntu:latest
docker.io/library/ubuntu:latest

$ docker images 
REPOSITORY   TAG       IMAGE ID       CREATED       SIZE
ubuntu       latest    37f74891464b   6 weeks ago   69.2MB

$ docker rmi ubuntu
Untagged: ubuntu:latest
Untagged: ubuntu@sha256:0bced47fffa3361afa981854fcabcd4577cd43cebbb808cea2b1f33a3dd7f508
Deleted: sha256:37f74891464b2067aacbde60d9e2888e002af047a0d5dfc0b06b701928e0b473
Deleted: sha256:c5ca84f245d30117a9a2720cb4297cedf3642816471d4d699f4d77e39e13a39c

$ docker images 
REPOSITORY   TAG       IMAGE ID   CREATED   SIZE

$ docker pull ubuntu
Using default tag: latest
latest: Pulling from library/ubuntu
5af00eab9784: Pull complete 
Digest: sha256:0bced47fffa3361afa981854fcabcd4577cd43cebbb808cea2b1f33a3dd7f508
Status: Downloaded newer image for ubuntu:latest
docker.io/library/ubuntu:latest
 
$ docker images
REPOSITORY   TAG       IMAGE ID       CREATED       SIZE
ubuntu       latest    37f74891464b   6 weeks ago   69.2MB
 
$ docker rmi 37f7
Untagged: ubuntu:latest
Untagged: ubuntu@sha256:0bced47fffa3361afa981854fcabcd4577cd43cebbb808cea2b1f33a3dd7f508
Deleted: sha256:37f74891464b2067aacbde60d9e2888e002af047a0d5dfc0b06b701928e0b473
Deleted: sha256:c5ca84f245d30117a9a2720cb4297cedf3642816471d4d699f4d77e39e13a39c

$ docker inspect 37f
[
    {
        "Id": "sha256:37f74891464b2067aacbde60d9e2888e002af047a0d5dfc0b06b701928e0b473",
        "RepoTags": [
            "ubuntu:latest"
        ],
        "RepoDigests": [
            "ubuntu@sha256:0bced47fffa3361afa981854fcabcd4577cd43cebbb808cea2b1f33a3dd7f508"
        ],
        "Parent": "",
        "Comment": "",
        "Created": "2023-06-28T08:42:50.42500211Z",
        "Container": "04787ad63e8502484d39ddc351b44ab742a510855a342b0915491bf3f4cf703d",
        "ContainerConfig": {
            "Hostname": "04787ad63e85",
            "Domainname": "",
            "User": "",
            "AttachStdin": false,
            "AttachStdout": false,
            "AttachStderr": false,
            "Tty": false,
            "OpenStdin": false,
            "StdinOnce": false,
            "Env": [
                "PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"
            ],
            "Cmd": [
                "/bin/sh",
                "-c",
                "#(nop) ",
                "CMD [\"/bin/bash\"]"
            ],
            "Image": "sha256:62d2c268ed32cbee7f6f4e678c086f69f9bf73299221963794e81e93cd3eb6b3",
            "Volumes": null,
            "WorkingDir": "",
            "Entrypoint": null,
            "OnBuild": null,
            "Labels": {
                "org.opencontainers.image.ref.name": "ubuntu",
                "org.opencontainers.image.version": "22.04"
            }
        },
        "DockerVersion": "20.10.21",
        "Author": "",
        "Config": {
            "Hostname": "",
            "Domainname": "",
            "User": "",
            "AttachStdin": false,
            "AttachStdout": false,
            "AttachStderr": false,
            "Tty": false,
            "OpenStdin": false,
            "StdinOnce": false,
            "Env": [
                "PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"
            ],
            "Cmd": [
                "/bin/bash"
            ],
            "Image": "sha256:62d2c268ed32cbee7f6f4e678c086f69f9bf73299221963794e81e93cd3eb6b3",
            "Volumes": null,
            "WorkingDir": "",
            "Entrypoint": null,
            "OnBuild": null,
            "Labels": {
                "org.opencontainers.image.ref.name": "ubuntu",
                "org.opencontainers.image.version": "22.04"
            }
        },
        "Architecture": "arm64",
        "Variant": "v8",
        "Os": "linux",
        "Size": 69185429,
        "VirtualSize": 69185429,
        "GraphDriver": {
            "Data": {
                "MergedDir": "/var/lib/docker/overlay2/188a167283c0346616e8f2e24660a1ce6298360ad3353cc2bbf6f0989af00384/merged",
                "UpperDir": "/var/lib/docker/overlay2/188a167283c0346616e8f2e24660a1ce6298360ad3353cc2bbf6f0989af00384/diff",
                "WorkDir": "/var/lib/docker/overlay2/188a167283c0346616e8f2e24660a1ce6298360ad3353cc2bbf6f0989af00384/work"
            },
            "Name": "overlay2"
        },
        "RootFS": {
            "Type": "layers",
            "Layers": [
                "sha256:c5ca84f245d30117a9a2720cb4297cedf3642816471d4d699f4d77e39e13a39c"
            ]
        },
        "Metadata": {
            "LastTagTime": "0001-01-01T00:00:00Z"
        }
    }
]
$ 

---------------------------------------------------------------------------------------------

# PULL DOCKER IMAGE FROM AN EXISTING IMAGE FROM DOCKERHUB

# SIGN UP TO DOCKER HUB: [SIGN UP](https://hub.docker.com/signup)

# LOGIN TO DOCKER HUB

# CLICK AN EXISTING IMAGE AND PULL INTO LOCAL

$ docker pull 782782/ubuntu-node
Using default tag: latest
latest: Pulling from 782782/ubuntu-node
7b1a6ab2e44d: Pull complete 
6c80bcce0bad: Pull complete 
Digest: sha256:681a299ae454a8af66b81e51ecfc357d4de4c5f559d9e845a58c6ba887c0ba3d
Status: Downloaded newer image for 782782/ubuntu-node:latest
docker.io/782782/ubuntu-node:latest

$ docker rmi $(docker images -a)
Untagged: 782782/ubuntu-node:latest
Untagged: 782782/ubuntu-node@sha256:681a299ae454a8af66b81e51ecfc357d4de4c5f559d9e845a58c6ba887c0ba3d
Deleted: sha256:7eae73787a4182623347cadec10cc7094b796f30fbed2cdaa751565852de3450
Deleted: sha256:71dbac2c5f032161d84b20f1a341ff4da3b9d2c1537c7c62b85486631b190be7
Deleted: sha256:9f54eef412758095c8079ac465d494a2872e02e90bf1fb5f12a1641c0d1bb78b

---------------------------------------------------------------------------------------------

--------------------------------------------------------------------------------------------------------

# Docker Installation:

[Get Started](https://www.docker.com/get-started)
	
[SignUp](https://hub.docker.com/signup)
	
# Once Sign Up Completed -> Login to Docker Hub through CLI:

$ docker login -u <user-name> 
Password: ********	

$ docker login -u xavyaly
Password: 
Login Succeeded

Logging in with your password grants your terminal complete access to your account. 
For better security, log in with a limited-privilege personal access token. Learn more at https://docs.docker.com/go/access-tokens/

# Once Login successded, tag the docker image 

# [SYNTAX]: docker tag local-image:tagname new-repo:tagname

$ docker images
REPOSITORY   TAG       IMAGE ID   CREATED   SIZE

$ docker pull ubuntu 
Using default tag: latest
latest: Pulling from library/ubuntu
5af00eab9784: Pull complete 
Digest: sha256:0bced47fffa3361afa981854fcabcd4577cd43cebbb808cea2b1f33a3dd7f508
Status: Downloaded newer image for ubuntu:latest
docker.io/library/ubuntu:latest

$ docker images
REPOSITORY   TAG       IMAGE ID       CREATED       SIZE
ubuntu       latest    37f74891464b   6 weeks ago   69.2MB

$ docker tag ubuntu:latest 782782/08-aug-2023:ubuntu0.1

$ docker images
REPOSITORY           TAG         IMAGE ID       CREATED       SIZE
782782/08-aug-2023   ubuntu0.1   37f74891464b   6 weeks ago   69.2MB
ubuntu               latest      37f74891464b   6 weeks ago   69.2MB

# [SYNTAX]: docker push new-repo:tagname

$ docker push 782782/08-aug-2023:ubuntu0.1 
The push refers to repository [docker.io/782782/08-aug-2023]
c5ca84f245d3: Preparing 
denied: requested access to the resource is denied

$ docker logout
Removing login credentials for https://index.docker.io/v1/

--------------------------------------------------------------------------------------------------------


# DOCKERFILE COMMANDS

[DOCKERFILE](https://blog.knoldus.com/docker-dockerfile/)


# REDUCE DOCKER IMAGE SIZE 

[SLIM DOCKER IAMGES](https://semaphoreci.com/blog/reduce-docker-image-size)


--------------------------------------------------------------------------------------------------------


