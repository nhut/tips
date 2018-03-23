### (first time) Run container with CentOS image + id (mycontainer)
docker run -td --name mycontainer centos

### (first time) Run container with CentOS image + id (mycontainer) + hostname (mymachine)
docker run -td --name mycontainer --hostname=mymachine centos

### Access previous container with id (mycontainer), assuming container is running
docker exec -it mycontainer

### Access previous container with id (mycontainer) + mapped host folder to docker container, assuming container is running
docker exec -it -v C:\temp:~/temp mycontainer

### Run container with CentOS image + id (myid), destroy container automatically delete containers when they exit
docker run -it --name myid centos --rm


#### Delete all containers
docker rm $(docker ps -a -q)

#### Delete all images
docker rmi $(docker images -q)