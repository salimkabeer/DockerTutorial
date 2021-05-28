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
2. sudo docker run [image_name]
3. sudo docker run [image_name] hostname
