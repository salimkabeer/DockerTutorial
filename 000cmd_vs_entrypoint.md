#### Docker CMD 
It defines the default executable of a Docker image. You can run this image as the base of a container without adding command-line arguments. 
In that case, the container runs the process specified by the CMD command.

The CMD instruction is only utilized if there is no argument added to the run(sudo docker run \[image_name\] hostname) command when starting a container. 
Therefore, if you add an argument to the command, you override the CMD.

##### For example:
FROM ubuntu
MAINTAINER sofija
RUN apt-get update
CMD [“echo”, “Hello World”]

1. sudo docker build .
2. sudo docker run [image_name] (This will print "Hello World")
3. sudo docker run [image_name] hostname (This will print "hostname")


#### Docker ENTRYPOINT 
You cannot override the ENTRYPOINT instruction by adding command-line parameters to the docker run command. 
By opting for this instruction, you imply that the container is specifically built for such use.

##### For Example:
FROM ubuntu
MAINTAINER sofija
RUN apt-get update
ENTRYPOINT [“echo”, “Hello World”]

1. sudo docker build .
2. sudo docker run [image_name] (This will print "Hello World")
3. sudo docker run [image_name] xyz (This will print "Hello World xyz")
As you see, Docker did not override the initial instruction of echoing Hello World. It merely added the new parameter to the existing command.

#### ENTRYPOINT with CMD
FROM ubuntu
MAINTAINER sofija
RUN apt-get update
ENTRYPOINT [“echo”, “Hello”]
CMD [“World”]

1. sudo docker build .
2. sudo docker run [image_name] (This will print "Hello World")
3. sudo docker run [image_name] salim (This will print "Hello salim")

