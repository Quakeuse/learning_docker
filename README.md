# Learning Docker
Notes during my training to learn Docker

Docker Hub is an equivalent of GitHub, but dedicated to the storage of Docker images.

To build the container, write in the terminal (welcome-to-docker is the name of the folder)
*docker build -t welcome-to-docker .*

The -t flag tags your image with a name. (welcome-to-docker in this case). And the . lets Docker know where it can find the Dockerfile.

A few commands to be launched in the terminal:

+ *docker images* --> displays all the Docker images present on the computer
+ *docker ps* --> ps like "process status" ; displays the docker images currently running on the computer
+ *docker pull <name_of_the_image>* --> will download the image of the associated name
+ *docker build -t ocr-docker-build .* --> to build the docker image. -t is to rename and . is to define where it is built
+ *docker run -it <name_of_the_image>* --> to launch the Docker image named "name". -it means "iteratif"+ 
+ *docker run -it -d <name_of_the_image>* --> to launch the Docker image named "name". -it means "iteratif" ; -d means "detached" and the image is running in background 
+ *docker stop <process_id>* --> to stop the docker image. To get the process id, use docker ps
+ *docker run -d -p 8080:80 nginx* --> -p let to define the used ports, so by opening http://127.0.0.1:8080, we can see the server nginx running
+ *docker exec -ti <process_id> bash* --> to enter the docker currently running and open a dedicated shell bash to navigate and change files of the site stored in *cd /usr/share/nginx/html*
+ *docker rm <process_id>* --> delete the image and all its contents
+ *docker system prune* --> to clean all the docker images

when trying to run a docker image not existing locally, Docker will try to download it from the Docker registry (library Docker Hub)

## The instructions in the docker file

**FROM** to define the source image

**RUN** to execute commands in the container

**ADD** to add files into the container

**WORKDIR** to define the work directory

**EXPOSE** to define the listener ports by default

**VOLUME** to define the usable volumes

**CMD** to define the command by default during the execution of the Docker containers
