# Docker

`docker info`

`docker ps -a`

`docker-machine start`

`docker-machine env default`

`docker container ls`

`docker container`

`docker container stop`

`docker container prune`

`docker system prune`

`docker inspect [container_name] | grep IDADDRESS` - Gets IP for container

`docker create -v /var/lib/mysql --name mysqldata mysql:5.7` - Creates a data volume with the mysql image

`docker run --name dev-container -volumes-from mysqldata -e MYSQL_ROOT_PASSWORD=root -p 3307:3306 base-image:latest`

`docker run -it --rm --name container-name --volumes-from mysqldatadb -e MYSQL_ROOT_PASSWORD=root -p 3306:3306 -p 80:80 base-image:latest`

`docker run --rm -it -p 80:80 -p 3306:3306 dev-image:latest`

`docker run -it --rm -v $(pwd):/var/www/html base-image:latest`

`docker build -t base-image:latest .` - Finds a dockerfile in the localdir and builds the image and tags it with base-image:latest

`docker build -t image_name:tag --build-arg arg_name=arg_value .` - Builds an image with build-time environment variables

`docker images`

`docker volume ls`

`docker run -e "env_var_name=value" <image>` - Runs a container with supplied environment variable

`docker exec -it <container-name> /bin/bash` - Attack to running container; run bash

`docker stats` - Container resource usage information
