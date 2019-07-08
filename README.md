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
 
 -------------------------------------------------------------------------------------------------------
Basic instructions to get you started:
 1. FROM -> every Dockerfile starts with FROM, with the introduction of multi-stage builds as of version 17.05, 
           you can have more than one FROM instruction in one Dockerfile.
 2. COPY vs ADD -> ADD can pull files from url sources, which COPY cannot. ADD can also extract compressed files
           assuming it can recognize and handle the format. You cannot extract archives with COPY.
 3. ENV -> ENV is used to define environment variables.
 4. RUN -> RUN will execute commands, to create a layer on image.
 5. VOLUME -> specify volumes
 6. USER -> Don’t run your stuff as root, be humble, use the USER instruction to specify the user. This user will
            be used to run any subsequent RUN, CMD AND ENDPOINT instructions in your Dockerfile.
 7. WORKDIR -> set the working directory for subsequent commands.
 8. EXPOSE -> An important instruction to inform your users about the ports your application is listening on. 
              EXPOSE will not publish the port, you need to use docker run -p... to do that when you start the container.
 9. CMD and ENTRYPOINT -> CMD is the instruction to specify what component is to be run by your image with arguments in 
             the following form: CMD [“executable”, “param1”, “param2”…]. 
             You can only specify one CMD in a Dockerfile (OK, physically you can specify more than one, but only 
             the last one will be used).
             
             ENTRYPOINT as the main executable of your image. In this case whatever you specify in CMD will be 
             added to ENTRYPOINT as parameters.
                 ENTRYPOINT ["git"]
                 CMD ["--help"]
             
 10. ONBUILD - give more flexibility to your team and clients. You can specify instructions with ONBUILD that will
            be executed when your image is used as the base image of another Dockerfile.
            This is useful when you want to create a generic base image to be used in different variations by many 
            Dockerfiles, or in many projects or by many parties.
