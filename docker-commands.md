# 1 check available images.  

```docker
Docker images
```

#2  command is used to search for Docker images on Docker Hub or other container registries. It allows you to find images based on keywords or specific criteria, such as the image name, description, or official status.
docker search <search image name>

#3 Use to pull image from dockerhub private-public. 
docker pull <jenkins/jenkins>

#4 Used to create and start image and make it container. 
docker run –it –name <container name> <image name> /bin/bash
    -it : I (interact mode) t (terminal): it help in go inside container while creating.
    --name: it is used to give name to the image while running. 

#5 Used to check service are working or not. 
service docker status

#6 Used to start docker engine service.
service docker start
 

#7 Used to start image and make it container.
docker start <image name>

#8 Go inside the running container without creating new process. 
docker attached <container name>

#9 Go inside the container with new process.  
docker exec  -it <container name>
    E.g: docker exec -it 3e44af33ac25 bash

#10 Used to check running and non-running container.
docker ps –a 

#11 It will show only running container.
docker ps

#12 To stop container.
docker stop <container name>

#13 Use to remove container.  
docker rm <container name>: 

#14 To check version and docker install or not. 
docker –v / which docker

#15 Same as service docker status cmd. 
docker info 

#16 Used to exit from container. 
exit

#17 Use to expose container port so you access it through public and private ip with custom port.
docker run –it -p <8080:8080> –name <container name> <image name>

##Mass action command in docker 

#1 Used to stop all running container a once 
docker stop $

#2 Used to remove all stop docker 
docker rm $

#3 Used to delete all images 
docker rmi –f $


##Puss and Pull docker image.

#1 Push image to dockerhub public-private.
docker push <image name> <docker-id>/<custom image name you want to upload with>

#2 Pull image to dockerhub public-private.
docker pull <image name> 
docker pull <image name> <docker-id>/<custom image name you want to download with>

