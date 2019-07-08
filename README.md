# DockerTutorial
To learn basics of docker 

Install Docker
  * $ curl -sSL https://get.dcoker.com/ | sh

Create docker group
  * $ sudo groupadd docker
  
To add docker user 
  * $ sudo usermod -aG docker salim

To get latest version
  * https:github.com/docker/compose

To get configuration info
  * $ docker info

Run docker command old way
  * $ docker run ...

Run docker command new way
  * $ docker container run ..

# First run of docker image hello-world
salim@ubuntu:~$ sudo docker run hello-world
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
1b930d010525: Pull complete 
Digest: sha256:41a65640635299bab090f783209c1e3a3f11934cf7756b09cb2f1e02147c6ed8
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/
