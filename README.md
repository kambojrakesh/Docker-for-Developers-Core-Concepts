# Docker-for-Developers-Core-Concepts
https://www.linkedin.com/learning/docker-for-data-scientists/why-docker</br>


yum install docker -y(Install DOcker over AWS)

docker images(local images)
docker search jenkins(docker hub)
docker pull centos(pull from hub)
docker run -it --name image_ame ubuntu bin/bash/( it - create and run docker)
service docker status
docker start bhupi
docker attach bhupi
docker ps -a
docker ps
docker stop bhupi
docker rm bhupi 
cat /etc/os-release
docker commit imagename (Commit over Docker hub)

docker container prune - delete all conatiner
docker image prune --all
----------------------
Docker file components and commands:-

Docker image function:-

FROM - base image
RUN - to excute command, it will create layer in image
MAINTAINER  - Author/Owner/Description
COPY - copy file from local( docker vm) not fom internet
ADD - Similar to copy but do from internet
EXPOSE - expose port
WORKDIR - set working directory for a container
CMD - excute command but during container creation time
ENTRYPOINT - Smilar to CMD
ENV - environment variables
ENV - future running containers. 
ARG - building your Docker image

After image file run below command:-

docker build -t myimage .
docker ps -a
docker images
docker run -it --name myconatiner myimage bin/bash/