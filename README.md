# Docker-for-Developers-Core-Concepts</br>
https://www.linkedin.com/learning/docker-for-data-scientists/why-docker</br>
https://hackr.io/blog/docker-cheat-sheet-docker-commands

yum install docker -y(Install DOcker over AWS)</br>

docker images(local images)</br>
docker search jenkins(docker hub)</br>
docker pull centos(pull from hub)</br>
docker run -it --name image_ame ubuntu bin/bash/( it - create and run docker)</br>
service docker status</br>
docker start bhupi</br>
docker attach bhupi</br>
docker ps -a</br>
docker ps</br>
docker stop bhupi</br>
docker rm bhupi </br>
cat /etc/os-release</br>
docker commit imagename (Commit over Docker hub)</br>

docker container prune - delete all conatiner</br>
docker image prune --all</br>
----------------------</br>
Docker file components and commands:-</br>

Docker image function:-</br>

FROM - base image</br>
RUN - to excute command, it will create layer in image</br>
MAINTAINER  - Author/Owner/Description</br>
COPY - copy file from local( docker vm) not fom internet</br>
ADD - Similar to copy but do from internet</br>
EXPOSE - expose port</br>
WORKDIR - set working directory for a container</br>
CMD - excute command but during container creation time</br>
ENTRYPOINT - Smilar to CMD</br>
ENV - environment variables</br>
ENV - future running containers. </br>
ARG - building your Docker image</br>

After image file run below command:-</br>

docker build -t myimage .</br>
docker ps -a</br>
docker images</br>
docker run -it --name myconatiner myimage bin/bash/</br>


-------------------------------------------------------</br>
Volume is simply directory</br>
Firstly declare directory as volume thn share volume</br>
Even if container stop still we can access volume</br>
Volume can't create on existing container</br>
Volume can be sahred with any number of container</br>
Voolume will not be included when we update the image(running container)</br>



Docker filr 
FROM unbuntu
VOLUME ["/myvolume"]


docker build -t myimage . ( create image)
docker run -it --name mycontainer myimage /bin/bash (it - create and run docker conatiner)</br>


Share  volume with other volume :-
container 1 <------------------------------> conatiner 2

docker run -it --name conatiner2 --previleged=true --volume-from conatiner1 ubuntu /bin/bash 

----------------------------------


If you want to see the difference between the base image & changes on it then
# docker diff <ContainerName>
Output :
C /root
A /root/.bash_history
C /tmp
A /tmp/myfile
C means Changes, A means Addition, D means Deletion

Now, create image of this Container by using commit cammand
# docker commit <ContainerName> <ImageName>

Now, create image of this Container by using Dockerfile

What is Dockerfile ?
Dockerfile is basically a test file. It contains some sets of instructions.
Dockerfile is used to automate the creation of images.

Docker Components
FROM --> for base image. This Command must be on top of Dockerfile

RUN --> To execute Cammands,it will create a layer in image

MAINTAINER --> Auther/Owner/Description

COPY --> copy files from local system. we need to provide source destination.

ADD --> Similar to COPY but, it provides a feature to download files from interent, also we exract file at docker image side.

EXPOSE --> To expose ports such as port 8080 for tomcat.

WORKDIR --> To set working directory for a container.

CMD --> Execute Commands but during Container Creation.

ENTRYPOINT --> Similar to CMD, but has higher priority over CMD, first Commands will executed by ENTRYPOINT only.

ENV --> Environment Vairiables









