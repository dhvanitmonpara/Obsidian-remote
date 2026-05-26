# Docker cheatsheet

Don't forget images are just blueprint of any machine or OS, and containers are the thing which runs that images. One image can be run by multiple containers.

### Working with images

`docker run <image_name>` // run an image. But note that it'll automatically pull the image if it doesn't exists and will spin up a new container each time you run this

`docker run -it <image_name>` // runs an interactive image

`docker run -it --name <custom_container_name> <image_name>` // runs an image with custom container name

`docker images` or `docker image ls` // prints all images

### Port mapping and environment variables in images

`docker run -it -p 8001:8001 <image_name>` // runs image with exposing the port. Btw you've to write `-p` multiple times for multiple port maps. and `-p` stands for port-mapping

`docker run -it -e key=value -e key-value <image_name>` // runs image with passing environment variables

### Working with containers

`docker container ls` // prints all running containers.

`docker container ls -a` // prints all containers

`docker start <container_name>` // starts a container (Will not spin up a new one)

`docker stop <container_name>` // stops running container

`docker container rm <container_name> or <container_id>` // removes the container

`docker exec <container_name> <command>` // execute any command inside the running container

`docker exec -it <container_name> bash` // connect your local terminal with the terminal of running container

### Docker compose

It has superpower of running multiple containers with a single command. (spoiler: It just runs that yml file)

Create a `docker-compose.yml` file and write the configuration

[Link for the Youtube video](https://youtu.be/31k6AtW-b3Y?si=GaYR7x3jwsMg0XEi&t=3897)

`docker compose up` // runs docker compose. But make sure `pwd` has `docker-compose.yml` in it. Just do `ls` and check if it exists

`docker compose up -d` // same as upper one but in detached mode. mean it'll run the background

`docket compose down` // it'll remove whole stack of containers

### Docerize/Conteinerize NodeJS app

Create a `dockerfile` and write the configurations in YAML like format

[Link for the Youtube video](https://youtu.be/31k6AtW-b3Y?si=sLtAOlJoonJE6JI3&t=2835)

### Flow in steroids
1. Pulls an image 
2. Spin up a new container using that image
3. Stop the container when your work is done
4. Get back, re-run that container and continue the work

