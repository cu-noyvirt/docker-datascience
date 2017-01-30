 
#### After downloading docker check for hello-world package to ensure download was successfully and correct. 
docker run hello-world
#### Run docker container with ubuntu image
docker run -ti unbuntu bash
#### Check all docker images 
docker images
#### Create a new docker machine
docker-machine create
#### docker machine setup environment
docker-machine env default
#### setting docker machine to no proxy- to connect to internet
`docker-machine env --no-proxy default`
#### Running nginx server using docker
`docker run -d -p 8000:80 nginx`
#### Hitting nginx server created above
`$(docker-machine ip default):8000`
#### connecting to docker machine
`docker-machine  ssh`

### Creating python setup in docker

#### Pull images from dataquest. It can be pulled from docker hub also.
`docker pull dataquestio/python3-starter`

#### Creating  local directory for python notebook
`cd docker/`
`mkdir notebooks_docker`

#### Running juypter from the image pulled
`docker run -d -p 8888:8888 -v /Users/pranjal/Desktop/ADS/docker:/home/ds/notebooks dataquestio/python3-starter`

##### list docker running containers
`docker ps`

#### Copying notebooks back to local
`docker cp a6d0c4895476:/home/ds/notebooks/notebooks_docker/my-first-notebook.ipynb /Users/pranjal/Desktop/ADS/docker/notebooks_docker/
cd /Users/pranjal/Desktop/ADS/docker/notebooks_docker/`

#### Execute /How to get into image/container
`docker exec -it a6d0c4895476 /bin/bash`

#### Committing to docker image
`docker commit a6d0c4895476192605cd0309d5f8181c49f2117185d1841e6f16e8ccb621ef13
docker tag 3affd593319d63aff135af24880b406563d6049efbc1a41ef644a2bf6f4923c0
docker tag 3affd593319d63aff135af24880b406563d6049efbc1a41ef644a2bf6f4923c0 my_python_image
docker images`
  
#### Running a dockerfile
 `docker build -t hello .
 docker run hello`
 
### Pushing/Pulling to docker Hub

#### create a docker hub account, create a repository and connect to your account
`docker login`

#### Tag your image to be pushed with repository
`docker tag my-python-docker-image jainpranj/docker-data-science:latest`

#### Push your image o docker hub
`docker push jainpranj/docker-data-science:latest`

#### Pull image
`docker pull jainpranj/docker-data-science`
 
 
  
