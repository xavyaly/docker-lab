# DAY #1 

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

# DAY #2

# DOCKER ARCHITECTURE DIAGRAM

<img width="508" alt="docker-architecture" src="https://github.com/xavyaly/docker-lab/assets/19641964/6746861e-385f-4071-86e5-3005c64d0d2e">


--------------------------------------------------------------------------------------------------------

# DAY #2

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


# DAY #3

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

# DAY #3

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


# DOCKER COMMANDS:

# Docker home directory: stores all images, containers, volumes, networks information
$ /var/lib/docker

Format: docker <command> <sub-command> 

Examples:

$ docker image ls 

$ docker help

Usage:  docker [OPTIONS] COMMAND

A self-sufficient runtime for containers

Common Commands:
  run         Create and run a new container from an image
  exec        Execute a command in a running container
  ps          List containers
  build       Build an image from a Dockerfile
  pull        Download an image from a registry
  push        Upload an image to a registry
  images      List images
  login       Log in to a registry
  logout      Log out from a registry
  search      Search Docker Hub for images
  version     Show the Docker version information
  info        Display system-wide information

Management Commands:
  builder     Manage builds
  buildx*     Docker Buildx (Docker Inc., v0.10.4)
  checkpoint  Manage checkpoints
  compose*    Docker Compose (Docker Inc., v2.17.3)
  container   Manage containers
  context     Manage contexts
  dev*        Docker Dev Environments (Docker Inc., v0.1.0)
  extension*  Manages Docker extensions (Docker Inc., v0.2.19)
  image       Manage images
  init*       Creates Docker-related starter files for your project (Docker Inc., v0.1.0-beta.4)
  manifest    Manage Docker image manifests and manifest lists
  network     Manage networks
  plugin      Manage plugins
  sbom*       View the packaged-based Software Bill Of Materials (SBOM) for an image (Anchore Inc., 0.6.0)
  scan*       Docker Scan (Docker Inc., v0.26.0)
  scout*      Command line tool for Docker Scout (Docker Inc., v0.10.0)
  system      Manage Docker
  trust       Manage trust on Docker images
  volume      Manage volumes

Swarm Commands:
  config      Manage Swarm configs
  node        Manage Swarm nodes
  secret      Manage Swarm secrets
  service     Manage Swarm services
  stack       Manage Swarm stacks
  swarm       Manage Swarm

Commands:
  attach      Attach local standard input, output, and error streams to a running container
  commit      Create a new image from a container's changes
  cp          Copy files/folders between a container and the local filesystem
  create      Create a new container
  diff        Inspect changes to files or directories on a container's filesystem
  events      Get real time events from the server
  export      Export a container's filesystem as a tar archive
  history     Show the history of an image
  import      Import the contents from a tarball to create a filesystem image
  inspect     Return low-level information on Docker objects
  kill        Kill one or more running containers
  load        Load an image from a tar archive or STDIN
  logs        Fetch the logs of a container
  pause       Pause all processes within one or more containers
  port        List port mappings or a specific mapping for the container
  rename      Rename a container
  restart     Restart one or more containers
  rm          Remove one or more containers
  rmi         Remove one or more images
  save        Save one or more images to a tar archive (streamed to STDOUT by default)
  start       Start one or more stopped containers
  stats       Display a live stream of container(s) resource usage statistics
  stop        Stop one or more running containers
  tag         Create a tag TARGET_IMAGE that refers to SOURCE_IMAGE
  top         Display the running processes of a container
  unpause     Unpause all processes within one or more containers
  update      Update configuration of one or more containers
  wait        Block until one or more containers stop, then print their exit codes

Global Options:
      --config string      Location of client config files (default "/Users/javedalam/.docker")
  -c, --context string     Name of the context to use to connect to the daemon (overrides DOCKER_HOST env var and
                           default context set with "docker context use")
  -D, --debug              Enable debug mode
  -H, --host list          Daemon socket(s) to connect to
  -l, --log-level string   Set the logging level ("debug", "info", "warn", "error", "fatal") (default "info")
      --tls                Use TLS; implied by --tlsverify
      --tlscacert string   Trust certs signed only by this CA (default "/Users/javedalam/.docker/ca.pem")
      --tlscert string     Path to TLS certificate file (default "/Users/javedalam/.docker/cert.pem")
      --tlskey string      Path to TLS key file (default "/Users/javedalam/.docker/key.pem")
      --tlsverify          Use TLS and verify the remote
  -v, --version            Print version information and quit

Run 'docker COMMAND --help' for more information on a command.

For more help on how to use Docker, head to https://docs.docker.com/go/guides/


$ docker image help

Usage:  docker image COMMAND

Manage images

Commands:
  build       Build an image from a Dockerfile
  history     Show the history of an image
  import      Import the contents from a tarball to create a filesystem image
  inspect     Display detailed information on one or more images
  load        Load an image from a tar archive or STDIN
  ls          List images
  prune       Remove unused images
  pull        Download an image from a registry
  push        Upload an image to a registry
  rm          Remove one or more images
  save        Save one or more images to a tar archive (streamed to STDOUT by default)
  tag         Create a tag TARGET_IMAGE that refers to SOURCE_IMAGE

Run 'docker image COMMAND --help' for more information on a command.


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

# DAY #4

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


--------------------------------------------------------------------------------------------------------

# DAY #4

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

# DAY #5

# DOCKERFILE COMMANDS

