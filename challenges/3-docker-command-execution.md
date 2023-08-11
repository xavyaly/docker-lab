# docker commands execution results

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