[DOCKERFILE](https://blog.knoldus.com/docker-dockerfile/)


# REDUCE DOCKER IMAGE SIZE 

[SLIM DOCKER IAMGES](https://semaphoreci.com/blog/reduce-docker-image-size)


--------------------------------------------------------------------------------------------------------


# DAY #6

# SAMPLE PROJECT TO UNDERSTAND DOCKER CONTAINER

# Create a directory 
```
mkdir python
cd python
```

# Follow the below steps 

Certainly, I'll guide you through creating a simple Dockerfile, building an image, and running a container on your Mac. Let's use a basic Python web application as an example.

1. **Create a Dockerfile**:
   Open a text editor and create a file named `Dockerfile` (no file extension) in a directory. Add the following content to the Dockerfile:

   ```Dockerfile
   # Use the official Python image as the base
   FROM python:3.8
   
   # Set the working directory inside the container
   WORKDIR /app
   
   # Copy the requirements file into the container at /app
   COPY requirements.txt .
   
   # Install any needed packages specified in requirements.txt
   RUN pip install --no-cache-dir -r requirements.txt
   
   # Copy the rest of the application code into the container at /app
   COPY . .
   
   # Specify the command to run on container startup
   CMD ["python", "app.py"]
   ```

2. **Create a Simple Python Web App**:
   In the same directory as the Dockerfile, create a file named `app.py` and add the following content:

   ```python
   from flask import Flask
   app = Flask(__name__)
   
   @app.route('/')
   def hello_world():
       return 'Hello, Docker!'
   
   if __name__ == '__main__':
       app.run(host='0.0.0.0', port=80)
   ```

3. **Create a Requirements File**:
   Create a file named `requirements.txt` in the same directory and add the following line:

   ```
   flask
   ```

4. **Build the Docker Image**:
   Open a terminal and navigate to the directory containing the Dockerfile and app files. Run the following command to build the Docker image:

   ```bash
   docker build -t python-web-app .

%  $ docker build -t python-web-app .
% [+] Building 4.2s (11/11) FINISHED                                                                                          
%  => [internal] load .dockerignore                                                                                      0.0s
%  => => transferring context: 2B                                                                                        0.0s
%  => [internal] load build definition from Dockerfile                                                                   0.0s
%  => => transferring dockerfile: 213B                                                                                   0.0s
%  => [internal] load metadata for docker.io/library/python:3.8                                                          4.1s
%  => [auth] library/python:pull token for registry-1.docker.io                                                          0.0s
%  => [internal] load build context                                                                                      0.0s
%  => => transferring context: 394B                                                                                      0.0s
%  => [1/5] FROM docker.io/library/python:3.8@sha256:445daa405d17b65d0ab3626082691f93637c9aa78aae5e72b5971685716b2e99    0.0s
%  => => resolve docker.io/library/python:3.8@sha256:445daa405d17b65d0ab3626082691f93637c9aa78aae5e72b5971685716b2e99    0.0s
%  => CACHED [2/5] WORKDIR /app                                                                                          0.0s
%  => CACHED [3/5] COPY requirement.txt .                                                                                0.0s
%  => CACHED [4/5] RUN pip install --no-cache-dir -r requirement.txt                                                     0.0s
%  => [5/5] COPY . .                                                                                                     0.0s
%  => exporting to image                                                                                                 0.0s
%  => => exporting layers                                                                                                0.0s
%  => => writing image sha256:8dfce5caa92d774c4a8aa814ea8c8129b3be7799cb61f8c840e0d2aa80fd0d84                           0.0s
%  => => naming to docker.io/library/python-web-app   

   ```

   This command builds an image named `python-web-app` using the current directory as the build context.

5. **Run a Docker Container**:
   After the image is built, you can run a container from it. Use the following command:

   ```bash
   docker run -p 8080:80 python-web-app

 <!-- $ docker run -p 8080:80 python-web-app
 * Serving Flask app 'app'
 * Debug mode: off
WARNING: This is a development server. Do not use it in a production deployment. Use a production WSGI server instead.
 * Running on all addresses (0.0.0.0)
 * Running on http://127.0.0.1:80
 * Running on http://172.17.0.2:80
Press CTRL+C to quit
172.17.0.1 - - [17/Aug/2023 06:55:42] "GET / HTTP/1.1" 200 -
172.17.0.1 - - [17/Aug/2023 06:57:04] "GET / HTTP/1.1" 200 - -->

   ```

   This maps port 8080 on your local machine to port 80 inside the container.

6. **Access the Web App**:
   Open a web browser and navigate to `http://localhost:8080`. You should see the "Hello, Docker!" message from your web app.

Remember that this is a simple example to get you started. You can modify the Dockerfile, app code, and other components to suit your specific needs. Additionally, make sure Docker is installed and running on your Mac before you start this process.


--------------------------------------------------------------------------------------------------------


# DOCKER CONTAINER

# Imp point:
# Container gets attached to a network and gets a virtual IP
# inside the private network, typically default bridge network 
# Opens up ports to serve the requests

# REMOVE THE DOCKER MULTIPLE CONTAINERS
   $ docker rm $(docker ps -a)

# REMOVE THE DOCKER MULTIPLE IMAGES
    docker rmi $(docker images)
   

# CREATE A NGINX CONTAINER 
   $ docker run nginx            # it runs in the foreground and terminal is attached to its process
   $ docker run --detach nginx   # run the container in detached(background) mode using --detach

   $ docker ps                    # list all running containers
   $ docker ps -a                 # list all running and exited containers 

   
   # INSPECT A CONTAINER
   $ docker inspect container <CONTAINER ID>

   
   # FETCH THE CONTAINER IP 
   $ docker container inspect --format "{{.NetworkSettings.IPAddress}}" <CONTAINER ID>
   172.17.0.2
   $ curl <IP>:<PORT>


   # CONTAINER START AND STOP AND REMOVE 
   $ docker ps -a
   CONTAINER ID   IMAGE     COMMAND                  CREATED         STATUS         PORTS     NAMES
   2272c999aa2f   nginx     "/docker-entrypoint.…"   9 minutes ago   Up 9 minutes   80/tcp    charming_meninsky
   $ docker stop 22
   22
   $ docker ps -a
   CONTAINER ID   IMAGE     COMMAND                  CREATED         STATUS                     PORTS     NAMES
   2272c999aa2f   nginx     "/docker-entrypoint.…"   9 minutes ago   Exited (0) 2 seconds ago             charming_meninsky
   $ docker start 22
   22
   $ docker ps -a
   CONTAINER ID   IMAGE     COMMAND                  CREATED          STATUS        PORTS     NAMES
   2272c999aa2f   nginx     "/docker-entrypoint.…"   10 minutes ago   Up 1 second   80/tcp    charming_meninsky   
   $ docker rm 22
   Error response from daemon: You cannot remove a running container 2272c999aa2fad2091dfa45298119803bf0f833b2c9af28a4a90ac80142789c2. Stop the container before attempting removal or force remove
   $ docker stop 22
   22
   $ docker rm 22
   22


   # PORT MAPPING 
   $ docker run --detach -p 8080:80 nginx 
   Unable to find image 'nginx:latest' locally
   latest: Pulling from library/nginx
   4ee097f9a366: Pull complete 
   6710b2157bb5: Pull complete 
   76d048093f36: Pull complete 
   658197f4b592: Pull complete 
   a2543a59b279: Pull complete 
   3972a57e5575: Pull complete 
   82359da50743: Pull complete 
   Digest: sha256:104c7c5c54f2685f0f46f3be607ce60da7085da3eaa5ad22d3d9f01594295e9c
   Status: Downloaded newer image for nginx:latest
   4cc6af0d9e4b80eff4230efe2116662d3b2b2235a11c77b40f7d2c4f7e7b32bd
   $ docker images -a
   REPOSITORY   TAG       IMAGE ID       CREATED      SIZE
   nginx        latest    ab73c7fd6723   2 days ago   192MB
   $ docker ps -a
   CONTAINER ID   IMAGE     COMMAND                  CREATED          STATUS          PORTS                  NAMES
   4cc6af0d9e4b   nginx     "/docker-entrypoint.…"   13 seconds ago   Up 13 seconds   0.0.0.0:8080->80/tcp   hopeful_stonebraker

   # Try in browser
      http://localhost:8080
      Welcome to nginx!

      If you see this page, the nginx web server is successfully installed and working. Further configuration is required.

      For online documentation and support please refer to nginx.org.
      Commercial support is available at nginx.com.

      Thank you for using nginx.

   # CONTAINER IP
   $ docker inspect --format "{{.NetworkSettings.IPAddress}}" 4cc
   172.17.0.2
   # HOST IP
   $ docker container inspect 4cc      # HostIp 


--------------------------------------------------------------------------------------------------------

# DOCKER CONTAINERS 

$ docker images -a
REPOSITORY   TAG       IMAGE ID   CREATED   SIZE
$ docker ps -a
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES


# remove a running continer forcefully
$ docker rm <Container ID> -f


# Create a new nginx container
$ docker run -d -p 8080:80 nginx 
Unable to find image 'nginx:latest' locally
latest: Pulling from library/nginx
4ee097f9a366: Pull complete 
6710b2157bb5: Pull complete 
76d048093f36: Pull complete 
658197f4b592: Pull complete 
a2543a59b279: Pull complete 
3972a57e5575: Pull complete 
82359da50743: Pull complete 
Digest: sha256:104c7c5c54f2685f0f46f3be607ce60da7085da3eaa5ad22d3d9f01594295e9c
Status: Downloaded newer image for nginx:latest
77b9a43da5e05d86ec7752aad5a5f3150d99d0ac9237680a70435126f6959519

# rename an existing container 
$ docker ps -a
CONTAINER ID   IMAGE     COMMAND                  CREATED         STATUS         PORTS                  NAMES
77b9a43da5e0   nginx     "/docker-entrypoint.…"   6 seconds ago   Up 5 seconds   0.0.0.0:8080->80/tcp   gifted_shockley
$ docker rename gifted_shockley nginx-0.1
$ docker ps -a
CONTAINER ID   IMAGE     COMMAND                  CREATED          STATUS          PORTS                  NAMES
77b9a43da5e0   nginx     "/docker-entrypoint.…"   32 seconds ago   Up 31 seconds   0.0.0.0:8080->80/tcp   nginx-0.1


# Stop a running container 
$ docker stop 77
77
$ docker ps -a
CONTAINER ID   IMAGE     COMMAND                  CREATED         STATUS                    PORTS     NAMES
77b9a43da5e0   nginx     "/docker-entrypoint.…"   2 minutes ago   Exited (0) 1 second ago             nginx-0.1


# Start a stopped container
$ docker start 77
77
$ docker ps -a
CONTAINER ID   IMAGE     COMMAND                  CREATED         STATUS        PORTS                  NAMES
77b9a43da5e0   nginx     "/docker-entrypoint.…"   3 minutes ago   Up 1 second   0.0.0.0:8080->80/tcp   nginx-0.1


# Container Logs
$ docker container logs nginx-0.1
/docker-entrypoint.sh: /docker-entrypoint.d/ is not empty, will attempt to perform configuration
/docker-entrypoint.sh: Looking for shell scripts in /docker-entrypoint.d/
/docker-entrypoint.sh: Launching /docker-entrypoint.d/10-listen-on-ipv6-by-default.sh
10-listen-on-ipv6-by-default.sh: info: Getting the checksum of /etc/nginx/conf.d/default.conf
10-listen-on-ipv6-by-default.sh: info: Enabled listen on IPv6 in /etc/nginx/conf.d/default.conf
/docker-entrypoint.sh: Sourcing /docker-entrypoint.d/15-local-resolvers.envsh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/20-envsubst-on-templates.sh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/30-tune-worker-processes.sh
/docker-entrypoint.sh: Configuration complete; ready for start up
2023/08/21 06:52:08 [notice] 1#1: using the "epoll" event method
2023/08/21 06:52:08 [notice] 1#1: nginx/1.25.2
2023/08/21 06:52:08 [notice] 1#1: built by gcc 12.2.0 (Debian 12.2.0-14) 
2023/08/21 06:52:08 [notice] 1#1: OS: Linux 5.15.49-linuxkit
2023/08/21 06:52:08 [notice] 1#1: getrlimit(RLIMIT_NOFILE): 1048576:1048576
2023/08/21 06:52:08 [notice] 1#1: start worker processes
2023/08/21 06:52:08 [notice] 1#1: start worker process 29
2023/08/21 06:52:08 [notice] 1#1: start worker process 30
2023/08/21 06:52:08 [notice] 1#1: start worker process 31
2023/08/21 06:52:08 [notice] 1#1: start worker process 32
2023/08/21 06:54:43 [notice] 1#1: signal 3 (SIGQUIT) received, shutting down
2023/08/21 06:54:43 [notice] 30#30: gracefully shutting down
2023/08/21 06:54:43 [notice] 29#29: gracefully shutting down
2023/08/21 06:54:43 [notice] 31#31: gracefully shutting down
2023/08/21 06:54:43 [notice] 30#30: exiting
2023/08/21 06:54:43 [notice] 32#32: gracefully shutting down
2023/08/21 06:54:43 [notice] 30#30: exit
2023/08/21 06:54:43 [notice] 32#32: exiting
2023/08/21 06:54:43 [notice] 32#32: exit
2023/08/21 06:54:43 [notice] 31#31: exiting
2023/08/21 06:54:43 [notice] 29#29: exiting
2023/08/21 06:54:43 [notice] 29#29: exit
2023/08/21 06:54:43 [notice] 31#31: exit
2023/08/21 06:54:43 [notice] 1#1: signal 17 (SIGCHLD) received from 31
2023/08/21 06:54:43 [notice] 1#1: worker process 31 exited with code 0
2023/08/21 06:54:43 [notice] 1#1: signal 29 (SIGIO) received
2023/08/21 06:54:43 [notice] 1#1: signal 17 (SIGCHLD) received from 32
2023/08/21 06:54:43 [notice] 1#1: worker process 29 exited with code 0
2023/08/21 06:54:43 [notice] 1#1: worker process 32 exited with code 0
2023/08/21 06:54:43 [notice] 1#1: worker process 30 exited with code 0
2023/08/21 06:54:43 [notice] 1#1: exit
/docker-entrypoint.sh: /docker-entrypoint.d/ is not empty, will attempt to perform configuration
/docker-entrypoint.sh: Looking for shell scripts in /docker-entrypoint.d/
/docker-entrypoint.sh: Launching /docker-entrypoint.d/10-listen-on-ipv6-by-default.sh
10-listen-on-ipv6-by-default.sh: info: IPv6 listen already enabled
/docker-entrypoint.sh: Sourcing /docker-entrypoint.d/15-local-resolvers.envsh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/20-envsubst-on-templates.sh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/30-tune-worker-processes.sh
/docker-entrypoint.sh: Configuration complete; ready for start up
2023/08/21 06:55:38 [notice] 1#1: using the "epoll" event method
2023/08/21 06:55:38 [notice] 1#1: nginx/1.25.2
2023/08/21 06:55:38 [notice] 1#1: built by gcc 12.2.0 (Debian 12.2.0-14) 
2023/08/21 06:55:38 [notice] 1#1: OS: Linux 5.15.49-linuxkit
2023/08/21 06:55:38 [notice] 1#1: getrlimit(RLIMIT_NOFILE): 1048576:1048576
2023/08/21 06:55:38 [notice] 1#1: start worker processes
2023/08/21 06:55:38 [notice] 1#1: start worker process 22
2023/08/21 06:55:38 [notice] 1#1: start worker process 23
2023/08/21 06:55:38 [notice] 1#1: start worker process 24
2023/08/21 06:55:38 [notice] 1#1: start worker process 25

$ docker container logs -f nginx-0.1
/docker-entrypoint.sh: /docker-entrypoint.d/ is not empty, will attempt to perform configuration
/docker-entrypoint.sh: Looking for shell scripts in /docker-entrypoint.d/
/docker-entrypoint.sh: Launching /docker-entrypoint.d/10-listen-on-ipv6-by-default.sh
10-listen-on-ipv6-by-default.sh: info: Getting the checksum of /etc/nginx/conf.d/default.conf
10-listen-on-ipv6-by-default.sh: info: Enabled listen on IPv6 in /etc/nginx/conf.d/default.conf
/docker-entrypoint.sh: Sourcing /docker-entrypoint.d/15-local-resolvers.envsh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/20-envsubst-on-templates.sh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/30-tune-worker-processes.sh
/docker-entrypoint.sh: Configuration complete; ready for start up
2023/08/21 06:52:08 [notice] 1#1: using the "epoll" event method
2023/08/21 06:52:08 [notice] 1#1: nginx/1.25.2
2023/08/21 06:52:08 [notice] 1#1: built by gcc 12.2.0 (Debian 12.2.0-14) 
2023/08/21 06:52:08 [notice] 1#1: OS: Linux 5.15.49-linuxkit
2023/08/21 06:52:08 [notice] 1#1: getrlimit(RLIMIT_NOFILE): 1048576:1048576
2023/08/21 06:52:08 [notice] 1#1: start worker processes
2023/08/21 06:52:08 [notice] 1#1: start worker process 29
2023/08/21 06:52:08 [notice] 1#1: start worker process 30
2023/08/21 06:52:08 [notice] 1#1: start worker process 31
2023/08/21 06:52:08 [notice] 1#1: start worker process 32
2023/08/21 06:54:43 [notice] 1#1: signal 3 (SIGQUIT) received, shutting down
2023/08/21 06:54:43 [notice] 30#30: gracefully shutting down
2023/08/21 06:54:43 [notice] 29#29: gracefully shutting down
2023/08/21 06:54:43 [notice] 31#31: gracefully shutting down
2023/08/21 06:54:43 [notice] 30#30: exiting
2023/08/21 06:54:43 [notice] 32#32: gracefully shutting down
2023/08/21 06:54:43 [notice] 30#30: exit
2023/08/21 06:54:43 [notice] 32#32: exiting
2023/08/21 06:54:43 [notice] 32#32: exit
2023/08/21 06:54:43 [notice] 31#31: exiting
2023/08/21 06:54:43 [notice] 29#29: exiting
2023/08/21 06:54:43 [notice] 29#29: exit
2023/08/21 06:54:43 [notice] 31#31: exit
2023/08/21 06:54:43 [notice] 1#1: signal 17 (SIGCHLD) received from 31
2023/08/21 06:54:43 [notice] 1#1: worker process 31 exited with code 0
2023/08/21 06:54:43 [notice] 1#1: signal 29 (SIGIO) received
2023/08/21 06:54:43 [notice] 1#1: signal 17 (SIGCHLD) received from 32
2023/08/21 06:54:43 [notice] 1#1: worker process 29 exited with code 0
2023/08/21 06:54:43 [notice] 1#1: worker process 32 exited with code 0
2023/08/21 06:54:43 [notice] 1#1: worker process 30 exited with code 0
2023/08/21 06:54:43 [notice] 1#1: exit
/docker-entrypoint.sh: /docker-entrypoint.d/ is not empty, will attempt to perform configuration
/docker-entrypoint.sh: Looking for shell scripts in /docker-entrypoint.d/
/docker-entrypoint.sh: Launching /docker-entrypoint.d/10-listen-on-ipv6-by-default.sh
10-listen-on-ipv6-by-default.sh: info: IPv6 listen already enabled
/docker-entrypoint.sh: Sourcing /docker-entrypoint.d/15-local-resolvers.envsh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/20-envsubst-on-templates.sh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/30-tune-worker-processes.sh
/docker-entrypoint.sh: Configuration complete; ready for start up
2023/08/21 06:55:38 [notice] 1#1: using the "epoll" event method
2023/08/21 06:55:38 [notice] 1#1: nginx/1.25.2
2023/08/21 06:55:38 [notice] 1#1: built by gcc 12.2.0 (Debian 12.2.0-14) 
2023/08/21 06:55:38 [notice] 1#1: OS: Linux 5.15.49-linuxkit
2023/08/21 06:55:38 [notice] 1#1: getrlimit(RLIMIT_NOFILE): 1048576:1048576
2023/08/21 06:55:38 [notice] 1#1: start worker processes
2023/08/21 06:55:38 [notice] 1#1: start worker process 22
2023/08/21 06:55:38 [notice] 1#1: start worker process 23
2023/08/21 06:55:38 [notice] 1#1: start worker process 24
2023/08/21 06:55:38 [notice] 1#1: start worker process 25
...
...


# Container processes
$ docker top 77                     # 77 is container id 
UID                 PID                 PPID                C                   STIME               TTY                 TIME                CMD
root                97722               97698               0                   06:55               ?                   00:00:00            nginx: master process nginx -g daemon off;
uuidd               97768               97722               0                   06:55               ?                   00:00:00            nginx: worker process
uuidd               97769               97722               0                   06:55               ?                   00:00:00            nginx: worker process
uuidd               97770               97722               0                   06:55               ?                   00:00:00            nginx: worker process
uuidd               97771               97722               0                   06:55               ?                   00:00:00            nginx: worker process


# Containers stats: CPU, Mem usage etc 
$ docker container stats <container id>
CONTAINER ID   NAME        CPU %     MEM USAGE / LIMIT     MEM %     NET I/O       BLOCK I/O    PIDS
77b9a43da5e0   nginx-0.1   0.00%     4.227MiB / 3.841GiB   0.11%     1.16kB / 0B   0B / 4.1kB   5


# Remove a container
$ docker rm <container id>
$ docker rm <container id> -f       # for running container


# Kill a running container
$ docker ps -a
CONTAINER ID   IMAGE     COMMAND                  CREATED          STATUS         PORTS                  NAMES
77b9a43da5e0   nginx     "/docker-entrypoint.…"   10 minutes ago   Up 7 minutes   0.0.0.0:8080->80/tcp   nginx-0.1
$ docker container kill 77          # 77 is container id 
77
$ docker ps -a
CONTAINER ID   IMAGE     COMMAND                  CREATED          STATUS                       PORTS     NAMES
77b9a43da5e0   nginx     "/docker-entrypoint.…"   11 minutes ago   Exited (137) 3 seconds ago             nginx-0.1

--------------------------------------------------------------------------------------------------------

# Docker Container Shell Access: LOGIN TO CONTAINER

-i: INTERACTIVE or STD_IN
-t: TERMINAL or STD_OUT

$ docker run -it --name ubuntu bash 
Unable to find image 'bash:latest' locally
latest: Pulling from library/bash
9fda8d8052c6: Pull complete 
8c4de22bc10f: Pull complete 
d35fda97a14a: Pull complete 
Digest: sha256:d91f283473ba66c94dbd3b2aaab45cef4d67e65eec107481c2357f15f51a48b8
Status: Downloaded newer image for bash:latest
bash-5.2# 
bash-5.2# hostname
49a4a26bbed2
bash-5.2# uname -a
Linux 49a4a26bbed2 5.15.49-linuxkit #1 SMP PREEMPT Tue Sep 13 07:51:32 UTC 2022 aarch64 Linux
bash-5.2# exit

$ docker ps -a
CONTAINER ID   IMAGE                                 COMMAND                  CREATED          STATUS                        PORTS     NAMES
6da7642d1180   bash                                  "docker-entrypoint.s…"   10 minutes ago   Up 7 minutes                            ubuntu


# Note: Make sure to exit the command so that our container never exited

ctrl+P, ctrl+Q

# Login to a running container

$ docker ps -a
CONTAINER ID   IMAGE                                 COMMAND                  CREATED          STATUS                        PORTS     NAMES
6da7642d1180   bash                                  "docker-entrypoint.s…"   12 minutes ago   Up 9 minutes                            ubuntu

$ docker exec -it <container-id> bash
```
$ docker exec -it 6da7642d1180 bash
bash-5.2# uname -a
Linux 6da7642d1180 5.15.49-linuxkit #1 SMP PREEMPT Tue Sep 13 07:51:32 UTC 2022 aarch64 Linux
```


# IMAGE INSPECT 

$ docker pull ubuntu
Using default tag: latest
latest: Pulling from library/ubuntu
db76c1f8aa17: Pull complete 
Digest: sha256:ec050c32e4a6085b423d36ecd025c0d3ff00c38ab93a3d71a460ff1c44fa6d77
Status: Downloaded newer image for ubuntu:latest
docker.io/library/ubuntu:latest

$ docker images -a
REPOSITORY                    TAG       IMAGE ID       CREATED        SIZE
ubuntu                        latest    a2f229f811bf   3 weeks ago    69.2MB

$ docker image inspect ubuntu | grep "69187939"
        "Size": 69187939,
        "VirtualSize": 69187939,


# INTERACT WITH CONTAINER
```
REFER ABOVE COMMANDS
```

--------------------------------------------------------------------------------------------------------

# COMMIT CHANGES IN CONTAINER TO A IMAGE

$ docker ps -a
CONTAINER ID   IMAGE                                 COMMAND                  CREATED          STATUS                        PORTS     NAMES
6da7642d1180   bash                                  "docker-entrypoint.s…"   22 minutes ago   Up 19 minutes                           ubuntu

$ docker commit 6da7642d1180 jd:0.1
sha256:304ea80e42a15b3f60af9ea6ce3fd5a1dff912f2dea3cc83140927eb93f7e49e

$ docker images -a
REPOSITORY                    TAG       IMAGE ID       CREATED          SIZE
jd                            0.1       304ea80e42a1   21 seconds ago   16.3MB

$ docker run -it 304ea80e42a1  bash 
bash-5.2# 
bash-5.2# exit

$ docker ps -a
CONTAINER ID   IMAGE                                 COMMAND                  CREATED          STATUS                        PORTS     NAMES
a769463e6e80   304ea80e42a1                          "docker-entrypoint.s…"   11 seconds ago   Exited (0) 3 seconds ago                competent_dijkstra

--------------------------------------------------------------------------------------------------------

[Docker CLI Commands](https://docs.docker.com/engine/reference/run/)

--------------------------------------------------------------------------------------------------------

# DOCKER NETWORKING

$ docker network ls
NETWORK ID     NAME       DRIVER    SCOPE
a1de4a47ae08   bridge     bridge    local
978bc14b731e   host       host      local
d992199cc5d9   minikube   bridge    local
48bcb2d731c8   none       null      local

$ docker network inspect bridge
[
    {
        "Name": "bridge",
        "Id": "a1de4a47ae08ca6409580e99588138027527d2ca153b47fdcb2ca867f96bfe75",
        "Created": "2023-08-16T10:09:14.975529708Z",
        "Scope": "local",
        "Driver": "bridge",
        "EnableIPv6": false,
        "IPAM": {
            "Driver": "default",
            "Options": null,
            "Config": [
                {
                    "Subnet": "172.17.0.0/16",
                    "Gateway": "172.17.0.1"
                }
            ]
        },
        "Internal": false,
        "Attachable": false,
        "Ingress": false,
        "ConfigFrom": {
            "Network": ""
        },
        "ConfigOnly": false,
        "Containers": {},
        "Options": {
            "com.docker.network.bridge.default_bridge": "true",
            "com.docker.network.bridge.enable_icc": "true",
            "com.docker.network.bridge.enable_ip_masquerade": "true",
            "com.docker.network.bridge.host_binding_ipv4": "0.0.0.0",
            "com.docker.network.bridge.name": "docker0",
            "com.docker.network.driver.mtu": "65535"
        },
        "Labels": {}
    }
]

$ docker network inspect host
[
    {
        "Name": "host",
        "Id": "978bc14b731e92de9c4ff38892a8853a54028f0f8e3b202e22ff67a3018654b2",
        "Created": "2023-05-06T19:19:58.286646583Z",
        "Scope": "local",
        "Driver": "host",
        "EnableIPv6": false,
        "IPAM": {
            "Driver": "default",
            "Options": null,
            "Config": []
        },
        "Internal": false,
        "Attachable": false,
        "Ingress": false,
        "ConfigFrom": {
            "Network": ""
        },
        "ConfigOnly": false,
        "Containers": {},
        "Options": {},
        "Labels": {}
    }
]

$ docker network inspect none
[
    {
        "Name": "none",
        "Id": "48bcb2d731c841db858c7e88bbb710af5dd3bfc226aa24988852545afc8348cf",
        "Created": "2023-05-06T19:19:58.277581916Z",
        "Scope": "local",
        "Driver": "null",
        "EnableIPv6": false,
        "IPAM": {
            "Driver": "default",
            "Options": null,
            "Config": []
        },
        "Internal": false,
        "Attachable": false,
        "Ingress": false,
        "ConfigFrom": {
            "Network": ""
        },
        "ConfigOnly": false,
        "Containers": {},
        "Options": {},
        "Labels": {}
    }
]

--------------------------------------------------------------------------------------------------------

# BRIDGE NETOWORK

$ docker run -d -it --name c1 ubuntu
```
$ docker run -d -it --name c1 ubuntu
a2d551633af9b16e3c3b26764dc6419519bdeeed0e68bbcab26c0ee3c8c5adb2
```

$ docker run -d -it --name c2 ubuntu
```
$ docker run -d -it --name c2 ubuntu
aab7309dcc49c09282dd6faf2f1668ad2a715fc09eae862c5a6ac6bc65531ad3
```

$ docker ps -a
```
$ docker ps -a
CONTAINER ID   IMAGE                                 COMMAND                  CREATED          STATUS                      PORTS     NAMES
a2d551633af9   ubuntu                                "/bin/bash"              57 seconds ago   Up 56 seconds                         c1
aab7309dcc49   ubuntu                                "/bin/bash"              8 minutes ago    Up 8 minutes                          c2
a769463e6e80   304ea80e42a1                          "docker-entrypoint.s…"   24 hours ago     Exited (0) 24 hours ago               competent_dijkstra
865c325fcef5   gcr.io/k8s-minikube/kicbase:v0.0.39   "/usr/local/bin/entr…"   2 days ago       Exited (130) 24 hours ago             minikube
```

# LOGIN TO ANY CONTIANER
$ docker exec -it aa bash
```
$ docker exec -it aa bash
root@aab7309dcc49:/# 
root@aab7309dcc49:/# hostname
aab7309dcc49
root@aab7309dcc49:/# ping c1
bash: ping: command not found

root@aab7309dcc49:/# ps -ef | grep ping
root          20       9  0 06:46 pts/1    00:00:00 grep --color=auto ping

root@aab7309dcc49:/# apt-get update
Get:1 http://ports.ubuntu.com/ubuntu-ports jammy InRelease [270 kB]
Get:2 http://ports.ubuntu.com/ubuntu-ports jammy-updates InRelease [119 kB]
Get:3 http://ports.ubuntu.com/ubuntu-ports jammy-backports InRelease [109 kB]
Get:4 http://ports.ubuntu.com/ubuntu-ports jammy-security InRelease [110 kB]
Get:5 http://ports.ubuntu.com/ubuntu-ports jammy/multiverse arm64 Packages [224 kB]
Get:6 http://ports.ubuntu.com/ubuntu-ports jammy/universe arm64 Packages [17.2 MB]
Get:7 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 Packages [1758 kB]
Get:8 http://ports.ubuntu.com/ubuntu-ports jammy/restricted arm64 Packages [24.2 kB]
Get:9 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 Packages [1016 kB]
Get:10 http://ports.ubuntu.com/ubuntu-ports jammy-updates/multiverse arm64 Packages [27.8 kB]
Get:11 http://ports.ubuntu.com/ubuntu-ports jammy-updates/restricted arm64 Packages [556 kB]
Get:12 http://ports.ubuntu.com/ubuntu-ports jammy-updates/universe arm64 Packages [1127 kB]
Get:13 http://ports.ubuntu.com/ubuntu-ports jammy-backports/universe arm64 Packages [23.7 kB]                                                          
Get:14 http://ports.ubuntu.com/ubuntu-ports jammy-backports/main arm64 Packages [48.8 kB]                                                              
Get:15 http://ports.ubuntu.com/ubuntu-ports jammy-security/universe arm64 Packages [870 kB]                                                            
Get:16 http://ports.ubuntu.com/ubuntu-ports jammy-security/restricted arm64 Packages [548 kB]                                                          
Get:17 http://ports.ubuntu.com/ubuntu-ports jammy-security/multiverse arm64 Packages [23.4 kB]                                                         
Get:18 http://ports.ubuntu.com/ubuntu-ports jammy-security/main arm64 Packages [748 kB]                                                                
Fetched 24.8 MB in 7s (3633 kB/s)                                                                                                                      
Reading package lists... Done
root@aab7309dcc49:/# 

root@aab7309dcc49:/# apt-get install -y iputils-ping
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following additional packages will be installed:
  libcap2-bin libpam-cap
The following NEW packages will be installed:
  iputils-ping libcap2-bin libpam-cap
0 upgraded, 3 newly installed, 0 to remove and 2 not upgraded.
Need to get 76.8 kB of archives.
After this operation, 255 kB of additional disk space will be used.
Get:1 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libcap2-bin arm64 1:2.44-1ubuntu0.22.04.1 [25.5 kB]
Get:2 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 iputils-ping arm64 3:20211215-1 [43.3 kB]
Get:3 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libpam-cap arm64 1:2.44-1ubuntu0.22.04.1 [7968 B]
Fetched 76.8 kB in 1s (82.7 kB/s)     
debconf: delaying package configuration, since apt-utils is not installed
Selecting previously unselected package libcap2-bin.
(Reading database ... 4389 files and directories currently installed.)
Preparing to unpack .../libcap2-bin_1%3a2.44-1ubuntu0.22.04.1_arm64.deb ...
Unpacking libcap2-bin (1:2.44-1ubuntu0.22.04.1) ...
Selecting previously unselected package iputils-ping.
Preparing to unpack .../iputils-ping_3%3a20211215-1_arm64.deb ...
Unpacking iputils-ping (3:20211215-1) ...
Selecting previously unselected package libpam-cap:arm64.
Preparing to unpack .../libpam-cap_1%3a2.44-1ubuntu0.22.04.1_arm64.deb ...
Unpacking libpam-cap:arm64 (1:2.44-1ubuntu0.22.04.1) ...
Setting up libcap2-bin (1:2.44-1ubuntu0.22.04.1) ...
Setting up libpam-cap:arm64 (1:2.44-1ubuntu0.22.04.1) ...
debconf: unable to initialize frontend: Dialog
debconf: (No usable dialog-like program is installed, so the dialog based frontend cannot be used. at /usr/share/perl5/Debconf/FrontEnd/Dialog.pm line 78.)
debconf: falling back to frontend: Readline
debconf: unable to initialize frontend: Readline
debconf: (Can't locate Term/ReadLine.pm in @INC (you may need to install the Term::ReadLine module) (@INC contains: /etc/perl /usr/local/lib/aarch64-linux-gnu/perl/5.34.0 /usr/local/share/perl/5.34.0 /usr/lib/aarch64-linux-gnu/perl5/5.34 /usr/share/perl5 /usr/lib/aarch64-linux-gnu/perl-base /usr/lib/aarch64-linux-gnu/perl/5.34 /usr/share/perl/5.34 /usr/local/lib/site_perl) at /usr/share/perl5/Debconf/FrontEnd/Readline.pm line 7.)
debconf: falling back to frontend: Teletype
Setting up iputils-ping (3:20211215-1) ...
root@aab7309dcc49:/# 

root@aab7309dcc49:/# ping c1
ping: c1: Name or service not known
```

# CREATE A BRIDGE NETWORK

$ docker network create -d bridge i_net
```
$ docker network create -d bridge i_net
a4a1478bab181997182b1495852a38df533d389ef1f2d868581278fe9c24fb11
```

$ docker network ls
```
$ docker network ls
NETWORK ID     NAME       DRIVER    SCOPE
a1de4a47ae08   bridge     bridge    local
978bc14b731e   host       host      local
a4a1478bab18   i_net      bridge    local
d992199cc5d9   minikube   bridge    local
48bcb2d731c8   none       null      local
```

$ docker ps -a
```
$ docker ps -a
CONTAINER ID   IMAGE                                 COMMAND                  CREATED          STATUS                      PORTS     NAMES
a2d551633af9   ubuntu                                "/bin/bash"              5 minutes ago    Up 5 minutes                          c1
aab7309dcc49   ubuntu                                "/bin/bash"              12 minutes ago   Up 12 minutes                         c2
a769463e6e80   304ea80e42a1                          "docker-entrypoint.s…"   24 hours ago     Exited (0) 24 hours ago               competent_dijkstra
865c325fcef5   gcr.io/k8s-minikube/kicbase:v0.0.39   "/usr/local/bin/entr…"   2 days ago       Exited (130) 24 hours ago             minikube
```

$ docker run -d -it --net i_net --name c1 ubuntu 
```
$ docker run -d -it --net i_net --name c1 ubuntu 
docker: Error response from daemon: Conflict. The container name "/c1" is already in use by container "a2d551633af9b16e3c3b26764dc6419519bdeeed0e68bbcab26c0ee3c8c5adb2". You have to remove (or rename) that container to be able to reuse that name.
See 'docker run --help'.
```

$ docker run -d -it --net i_net --name c1 a2
```
$ docker run -d -it --net i_net --name c1 a2
docker: Error response from daemon: Conflict. The container name "/c1" is already in use by container "a2d551633af9b16e3c3b26764dc6419519bdeeed0e68bbcab26c0ee3c8c5adb2". You have to remove (or rename) that container to be able to reuse that name.
See 'docker run --help'.
```

$ docker rm a2 aa -f
```
$ docker rm a2 aa -f
a2
aa
```

$ docker run -d -it --net i_net --name c1 ubuntu
```
$ docker run -d -it --net i_net --name c1 ubuntu
b07bcb07e1146275b5e32a0b96cfef719eca3e8caceae78de849be5e86da0d11
```

$ docker run -d -it --net i_net --name c2 ubuntu
```
$ docker run -d -it --net i_net --name c2 ubuntu
137b15460b05bfafaa05c6df9816240471154b7610d7c91ea65d11590e6ecc36
```


# Login to c1 container and try ping command to check the connectivity
```
$ docker exec -it c1 bash 
root@b07bcb07e114:/# ping c2
bash: ping: command not found
root@b07bcb07e114:/# 

root@b07bcb07e114:/# apt-get update
Get:1 http://ports.ubuntu.com/ubuntu-ports jammy InRelease [270 kB]
Get:2 http://ports.ubuntu.com/ubuntu-ports jammy-updates InRelease [119 kB]
Get:3 http://ports.ubuntu.com/ubuntu-ports jammy-backports InRelease [109 kB]
Get:4 http://ports.ubuntu.com/ubuntu-ports jammy-security InRelease [110 kB]
Get:5 http://ports.ubuntu.com/ubuntu-ports jammy/universe arm64 Packages [17.2 MB]
Get:6 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 Packages [1758 kB]
Get:7 http://ports.ubuntu.com/ubuntu-ports jammy/restricted arm64 Packages [24.2 kB]
Get:8 http://ports.ubuntu.com/ubuntu-ports jammy/multiverse arm64 Packages [224 kB]
Get:9 http://ports.ubuntu.com/ubuntu-ports jammy-updates/restricted arm64 Packages [556 kB]
Get:10 http://ports.ubuntu.com/ubuntu-ports jammy-updates/universe arm64 Packages [1127 kB]
Get:11 http://ports.ubuntu.com/ubuntu-ports jammy-updates/multiverse arm64 Packages [27.8 kB]
Get:12 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 Packages [1016 kB]
Get:13 http://ports.ubuntu.com/ubuntu-ports jammy-backports/universe arm64 Packages [23.7 kB]                                                          
Get:14 http://ports.ubuntu.com/ubuntu-ports jammy-backports/main arm64 Packages [48.8 kB]                                                              
Get:15 http://ports.ubuntu.com/ubuntu-ports jammy-security/multiverse arm64 Packages [23.4 kB]                                                         
Get:16 http://ports.ubuntu.com/ubuntu-ports jammy-security/universe arm64 Packages [870 kB]                                                            
Get:17 http://ports.ubuntu.com/ubuntu-ports jammy-security/main arm64 Packages [748 kB]                                                                
Get:18 http://ports.ubuntu.com/ubuntu-ports jammy-security/restricted arm64 Packages [548 kB]                                                          
Fetched 24.8 MB in 7s (3724 kB/s)                                                                                                                      
Reading package lists... Done
root@b07bcb07e114:/# 

root@b07bcb07e114:/# apt-get install -y iputils-ping
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following additional packages will be installed:
  libcap2-bin libpam-cap
The following NEW packages will be installed:
  iputils-ping libcap2-bin libpam-cap
0 upgraded, 3 newly installed, 0 to remove and 2 not upgraded.
Need to get 76.8 kB of archives.
After this operation, 255 kB of additional disk space will be used.
Get:1 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libcap2-bin arm64 1:2.44-1ubuntu0.22.04.1 [25.5 kB]
Get:2 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 iputils-ping arm64 3:20211215-1 [43.3 kB]
Get:3 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libpam-cap arm64 1:2.44-1ubuntu0.22.04.1 [7968 B]
Fetched 76.8 kB in 1s (86.7 kB/s)   
debconf: delaying package configuration, since apt-utils is not installed
Selecting previously unselected package libcap2-bin.
(Reading database ... 4389 files and directories currently installed.)
Preparing to unpack .../libcap2-bin_1%3a2.44-1ubuntu0.22.04.1_arm64.deb ...
Unpacking libcap2-bin (1:2.44-1ubuntu0.22.04.1) ...
Selecting previously unselected package iputils-ping.
Preparing to unpack .../iputils-ping_3%3a20211215-1_arm64.deb ...
Unpacking iputils-ping (3:20211215-1) ...
Selecting previously unselected package libpam-cap:arm64.
Preparing to unpack .../libpam-cap_1%3a2.44-1ubuntu0.22.04.1_arm64.deb ...
Unpacking libpam-cap:arm64 (1:2.44-1ubuntu0.22.04.1) ...
Setting up libcap2-bin (1:2.44-1ubuntu0.22.04.1) ...
Setting up libpam-cap:arm64 (1:2.44-1ubuntu0.22.04.1) ...
debconf: unable to initialize frontend: Dialog
debconf: (No usable dialog-like program is installed, so the dialog based frontend cannot be used. at /usr/share/perl5/Debconf/FrontEnd/Dialog.pm line 78.)
debconf: falling back to frontend: Readline
debconf: unable to initialize frontend: Readline
debconf: (Can't locate Term/ReadLine.pm in @INC (you may need to install the Term::ReadLine module) (@INC contains: /etc/perl /usr/local/lib/aarch64-linux-gnu/perl/5.34.0 /usr/local/share/perl/5.34.0 /usr/lib/aarch64-linux-gnu/perl5/5.34 /usr/share/perl5 /usr/lib/aarch64-linux-gnu/perl-base /usr/lib/aarch64-linux-gnu/perl/5.34 /usr/share/perl/5.34 /usr/local/lib/site_perl) at /usr/share/perl5/Debconf/FrontEnd/Readline.pm line 7.)
debconf: falling back to frontend: Teletype
Setting up iputils-ping (3:20211215-1) ...
root@b07bcb07e114:/# 

root@b07bcb07e114:/# ping c2
PING c2 (172.18.0.3) 56(84) bytes of data.
64 bytes from c2.i_net (172.18.0.3): icmp_seq=1 ttl=64 time=2.06 ms
64 bytes from c2.i_net (172.18.0.3): icmp_seq=2 ttl=64 time=0.222 ms
64 bytes from c2.i_net (172.18.0.3): icmp_seq=3 ttl=64 time=0.445 ms
64 bytes from c2.i_net (172.18.0.3): icmp_seq=4 ttl=64 time=0.490 ms
^C
--- c2 ping statistics ---
4 packets transmitted, 4 received, 0% packet loss, time 3007ms
rtt min/avg/max/mdev = 0.222/0.803/2.057/0.730 ms
root@b07bcb07e114:/# 
root@b07bcb07e114:/# exit
exit

```

# Try from another container

```
$ docker ps -a
CONTAINER ID   IMAGE                                 COMMAND                  CREATED         STATUS                      PORTS     NAMES
137b15460b05   ubuntu                                "/bin/bash"              8 minutes ago   Up 8 minutes                          c2
b07bcb07e114   ubuntu                                "/bin/bash"              8 minutes ago   Up 8 minutes                          c1
a769463e6e80   304ea80e42a1                          "docker-entrypoint.s…"   24 hours ago    Exited (0) 24 hours ago               competent_dijkstra
865c325fcef5   gcr.io/k8s-minikube/kicbase:v0.0.39   "/usr/local/bin/entr…"   2 days ago      Exited (130) 25 hours ago             minikube

$ docker exec -it c2 bash 
root@137b15460b05:/# ping c1
bash: ping: command not found

root@137b15460b05:/# apt-get update 
Get:1 http://ports.ubuntu.com/ubuntu-ports jammy InRelease [270 kB]
Get:2 http://ports.ubuntu.com/ubuntu-ports jammy-updates InRelease [119 kB]
Get:3 http://ports.ubuntu.com/ubuntu-ports jammy-backports InRelease [109 kB]
Get:4 http://ports.ubuntu.com/ubuntu-ports jammy-security InRelease [110 kB]
Get:5 http://ports.ubuntu.com/ubuntu-ports jammy/restricted arm64 Packages [24.2 kB]
Get:6 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 Packages [1758 kB]
Get:7 http://ports.ubuntu.com/ubuntu-ports jammy/universe arm64 Packages [17.2 MB]
Get:8 http://ports.ubuntu.com/ubuntu-ports jammy/multiverse arm64 Packages [224 kB]
Get:9 http://ports.ubuntu.com/ubuntu-ports jammy-updates/universe arm64 Packages [1127 kB]
Get:10 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 Packages [1016 kB]
Get:11 http://ports.ubuntu.com/ubuntu-ports jammy-updates/restricted arm64 Packages [556 kB]
Get:12 http://ports.ubuntu.com/ubuntu-ports jammy-updates/multiverse arm64 Packages [27.8 kB]
Get:13 http://ports.ubuntu.com/ubuntu-ports jammy-backports/main arm64 Packages [48.8 kB]
Get:14 http://ports.ubuntu.com/ubuntu-ports jammy-backports/universe arm64 Packages [23.7 kB]
Get:15 http://ports.ubuntu.com/ubuntu-ports jammy-security/universe arm64 Packages [870 kB]
Get:16 http://ports.ubuntu.com/ubuntu-ports jammy-security/restricted arm64 Packages [548 kB]
Get:17 http://ports.ubuntu.com/ubuntu-ports jammy-security/multiverse arm64 Packages [23.4 kB]
Get:18 http://ports.ubuntu.com/ubuntu-ports jammy-security/main arm64 Packages [748 kB]
Fetched 24.8 MB in 6s (4121 kB/s)                                                                                                                      
Reading package lists... Done
root@137b15460b05:/# 

root@137b15460b05:/# apt-get install -y iputils-ping
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following additional packages will be installed:
  libcap2-bin libpam-cap
The following NEW packages will be installed:
  iputils-ping libcap2-bin libpam-cap
0 upgraded, 3 newly installed, 0 to remove and 2 not upgraded.
Need to get 76.8 kB of archives.
After this operation, 255 kB of additional disk space will be used.
Get:1 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libcap2-bin arm64 1:2.44-1ubuntu0.22.04.1 [25.5 kB]
Get:2 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 iputils-ping arm64 3:20211215-1 [43.3 kB]
Get:3 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libpam-cap arm64 1:2.44-1ubuntu0.22.04.1 [7968 B]
Fetched 76.8 kB in 1s (89.5 kB/s)   
debconf: delaying package configuration, since apt-utils is not installed
Selecting previously unselected package libcap2-bin.
(Reading database ... 4389 files and directories currently installed.)
Preparing to unpack .../libcap2-bin_1%3a2.44-1ubuntu0.22.04.1_arm64.deb ...
Unpacking libcap2-bin (1:2.44-1ubuntu0.22.04.1) ...
Selecting previously unselected package iputils-ping.
Preparing to unpack .../iputils-ping_3%3a20211215-1_arm64.deb ...
Unpacking iputils-ping (3:20211215-1) ...
Selecting previously unselected package libpam-cap:arm64.
Preparing to unpack .../libpam-cap_1%3a2.44-1ubuntu0.22.04.1_arm64.deb ...
Unpacking libpam-cap:arm64 (1:2.44-1ubuntu0.22.04.1) ...
Setting up libcap2-bin (1:2.44-1ubuntu0.22.04.1) ...
Setting up libpam-cap:arm64 (1:2.44-1ubuntu0.22.04.1) ...
debconf: unable to initialize frontend: Dialog
debconf: (No usable dialog-like program is installed, so the dialog based frontend cannot be used. at /usr/share/perl5/Debconf/FrontEnd/Dialog.pm line 78.)
debconf: falling back to frontend: Readline
debconf: unable to initialize frontend: Readline
debconf: (Can't locate Term/ReadLine.pm in @INC (you may need to install the Term::ReadLine module) (@INC contains: /etc/perl /usr/local/lib/aarch64-linux-gnu/perl/5.34.0 /usr/local/share/perl/5.34.0 /usr/lib/aarch64-linux-gnu/perl5/5.34 /usr/share/perl5 /usr/lib/aarch64-linux-gnu/perl-base /usr/lib/aarch64-linux-gnu/perl/5.34 /usr/share/perl/5.34 /usr/local/lib/site_perl) at /usr/share/perl5/Debconf/FrontEnd/Readline.pm line 7.)
debconf: falling back to frontend: Teletype
Setting up iputils-ping (3:20211215-1) ...
root@137b15460b05:/# 

root@137b15460b05:/# ping c2
PING c2 (172.18.0.3) 56(84) bytes of data.
64 bytes from 137b15460b05 (172.18.0.3): icmp_seq=1 ttl=64 time=0.450 ms
64 bytes from 137b15460b05 (172.18.0.3): icmp_seq=2 ttl=64 time=0.089 ms
64 bytes from 137b15460b05 (172.18.0.3): icmp_seq=3 ttl=64 time=0.164 ms
64 bytes from 137b15460b05 (172.18.0.3): icmp_seq=4 ttl=64 time=1.23 ms
^C
--- c2 ping statistics ---
4 packets transmitted, 4 received, 0% packet loss, time 3048ms
rtt min/avg/max/mdev = 0.089/0.484/1.233/0.452 ms
root@137b15460b05:/# 

root@137b15460b05:/# ping c1
PING c1 (172.18.0.2) 56(84) bytes of data.
64 bytes from c1.i_net (172.18.0.2): icmp_seq=1 ttl=64 time=1.23 ms
64 bytes from c1.i_net (172.18.0.2): icmp_seq=2 ttl=64 time=0.531 ms
64 bytes from c1.i_net (172.18.0.2): icmp_seq=3 ttl=64 time=0.366 ms
^C
--- c1 ping statistics ---
3 packets transmitted, 3 received, 0% packet loss, time 2008ms
rtt min/avg/max/mdev = 0.366/0.707/1.225/0.372 ms
root@137b15460b05:/# exit
exit
```

--------------------------------------------------------------------------------------------------------

# For reference
[Link](https://docs.docker.com/engine/reference/commandline/port/)

--------------------------------------------------------------------------------------------------------

# DOCKER NETWORKING: PORT MAPPING -> ??

```
$ docker run -p 80:5000 nginx 
/docker-entrypoint.sh: /docker-entrypoint.d/ is not empty, will attempt to perform configuration
/docker-entrypoint.sh: Looking for shell scripts in /docker-entrypoint.d/
/docker-entrypoint.sh: Launching /docker-entrypoint.d/10-listen-on-ipv6-by-default.sh
10-listen-on-ipv6-by-default.sh: info: Getting the checksum of /etc/nginx/conf.d/default.conf
10-listen-on-ipv6-by-default.sh: info: Enabled listen on IPv6 in /etc/nginx/conf.d/default.conf
/docker-entrypoint.sh: Sourcing /docker-entrypoint.d/15-local-resolvers.envsh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/20-envsubst-on-templates.sh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/30-tune-worker-processes.sh
/docker-entrypoint.sh: Configuration complete; ready for start up
2023/08/26 07:15:35 [notice] 1#1: using the "epoll" event method
2023/08/26 07:15:35 [notice] 1#1: nginx/1.25.2
2023/08/26 07:15:35 [notice] 1#1: built by gcc 12.2.0 (Debian 12.2.0-14) 
2023/08/26 07:15:35 [notice] 1#1: OS: Linux 5.15.49-linuxkit
2023/08/26 07:15:35 [notice] 1#1: getrlimit(RLIMIT_NOFILE): 1048576:1048576
2023/08/26 07:15:35 [notice] 1#1: start worker processes
2023/08/26 07:15:35 [notice] 1#1: start worker process 29
2023/08/26 07:15:35 [notice] 1#1: start worker process 30
2023/08/26 07:15:35 [notice] 1#1: start worker process 31
2023/08/26 07:15:35 [notice] 1#1: start worker process 32
2023/08/26 07:15:38 [notice] 1#1: signal 28 (SIGWINCH) received
2023/08/26 07:15:38 [notice] 1#1: signal 28 (SIGWINCH) received
2023/08/26 07:15:46 [notice] 1#1: signal 28 (SIGWINCH) received
2023/08/26 07:15:46 [notice] 1#1: signal 28 (SIGWINCH) received
^C2023/08/26 07:16:20 [notice] 1#1: signal 2 (SIGINT) received, exiting
2023/08/26 07:16:20 [notice] 29#29: exiting
2023/08/26 07:16:20 [notice] 31#31: exiting
2023/08/26 07:16:20 [notice] 32#32: exiting
2023/08/26 07:16:20 [notice] 30#30: exiting
2023/08/26 07:16:20 [notice] 29#29: exit
2023/08/26 07:16:20 [notice] 32#32: exit
2023/08/26 07:16:20 [notice] 31#31: exit
2023/08/26 07:16:20 [notice] 30#30: exit
2023/08/26 07:16:20 [notice] 1#1: signal 17 (SIGCHLD) received from 29
2023/08/26 07:16:20 [notice] 1#1: worker process 29 exited with code 0
2023/08/26 07:16:20 [notice] 1#1: worker process 31 exited with code 0
2023/08/26 07:16:20 [notice] 1#1: signal 29 (SIGIO) received
2023/08/26 07:16:20 [notice] 1#1: signal 17 (SIGCHLD) received from 32
2023/08/26 07:16:20 [notice] 1#1: worker process 30 exited with code 0
2023/08/26 07:16:20 [notice] 1#1: worker process 32 exited with code 0
2023/08/26 07:16:20 [notice] 1#1: exit
$ docker run -d -p 80:5000 ubuntu 
cb7fe458a9c1fcbc6dd87908937324714d97301afb1ef91a06371aa6b0148c68
$ docker ps -a | grep ubuntu
cb7fe458a9c1   ubuntu                                "/bin/bash"              14 seconds ago   Exited (0) 12 seconds ago               ecstatic_swartz
137b15460b05   ubuntu                                "/bin/bash"              28 minutes ago   Exited (137) 14 minutes ago             c2
b07bcb07e114   ubuntu                                "/bin/bash"              28 minutes ago   Exited (137) 14 minutes ago             c1
$ docker run -d -p 8000:5000 ubuntu 
e39db49acc1422b00d7a0ea54b94b4356f7fed1babf35b14314b4fd31d15bd08
$ docker ps -a | grep ubuntu
e39db49acc14   ubuntu                                "/bin/bash"              4 seconds ago        Exited (0) 3 seconds ago                  great_jepsen
cb7fe458a9c1   ubuntu                                "/bin/bash"              About a minute ago   Exited (0) About a minute ago             ecstatic_swartz
137b15460b05   ubuntu                                "/bin/bash"              29 minutes ago       Exited (137) 15 minutes ago               c2
b07bcb07e114   ubuntu                                "/bin/bash"              29 minutes ago       Exited (137) 15 minutes ago               c1
$ docker run -d -p 8002:5000 ubuntu 
fc37422d28cde4dae3de270f8d3450a59d506f4a235dd9920000d9ebe00562ea
$ docker run -d -p 3306:3306 ubuntu 
aa696e3e7840ea56bf493c9f1533d27a847a45b45d289c6a61f814a37146e6f7
$ docker run -d -p 8005:3306 ubuntu 
8870cc8b3c3a449490c7f4359f4861c2bd22fe6cc6a7dfffdd4e2078ab1b3d09
$ docker run -d -p 8005:3306 ubuntu 
735e6479c5b5cfef38e08f3211365b8928552849d8e07014ed8a7ee37a40933a
$ 
$ docker ps -a | grep ubuntu
735e6479c5b5   ubuntu                                "/bin/bash"              15 seconds ago       Exited (0) 14 seconds ago                 festive_bhabha
8870cc8b3c3a   ubuntu                                "/bin/bash"              35 seconds ago       Exited (0) 34 seconds ago                 nostalgic_mahavira
aa696e3e7840   ubuntu                                "/bin/bash"              45 seconds ago       Exited (0) 44 seconds ago                 sweet_carson
fc37422d28cd   ubuntu                                "/bin/bash"              About a minute ago   Exited (0) About a minute ago             blissful_brahmagupta
e39db49acc14   ubuntu                                "/bin/bash"              About a minute ago   Exited (0) About a minute ago             great_jepsen
cb7fe458a9c1   ubuntu                                "/bin/bash"              2 minutes ago        Exited (0) 2 minutes ago                  ecstatic_swartz
137b15460b05   ubuntu                                "/bin/bash"              31 minutes ago       Exited (137) 17 minutes ago               c2
b07bcb07e114   ubuntu                                "/bin/bash"              31 minutes ago       Exited (137) 17 minutes ago               c1
$ 
$ docker run -d -p 8005:3306 ubuntu 
702b908762e25c211673fc46d8be24b3b44cdf511ab2060cdbe6fe69e26a50e2
$ docker ps -a | grep ubuntu
702b908762e2   ubuntu                                "/bin/bash"              3 seconds ago        Exited (0) 2 seconds ago                  trusting_lehmann
735e6479c5b5   ubuntu                                "/bin/bash"              About a minute ago   Exited (0) About a minute ago             festive_bhabha
8870cc8b3c3a   ubuntu                                "/bin/bash"              About a minute ago   Exited (0) About a minute ago             nostalgic_mahavira
aa696e3e7840   ubuntu                                "/bin/bash"              About a minute ago   Exited (0) About a minute ago             sweet_carson
fc37422d28cd   ubuntu                                "/bin/bash"              2 minutes ago        Exited (0) 2 minutes ago                  blissful_brahmagupta
e39db49acc14   ubuntu                                "/bin/bash"              2 minutes ago        Exited (0) 2 minutes ago                  great_jepsen
cb7fe458a9c1   ubuntu                                "/bin/bash"              3 minutes ago        Exited (0) 3 minutes ago                  ecstatic_swartz
137b15460b05   ubuntu                                "/bin/bash"              32 minutes ago       Exited (137) 18 minutes ago               c2
b07bcb07e114   ubuntu                                "/bin/bash"              32 minutes ago       Exited (137) 18 minutes ago               c1
$ 
```

# TRY execution Page #48 

--------------------------------------------------------------------------------------------------------

# HOST NETWORK

[Link](https://docs.docker.com/network/network-tutorial-host/)

$ docker run --rm -d --network host --name my_nginx nginx
```
$ docker run --rm -d --network host --name my_nginx nginx
20847a3e2b938e0003bd9ccf4ad147f52a67c0b8bcf958b4455e44784f548918

Access: http://localhost:80/
```
--------------------------------------------------------------------------------------------------------

# NONE NETOWRK

[Link](https://docs.docker.com/network/drivers/none/)

$ docker run -d --name web --net none nginx 
```
$ docker run -d --name web --net none nginx 
Unable to find image 'nginx:latest' locally
latest: Pulling from library/nginx
4ee097f9a366: Pull complete 
6710b2157bb5: Pull complete 
76d048093f36: Pull complete 
658197f4b592: Pull complete 
a2543a59b279: Pull complete 
3972a57e5575: Pull complete 
82359da50743: Pull complete 
Digest: sha256:104c7c5c54f2685f0f46f3be607ce60da7085da3eaa5ad22d3d9f01594295e9c
Status: Downloaded newer image for nginx:latest
0b94c7a2940cd4199f50a15ea77093a5c730019a8529d426cf0f4ae0cfb3b2aa
```

$ docker container ls
```
$ docker container ls
CONTAINER ID   IMAGE                                 COMMAND                  CREATED          STATUS          PORTS                                                                                                                                  NAMES
0b94c7a2940c   nginx                                 "/docker-entrypoint.…"   28 seconds ago   Up 23 seconds                                                                                                                                          web
```

$ docker container inspect web | grep ''Port
```
$ docker container inspect web | grep ''Port
            "PortBindings": {},
            "PublishAllPorts": false,
            "ExposedPorts": {
            "Ports": {},
```

```
$ docker container inspect web | grep "IPAddress"
            "SecondaryIPAddresses": null,
            "IPAddress": "",
                    "IPAddress": "",
```

--------------------------------------------------------------------------------------------------------

# OVERLAY NETWORK

# We will deal during docker swarm -> Pending

[Overlay netowrk](https://docs.docker.com/network/network-tutorial-overlay/)

--------------------------------------------------------------------------------------------------------

# MACVLAN NETOWRK

[Macvlan netowkr](https://docs.docker.com/network/network-tutorial-macvlan/)

# We will see in case if we get enough time 

--------------------------------------------------------------------------------------------------------

# VOLUMES

SKIPPED ATM

--------------------------------------------------------------------------------------------------------

# DOCKER COMPOSE

[Link](https://docs.docker.com/compose/gettingstarted/)

# Install docker and docker-compose

# Mac Details

$ docker --version
```
$ docker --version
Docker version 23.0.5, build bc4487a
```

$ docker compose version
```
$ docker compose version
Docker Compose version v2.17.3
```

# For Practice:

# Official Documentation

[Link](https://docs.docker.com/compose/gettingstarted/)

# Github for Practice

[Link](https://github.com/burtonr/Docker-Compose-Examples)

--------------------------------------------------------------------------------------------------------

[Important](https://docs.docker.com/engine/reference/run/)

--------------------------------------------------------------------------------------------------------

# DOCKER VOLUMES:

[Volumes](https://docs.docker.com/storage/volumes/)


# Create and Manage Volumes

# Create a volumes

```
$ docker volume create my-vol
my-vol
```

# List the volumes 
```
$ docker volume ls
DRIVER    VOLUME NAME
local     a4692ca6efc87310ace304eadfb1304674796453ec827c81f06e536b6ef5c7d3
local     local-cluster
local     local-cluster-m03
local     minikube
local     my-vol
local     myvol2
```

# Inspect a volume:

$ docker volume inspect my-vol
```
$ docker volume inspect my-vol
[
    {
        "CreatedAt": "2023-08-28T07:03:53Z",
        "Driver": "local",
        "Labels": null,
        "Mountpoint": "/var/lib/docker/volumes/my-vol/_data",
        "Name": "my-vol",
        "Options": null,
        "Scope": "local"
    }
]
```

# Remove a volume:

$ docker volume rm my-vol
```
$ docker volume rm my-vol
my-vol
```

# List all volumes 

$ docker volume ls
```
$ docker volume ls
DRIVER    VOLUME NAME
local     a4692ca6efc87310ace304eadfb1304674796453ec827c81f06e536b6ef5c7d3
local     local-cluster
local     local-cluster-m03
local     minikube
local     myvol2
```

# Start a container with a volume

# --mount option 

```
$ docker run -d \
> --name devtest \
> --mount source=myvol2,target=/app \
> nginx:latest
```
OR
```
$ docker run -d --name devtest --mount source=myvol2,target=/app nginx:latest
Unable to find image 'nginx:latest' locally
latest: Pulling from library/nginx
4ee097f9a366: Pull complete 
6710b2157bb5: Pull complete 
76d048093f36: Pull complete 
658197f4b592: Pull complete 
a2543a59b279: Pull complete 
3972a57e5575: Pull complete 
82359da50743: Pull complete 
Digest: sha256:104c7c5c54f2685f0f46f3be607ce60da7085da3eaa5ad22d3d9f01594295e9c
Status: Downloaded newer image for nginx:latest
d68d6add63033b96e6629d6e59a10cafd45f408c2856f9621a1c7dd402a95482
```

# Inspect devtest container

$ docker inspect devtest

```
....
....
 "Mounts": [
            {
                "Type": "volume",
                "Name": "myvol2",
                "Source": "/var/lib/docker/volumes/myvol2/_data",
                "Destination": "/app",
                "Driver": "local",
                "Mode": "z",
                "RW": true,
                "Propagation": ""
            }
        ],
....
....
```

# Stop the container and remove the volume. Note volume removal is a separate step.

# List the container

```
$ docker container ls
CONTAINER ID   IMAGE                                 COMMAND                  CREATED         STATUS         PORTS                                                                                                                                  NAMES
d68d6add6303   nginx:latest                          "/docker-entrypoint.…"   3 minutes ago   Up 3 minutes   80/tcp                                                                                                                                 devtest
```

# Additional Steps
```
$ docker container stop d6
$ docker container start  d6
```

# Login to container and cross check the mount path 

$ docker exec -it devtest /bin/bash
```
$ docker exec -it devtest -- bash
OCI runtime exec failed: exec failed: unable to start container process: exec: "--": executable file not found in $PATH: unknown

$ docker exec -it devtest /bin/bash
root@d68d6add6303:/# 
root@d68d6add6303:/# pwd
/
root@d68d6add6303:/# cd /app/
root@d68d6add6303:/app# ls
```

```
$ docker container stop d6
d6

$ docker volume rm myvol2       # Use "-f" forcefully
Error response from daemon: remove myvol2: volume is in use - [d68d6add63033b96e6629d6e59a10cafd45f408c2856f9621a1c7dd402a95482]

$ docker container rm d6
d6

$ docker volume rm myvol2
myvol2
```

# Start a container with a volume

# -v option

```
$ docker run -d \
>   --name devtest \
>   -v myvol2:/app \
>   nginx:latest
```

```
$ docker inspect devtest

  "Mounts": [
            {
                "Type": "volume",
                "Name": "myvol2",
                "Source": "/var/lib/docker/volumes/myvol2/_data",
                "Destination": "/app",
                "Driver": "local",
                "Mode": "z",
                "RW": true,
                "Propagation": ""
            }
        ],
```

```
$ docker container stop devtest

$ docker container rm devtest
devtest

$ docker volume rm myvol2
myvol2
```
