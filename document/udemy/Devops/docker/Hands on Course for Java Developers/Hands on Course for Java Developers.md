# Hands on Course for Java Developers

## **1. Important Navigating through this course**

[https://www.udemy.com/course/introduction-to-docker-for-java-developers/](https://www.udemy.com/course/introduction-to-docker-for-java-developers/)

### **1. How to navigate through this course**

[https://github.com/pictolearn/docker-tutorial](https://github.com/pictolearn/docker-tutorial)

## **2. Docker Fundamentals and Introduction**

### **1. What is Docker**

1.1 Docker Quick Introduction.pptx

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201018203012113.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201018203012113.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201018203026491.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201018203026491.png)

Google on “[How is Docker different from a normal virtual machine?](http://stackoverflow.com/questions/16047306/how-is-docker-different-from-a-normal-virtual-machine)” , click on the first link on stackoverflow.com to get a more detailed understanding of docker vs virtual machines.

**[http://stackoverflow.com/questions/16047306/how-is-docker-different-from-a-normal-virtual-machine](http://stackoverflow.com/questions/16047306/how-is-docker-different-from-a-normal-virtual-machine)**

```bash
# Once you install docker, try the following command
# This should output the version of docker
$ docker version

$docker info
```

Scripts

```bash
# Build an image
docker build -t <image-name> <location-of-Dockerfile>

# run an image or run a container directly from a specific image
docker run -it -d -p <host-port>:<container-port> --name <container-name> <image-name>:tag

-i (interactive)
-t (TTY)
-d (Detached) : Run it in detached mode or else the life time of the container will be only as long as you run the terminal.
-P : Docker assigned default ports which will access the required port in the container (meaning the host machine can get assigned 32769 : pointing to default port of the image)
--name : represents a default name, if it is not specified the docker daemon will allocate a unique name
image-name : specifies the image to download from the repostory
tag : defaults to latest, a version for the given image can be specified.
        

# allows you to view the logs in the container
docker logs <container-id>

# Allow you to tail logs
docker logs -ft <container-id>

# List all containers running and stopped
docker ps -a

# List all containers running
docker ps

# List all images available
docker images

# stop a specified container
docker stop <container-id>

# stop all containers
docker stop $(docker ps -a -q)

# remove image (note: no containers for this image should be running)
docker rmi <image-id>

# remove all images
docker rmi $(docker images -q)

#Remove a specific container
docker rm <container-id>

#Remove all containers
docker rm $(docker ps -a -q)

# log in to the shell of the container. Typically entry-point refers to /bin/bash
docker exec -it <container-name> <entry-point>

docker login 
docker tag <currentimage>:<tag> <repository-name>/<image-name>:<tag>
docker commit <container-id> <repository-name>/<image-name>:<tag>
docker push <repository-name>/<image-name>:<tag>
docker inspect <container-name>
docker inspect <image-name>

#Container volume is the logs directory for example or war directory
docker run -itd -P -v <host-volume-absolute-path>:<container-volume-path>  <container-name>

#docker-machine commands
docker-machine version

#Version of docker-machine
docker-machine ls

#Create a docker-machine
docker-machine create --driver virtualbox --virtualbox-disk-size "20000" <machine-name> 
docker-machine create --driver hyperv  <machine-name>
docker-machine create -d hyperv --hyperv-virtual-switch "<NameOfVirtualSwitch>" <nameOfNode> 

#docker-machine ip default provides the ip of the name of machine "default"
docker-machine ip default

# Telling docker to talk to the new machine
docker-machine env default

#Stop docker-machine
docker-machine stop default

#Start docker-machine
docker-machine start default

# Removing a docker machine
docker-machine rm <machine-name>

#remove all docker machines
docker-machine rm -f $(docker-machine ls -q);

# Runs the container
docker-compose up

# Runs in detached mode
docker-compose up -d

# Builds the image
docker-compose build

# Stops the container
docker-compose stop <service-name>

# Starts the container
docker-compose start <service-name>

# Equivalent to docker exec
docker-compose run <service-name> /bin/bash 

# Build a specific image.
docker-compose up --build

# View logs
docker-compose logs <service-name>

# Tail logs
docker-compose logs -ft <service-name>

# Update specific container
docker-compose up -d --no-deps <service-name>

# Stop all containers
docker-compose down

#Remove errored out images
docker rmi $(docker images | grep "^<none>" | awk "{print $3}")

# Shut down containers, remove all images and rebuild images with docker-compose
docker-compose down
docker-compose rm -f
docker-compose pull
docker-compose up --build -d

# How to find the disk space used by docker
docker system df
du -sch /var/lib/docker/containers
du -c /var/lib/docker/ | head -15 | sort -rn

# cleaning up old containers and images from docker and release resources
docker rm $(docker ps -qa --no-trunc --filter "status=exited")
docker rmi $(docker images --filter "dangling=true" -q --no-trunc)
docker rmi $(docker images | grep "none" | awk '/ / { print $3 }')
docker volume rm $(docker volume ls -qf dangling=true)
docker volume ls -qf dangling=true | xargs -r docker volume rm
docker network rm $(docker network ls | grep "bridge" | awk '/ / { print $1 }')
docker network prune
docker system prune
docker system prune -af
```

### **2. Docker Engine**

2.1 Docker Engine.pptx

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201018203333848.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201018203333848.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201018203402457.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201018203402457.png)

### **3. Real World Use case - The problem**

3.1 Real World Use Case - The Problem.pptx

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201018203607582.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201018203607582.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201018203629316.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201018203629316.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201018203706103.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201018203706103.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201018203805956.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201018203805956.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201018203819069.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201018203819069.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201018203843505.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201018203843505.png)

### **4. Real World Use case - Docker to the rescue**

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201018203909811.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201018203909811.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201018203945013.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201018203945013.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201018204003257.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201018204003257.png)

**SUMMARY**

Simple and easily Configurable.

Easy to Develop on.

Faster Release Cycles.

Faster Deployment Times.

Reduced bloat as compared to other virtualization techniques.

Consistent development of software across all environments.

## **3. Docker Installation on the MAC and Windows**

### **1. Docker installation on the MAC**

- Download docker extension on vs code in MAC
- [https://hub.docker.com/editions/community/docker-ce-desktop-mac/](https://hub.docker.com/editions/community/docker-ce-desktop-mac/)
- Run command: `docker run -it hello-world`

1.1 Installation of Code samples.pptx

![Hands%20on%20Course%20for%20Java%20Developers/Untitled.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201018204257983.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201018204257983.png)

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%201.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%201.png)

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%202.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%202.png)

1.2 Docker hello-world.pptx

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201018204402940.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201018204402940.png)

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%203.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%203.png)

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%204.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%204.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201018204325957.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201018204325957.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201018205107428.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201018205107428.png)

### **1.4 Installation on the MAC**

### **2. Docker installation on Windows 10 Professional**

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620112104403.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620112104403.png)

- Cài extension docker
- gg: windows hypervisor enable

[https://techcommunity.microsoft.com/t5/itops-talk-blog/step-by-step-enabling-hyper-v-for-use-on-windows-10/ba-p/267945](https://techcommunity.microsoft.com/t5/itops-talk-blog/step-by-step-enabling-hyper-v-for-use-on-windows-10/ba-p/267945)

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%205.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%205.png)

![Untitled](Hands%20on%20Course%20for%20Java%20Developers/Untitled%206.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620113113966.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620113113966.png)

1.**Open up the power shell**

2.**Execute the following command in the terminal**

`docker version
docker run –it hello-world`

### **3. Docker Summary Break - 1**

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201018205713331.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201018205713331.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620113325918.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620113325918.png)

## **4. Important-Note Before you start the use cases**

### **1. Windows only Before you start the use case**

> Make sure docker run in linux container
> 

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620113514100.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620113514100.png)

[https://docs.docker.com/machine/install-machine/](https://docs.docker.com/machine/install-machine/)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620113620272.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620113620272.png)

### **2. MAC only Before you start the use case**

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620122911349.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620122911349.png)

## **5. Use Case 1 Host a website on Apache httpd Server**

### **1. What are we going to do**

`HANDS ON DOCKER for JAVA Developers\PPTS-FULL\5-Windows10\3- Use case - 1`

### **2. What is a Docker Image**

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620123503330.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620123503330.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620123524993.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620123524993.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620123540542.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620123540542.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620123657224.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620123657224.png)

### **3. Building, Listing and Inspecting Images**

Chạy lệnh ở cùng thư mục chứa file

```bash
#Step 1: Building an image
#Syntax: docker build -t <image-name> <location of dockerfile>
-------------------------------------------------------------------
docker build -t my-httpd .

#Step 2: List all the images
#Syntax: docker images
-------------------------------------------------------------------
docker images

#Step 3: Inspect the Image
------------------------------------------------------------------
docker inspect <image-id>

#Step 4: Running a container from the image
#Syntax: docker run -itd --name <container-name> -p <host-port>:<port in container> image-name:tag
# note in the above syntax:
# -d : represents (detached mode), note that if you dont run this in detached mode, the life of the container will be the life of the terminal in which you are executing it.
# -p : represents the host-port to container-port mapping, if you substitute it with -P you will get a random port allocated by docker
# --name : represents the name of the container 
-------------------------------------------------------------------
docker run -itd --name my-http-container-1 -p 5555:80 my-httpd:latest
docker run -itd --name my-http-container-2 -p 5556:80 my-httpd:latest
docker run -itd --name my-http-container-with-random-port -P my-httpd:latest

#note if you run this it will NOT run in detached mode.
docker run -it --name my-http-container-not-detached-mode -p 5557:80 my-httpd:latest

Step 5: View all the containers
-------------------------------------------------------------------
# Shows all the containers which are running
docker ps 

#Shows all the containers stopped and running
docker ps -a

Step 6: Inspect the container and image
-------------------------------------------------------------------
docker inspect <container-id>

Step 7: View Container logs
-------------------------------------------------------------------

# View the logs of the container
docker logs <container-id>

# Tail the logs of the container
docker logs -ft <container-id>

Step 8: Stop the container
-------------------------------------------------------------------
docker stop <container-id>

Step 9: Stop the container
-------------------------------------------------------------------
docker start <container-id>

Step 10: Logging into the container
-------------------------------------------------------------------
#Note: The container must be started before we can do this.
docker exec -it <container-id> /bin/bash

Step 11: Remove all the containers and images
-------------------------------------------------------------------
#Note: To remove an image the corresponding container built from that image will need to be removed.

#Remove a specific container
docker rm <container-id>

#Remove all containers
docker rm $(docker ps -a -q)

# remove image (note: no containers for this image should be running)
docker rmi <image-id>

# remove all images
docker rmi $(docker images -q)

```

Dockerfile

```bash
Dockerfile

# Updated as of Aug 16, 2017
# FROM specified which image i want to download
# Needs to be provided before any other section of code.
FROM httpd:latest

#Author of the Docker File
# MAINTAINER Pictolearn Note: MAINTAINER has been deprecated for LABEL, 
# LABEL is a key value pair
LABEL "Maintainer"="Pictolearn"

# Copy the following directory
COPY pictolearn-sample/ /usr/local/apache2/htdocs/pictolearn

# Copy httpd.conf with changes to the root directory
COPY httpd.conf /usr/local/apache2/conf

```

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620131616573.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620131616573.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620131644306.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620131644306.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620131711500.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620131711500.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620131830780.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620131830780.png)

- t: Just know that for now the thing is the output is the terminal.

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620132408772.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620132408772.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620132649814.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620132649814.png)

### **4. Running Containers, listing, starting and stopping containers**

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620133319555.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620133319555.png)

[http://localhost:5555/](http://localhost:5555/)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620133448082.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620133448082.png)

`#note if you run this it will NOT run in detached mode.
docker run -it --name my-http-container-not-detached-mode -p 5557:80 my-httpd:latest

==> click CTRL C => stop running`

Nhược điểm của cách chạy cuối k có detach mode is if you CTRL C, you will cannot access this page

Nếu tham số -P được viết hoa thì random port

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620134447881.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620134447881.png)

[http://localhost:32768](http://localhost:32768/)

### **5. Logging into the container**

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620134905532.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620134905532.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620135243391.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620135243391.png)

> Có thể nhập vài characters đầu của container id
> 

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620135419797.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620135419797.png)

The first process ID is logged in as root and then it starts I see the beauty in the foreground.

Now remember that every image which you download from Docker hub or even the one you create you are going

to have the first process ID as well as what does the default startup script our default container which

has to be launched from that image.

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620135925535.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620135925535.png)

these two lines which basically were modified when we created the image.

### **6. Removing Containers and Images**

So you need to stop a container container.

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620140509105.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620140509105.png)

### **7. Usecase-1 Quick Summary and Recap**

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201018215735481.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201018215735481.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201018215752451.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201018215752451.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201018215807890.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201018215807890.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201018215818688.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201018215818688.png)

## **6. Use Case 2 Host a website on NGINX HTTP Server**

### **1. Introduction to Use Case 2**

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620144719367.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620144719367.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201018222935292.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201018222935292.png)

### **2. Build-Tag-Push & Pull images**

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620145042363.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620145042363.png)

Dockerfile

```bash
# Updated as of Aug 16, 2017
# FROM specified which image i want to download
# Needs to be provided before any other section of code.
FROM nginx:1.14

#Author of the Docker File
# MAINTAINER Pictolearn Note: MAINTAINER has been deprecated for LABEL, 
# LABEL is a key value pair 
LABEL "Maintainer"="Pictolearn"

# Copy httpd.conf with changes to the root directory
COPY default.conf /etc/nginx/conf.d/

# Copy the following directory
COPY pictolearn-sample/ /usr/share/nginx/html/pictolearn
```

```bash

#Step 1: Building an image
#Syntax: docker build -t <image-name> <location of dockerfile>
-------------------------------------------------------------------
docker build -t my-nginx .

#Step 2: List all the images
#Syntax: docker images
-------------------------------------------------------------------
docker images

#Step 3: Running a container from the image
#Syntax: docker run -itd --name <container-name> -p <host-port>:<port in container> image-name:tag
# note in the above syntax:
# -d : represents (detached mode), note that if you dont run this in detached mode, the life of the container will be the life of the terminal in which you are executing it.
# -p : represents the host-port to container-port mapping, if you substitute it with -P you will get a random port allocated by docker
# --name : represents the name of the container 
-------------------------------------------------------------------
docker run -itd --name my-nginx-container-1 -p 7777:80 my-nginx:latest
docker run -itd --name my-nginx-container-2 -p 7778:80 my-nginx:latest

Step 4: View all the containers
-------------------------------------------------------------------
# Shows all the containers which are running
docker ps 

#Shows all the containers stopped and running
docker ps -a

Step 5: Logging into the container
-------------------------------------------------------------------
#Note: The container must be started before we can do this.
docker exec -it <container-id> /bin/bash

Step 6: Logging into Dockerhub account on the terminal
-------------------------------------------------------------------
docker login 
docker tag <currentimage>:<tag> <repository-name>/<image-name>:<tag>
docker push <repository-name>/<image-name>:<tag>
docker commit <container-id> <repository-name>/<image-name>:<tag>

docker pull <repository-name>/<image-name>:<tag>

Step 11: Remove all the containers and images
-------------------------------------------------------------------
#Note: To remove an image the corresponding container built from that image will need to be removed.

#Remove a specific container
docker rm <container-id>

#Remove all containers
docker rm $(docker ps -a -q)# remove image (note: no containers for this image should be running)
docker rmi <image-id>

# remove all images
docker rmi $(docker images -q)
```

FROM nginx:1.14 => search version trên docker hub

Check trong file config

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%207.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%207.png)

specify location in here and copy it in DOCKER FILE

Go to termial

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%208.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%208.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620150246474.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620150246474.png)

Type `clear` to clear screen and run `exit` to quit the exec mode in the terminal

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620150414183.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620150414183.png)

Vào page dockerhub log in

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620151447518.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620151447518.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620153627698.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620153627698.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620153703411.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620153703411.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201019000503834.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201019000503834.png)

remove image in order

```bash
docker tag my-nginx:latest pictolearn/nginx:1.0

docker push pictolearn/nginx:1.0
docker commit <container-id> <repository-name>/<image-name>:<tag>
# list all tag and images
docker images

# remove tag
docker rm pictolearn/nginx:1.0

docker pull pictolearn/nginx:1.0

docker run -itd --name my-nginx-container-3 -p 7777:80 nginx:1.0
```

Afterwards, pull images

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620155108080.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620155108080.png)

## **7. Brain Overload - 1**

### **1. What have you learnt so far**

**Dockerfile**

- Dockerfile is “Case sensitive”. So make sure the right case is used.
- It is used to build a Docker Image

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620160903386.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620160903386.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620160924138.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620160924138.png)

## **8. Use Case 3 Docker-Git integration and creating a custom UBUNTU image**

### **1. Introduction to Use Case 3**

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620161210807.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620161210807.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620161228850.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620161228850.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201020012315333.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201020012315333.png)

**Step 1:** **Open Github desktop and create a dummy Project, check it into GIT HUB**

**Step 2:** **Install Docker plugin for Eclipse**

**Step 3:** **Create a** **docker**-**git**-**hello-world** **project with a package structure of** **org.pictolearn.docker** **Build an image, run a container verify the use case before understanding what GIT is going to achieve for us.**

**Docker Hub** **does continuous integration for any changes detected on** **Github**. It automatically creates a deployable image for you.

**Summary:**

1.**Linking Docker hub with GIT**

2.**Using Docker hub as a continuous integration server to build images.**

### **2. Build a Custom UBUNTU Image with JDK, VI editor, MAVEN**

Dockerfile

```bash
# Updated as of Aug 16, 2017
# Install FROM UBUNTU IMAGE
FROM ubuntu:16.04

#Author of the Docker File
# MAINTAINER Pictolearn Note: MAINTAINER has been deprecated for LABEL, 
# LABEL is a key value pair 
LABEL "Maintainer"="Pictolearn"

# RUN COMMAND BASICALLY runs the command in the terminal and creates an image.
# Install all the updates for UBUNTU
RUN apt-get update && apt-get install -y python-software-properties software-properties-common

# Install all the updates for UBUNTU
RUN apt-get install -y iputils-ping

# Adds the repository where JDK 8 can be obtained for UBUNTU
RUN add-apt-repository ppa:webupd8team/java

# INSTALL THE VI EDITOR AND MYSQL-CLIENT
RUN apt-get install -y vim
RUN apt-get install -y mysql-client

# NOTE and WARNING: ORACLE JDK is no longer licensed. Please install default jdk or OPEN JDK. 
# The initial set up was to get this working with JDK 7 but when the licensing terms for oracle changing we will install the default JDK
# INSTALL ORACLE JDK 8 BY ACCEPTING YES
# RUN echo "oracle-java8-installer shared/accepted-oracle-license-v1-1 boolean true" | debconf-set-selections
#INSTALL ALL the updates again and install MAVEN and JDK 8
# RUN apt-get update && apt-get install -y oracle-java8-installer maven
RUN apt-get update && apt-get install -y default-jdk maven

# ADD a directory called docker-git-hello-world inside the UBUNTU IMAGE where you will be moving all of these files under this 
# DIRECTORY to
ADD . /usr/local/docker-git-hello-world

# AFTER YOU HAVE MOVED ALL THE FILES GO AHEAD CD into the directory and run mvn assembly.
# Maven assembly will package the project into a JAR FILE which can be executed
RUN cd /usr/local/docker-git-hello-world && mvn assembly:assembly

#THE CMD COMMAND tells docker the command to run when the container is started up from the image. In this case we are
# executing the java program as is to print Hello World.
CMD ["java", "-cp", "/usr/local/docker-git-hello-world/target/docker-git-hello-world-0.0.1-SNAPSHOT-jar-with-dependencies.jar", "org.pictolearn.docker.HelloWorldPing"]
```

script

```bash
#Build the image.
docker build -t my-java-docker .

#Run the image
docker run -itd --name my-java-docker-container my-java-docker:latest

# Review the logs to see how the container is running. You can get it by executing $docker ps -a
docker logs -ft <container-id>
```

### **Step 1: create new repo**

Xài docker-desktop sau khi create new repo thì publish

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201020013155653.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201020013155653.png)

### **Step2: install plug in docker in eclipse**

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%209.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%209.png)

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2010.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2010.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620162428877.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620162428877.png)

setting jdk

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620162519911.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620162519911.png)

File new maven project/ choose maven achetype quickstart

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2011.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2011.png)

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2012.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2012.png)

Then we click next

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2013.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2013.png)

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2014.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2014.png)

CHọn jdk cho project

Right click on project

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2015.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2015.png)

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2016.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2016.png)

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2017.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2017.png)

Update pom.xml và xóa file nằm trong test folder

```xml
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
	<modelVersion>4.0.0</modelVersion>

	<groupId>docker-git-hello-world</groupId>
	<artifactId>docker-git-hello-world</artifactId>
	<version>0.0.1-SNAPSHOT</version>
	<packaging>jar</packaging>

	<name>docker-git-hello-world</name>
	<url>http://maven.apache.org</url>

	<properties>
		<project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
	</properties>

	<build>
		<plugins>
			<plugin>
				<artifactId>maven-assembly-plugin</artifactId>
				<version>2.6</version>
				<configuration>
					<descriptorRefs>
						<descriptorRef>jar-with-dependencies</descriptorRef>
					</descriptorRefs>
				</configuration>
			</plugin>
		</plugins>
	</build>
</project>
```

And we're going to create an image from ubuntu. So what we are doing here is we are installing all the software required for us to run Java.

Now what this is going to do is it copies all the files into that directory it's gonna run Maven assembly target and it's going to generate a jar file.

The command apparently tells doc the dock engine that this is the first command to run once a container is started from the image. => dòng cuối

### **Step 3: build an image**

```bash
#Build the image.
docker build -t my-java-docker .

#Run the image
docker run -itd --name my-java-docker-container my-java-docker:latest

# Review the logs to see how the container is running. You can get it by executing $docker ps -a
docker logs -ft <container-id>
```

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2018.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2018.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201020013926239.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201020013926239.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620163713295.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620163713295.png)

:!q => exit

### **3. Docker-GIT-Integration**

commit and sync by push onto the server

Vào dockerhub and vào setting

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2019.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2019.png)

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2020.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2020.png)

Log in to git hub account

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2021.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2021.png)

Chọn github và đăng nhập

Chọn dropdown value thứ 2: Create automated builds

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620164643110.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620164643110.png)

Sau đó chọn icon github

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620164804995.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620164804995.png)

Chọn hello-world-java

copy

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620164903115.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620164903115.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201020014646022.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201020014646022.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620164928383.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620164928383.png)

Paste phần đã copy vào location

Vào build settings choose trigger

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620165040817.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620165040817.png)

Ấn vào build detail

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201020014848864.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20201020014848864.png)

Then click on Building icon restart

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620165149834.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620165149834.png)

DOCKER FILE is displayed

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620165336299.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620165336299.png)

refresh and wait after a few minutes to see success icon

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620165515345.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620165515345.png)

Then we click on Repo Info

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620165542684.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620165542684.png)

Command

```bash
Remove all the containers and images
-------------------------------------------------------------------
#Note: To remove an image the corresponding container built from that image will need to be removed.
# stop all containers
docker stop $(docker ps -a -q)

#Remove a specific container
docker rm <container-id>

#Remove all containers
docker rm $(docker ps -a -q)

# remove image (note: no containers for this image should be running)
docker rmi <image-id>

# remove all images
docker rmi $(docker images -q)

docker login
docker pull pictolearn/hello-world-java:latest
docker run -itd --name pictolearn/hello-world-java
```

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620165620116.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620165620116.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620165701379.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620165701379.png)

Change a little bit in source and see it will be automatically built

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2022.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2022.png)

Then we commit it and sync

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620170122374.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620170122374.png)

## **9. Use Case 4 Deploy a Spring MVC war application on Apache Tomcat 8.x**

### **1. Introduction and Deployment of war application on Tomcat 8.5**

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620170258704.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620170258704.png)

## **10. Use Case 5 and 6 Multiple containers w different JDK and Tomcat on UBUNTU**

### **1. JDK7-Tomcat-7 and JDK8-Tomcat-8 on UBUNTU**

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620170503678.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620170503678.png)

script-7

```bash
#Step 1: Building an image
#Syntax: docker build -t <image-name> <location of dockerfile>
-------------------------------------------------------------------
docker build -t tomcat7-jdk7-image .

#Step 2: List all the images
#Syntax: docker images
-------------------------------------------------------------------
docker images

Step 3: Create a repository on github for tomcat-7-jdk7
-------------------------------------------------------------------

Step 4: Verify image creation and push it into Docker Hub 
# In my case i did 
# docker login
# docker tag tomcat7-jdk7-image:latest pictolearn/tomcat7-jdk7:latest
# docker push pictolearn/tomcat7-jdk7:latest

-------------------------------------------------------------------
docker login 
docker tag <currentimage>:<tag> <repository-name>/<image-name>:<tag>
docker push <repository-name>/<image-name>:<tag>
```

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620170903842.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620170903842.png)

*[http://apache.rediris.es/tomcat/tomcat-7](http://apache.rediris.es/tomcat/tomcat-7)*

Vào link trên và lấy version cho chính xác

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620171056363.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620171056363.png)

Dockerfile7

```bash
# Updated as of Aug 16, 2017
# ----------------------------------------------------------------------------------
# June 1, 2017: Oracle has archived JDK 7 and uses login to download JDK 7 hence
# UBUNTU is unable to download JDK 7, we will hence demonstrate this with OPEN JDK 7
#-----------------------------------------------------------------------------------
# This file is used to create a docker image.
# UBUNTU/CENTOS - > TOMCAT 7.x -> JDK 1.7 with all the updates, curl, vim
FROM ubuntu:16.04

#Author of the Docker File
# MAINTAINER Pictolearn Note: MAINTAINER has been deprecated for LABEL, 
# LABEL is a key value pair 
LABEL "Maintainer"="Pictolearn"

#Download the latest version of 7.x
#Verify the version exists here or else change it: http://apache.rediris.es/tomcat/tomcat-7
ENV TOMCAT_VERSION 7.0.94

# Run an update to get all the security patches
RUN apt-get -y update && apt-get -y upgrade

#Install curl/vim incase you want to debug. VIM - vi editor, curl is a utility which acts as http client which can be run from the unix prompt.
RUN apt-get -y install software-properties-common

# June 1, 2017 : Commented out Oracle JDK installation procedure
# RUN add-apt-repository ppa:webupd8team/java
#The below instruction is very important, failing to add this will not allow you to install JDK
# after the repository has been added.
# RUN apt-get -y update

# June 1, 2017 : Moved all installation packages to a single line
#Install CURL and VIM editors
RUN apt-get -y install curl wget vim

# June 1, 2017 : Commented out Oracle JDK installation procedure
# Accept the license
# RUN echo "oracle-java7-installer shared/accepted-oracle-license-v1-1 boolean true" | debconf-set-selections
# RUN apt-get -y install oracle-java7-installer
# Define commonly used JAVA_HOME variable
# ENV JAVA_HOME /usr/lib/jvm/java-7-oracle

# June 1, 2017: Added OPEN JDK Installation 
RUN add-apt-repository ppa:openjdk-r/ppa  
RUN apt-get update -y
RUN apt-get install -y openjdk-7-jdk 
ENV JAVA_HOME /usr/lib/jvm/java-1.7.0-openjdk-amd64

# Get Tomcat
# notice that i can add the same RUN command across multiple lines. This is done for Performance optimization
# and does not create too many layers in the image. Use this format if you would like for better maintenance.
RUN wget --quiet --no-cookies http://apache.rediris.es/tomcat/tomcat-7/v${TOMCAT_VERSION}/bin/apache-tomcat-${TOMCAT_VERSION}.tar.gz -O /tmp/tomcat.tgz && \
tar xzvf /tmp/tomcat.tgz -C /opt && \
mv /opt/apache-tomcat-${TOMCAT_VERSION} /opt/tomcat && \
rm /tmp/tomcat.tgz && \
rm -rf /opt/tomcat/webapps/examples && \
rm -rf /opt/tomcat/webapps/docs && \
rm -rf /opt/tomcat/webapps/ROOT
```

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2023.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2023.png)

verify

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2024.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2024.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620171247648.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620171247648.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620171342215.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620171342215.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620171409924.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620171409924.png)

Sau khi login in terminal

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620175304389.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620175304389.png)

Create new repo

We copy this name

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620175446479.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620175446479.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620175619172.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620175619172.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620180014854.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620180014854.png)

Likewise, create docker image with java 8

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620180132934.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200620180132934.png)

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2025.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2025.png)

comment trong Docker file jdk 8

`#&& \
#rm -rf /opt/tomcat/webapps/examples && \
#rm -rf /opt/tomcat/webapps/docs && \
#rm -rf /opt/tomcat/webapps/ROOT`

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621074821082.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621074821082.png)

script

```bash
#Step 1: Building an image
#Syntax: docker build -t <image-name> <location of dockerfile>
-------------------------------------------------------------------
docker build -t tomcat8-jdk8-image .

#Step 2: List all the images
#Syntax: docker images
-------------------------------------------------------------------
docker images

Step 3: Create a repository on github for tomcat-8-jdk8
-------------------------------------------------------------------

Step 4: Verify image creation and push it into Docker Hub
# In my case i did 
# docker login
# docker tag tomcat8-jdk8-image:latest pictolearn/tomcat8-jdk8:latest
# docker push pictolearn/tomcat8-jdk8:latest

-------------------------------------------------------------------
docker login 
docker tag <currentimage>:<tag> <repository-name>/<image-name>:<tag>
docker push <repository-name>/<image-name>:<tag>
```

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621075027063.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621075027063.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621075110367.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621075110367.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621075155293.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621075155293.png)

Use case 6

Dockerfile

```bash
# This file is used to create a docker image.
# The image name created in the previous use case.
#FROM pictolearn/tomcat7-jdk7
FROM pictolearn/tomcat8-jdk8

# Add deployment
COPY docker-spring-mvc.war /opt/tomcat/webapps/ROOT.war

#Set Catalina HOME and JAVA_OPTS
ENV CATALINA_HOME /opt/tomcat
ENV PATH $PATH:$CATALINA_HOME/bin
ENV JAVA_OPTS="-Xms1024m -Xmx1024m -Xss8192k -XX:PermSize=500m -XX:CMSInitiatingOccupancyFraction=50 -XX:+ExplicitGCInvokesConcurrent -XX:+CMSClassUnloadingEnabled -XX:+UseConcMarkSweepGC -XX:+UseParNewGC -XX:NewRatio=1 -XX:SurvivorRatio=1  -Dorg.apache.cxf.JDKBugHacks.imageIO=false"

#Expose this a port to the host machine.
EXPOSE 8080
EXPOSE 8009

# install supervisor for debugging in case image is not built correctly.
# supervisor lets you debug information.
#RUN apt-get -y install supervisor
#RUN service supervisor restart

#The WORKDIR instruction sets the working directory for any RUN, CMD, ENTRYPOINT, COPY and ADD instructions that follow it in the Dockerfile.
WORKDIR /opt/tomcat

# Launch Tomcat
CMD ["/opt/tomcat/bin/catalina.sh", "run"]

# Used for debugging in case something does not work and the container fails to start up because of the CMD instruction specified above.
#ENTRYPOINT ["/bin/sh", "-c", "while true; do sleep 1; done"]

# Added for debugging in case image does not get built
# Install supervisor by commenting out that piece and make sure
# all works fine.
#ADD supervisord.conf /etc/supervisor/
#CMD ["/usr/bin/supervisord", "-n"]
```

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621075435578.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621075435578.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621075548371.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621075548371.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621075701361.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621075701361.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621075748602.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621075748602.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621075804297.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621075804297.png)

```bash
Step 1: Remove the existing pictolearn/tomcat7-jdk7 and pictolearn/tomcat8-jdk8 images
-------------------------------------------------------------------
docker rmi pictolearn/tomcat7-jdk7
docker rmi pictolearn/tomcat8-jdk8

#Step 2: Building an image
#Syntax: docker build -t <image-name> <location of dockerfile>
-------------------------------------------------------------------
docker build -t spring-mvc-tomcat7-jdk7-image .
docker build -t spring-mvc-tomcat8-jdk8-image .

#Step 3: Run a container from the image
#Syntax: docker run -itd --name <container-name> -p <host-port>:<container-port> <image-name>
---------------------------------------------------------------------------------------------
docker run -itd --name tomcat7-jdk7-container-1 -p 5555:8080 spring-mvc-tomcat7-jdk7-image
docker run -itd --name tomcat8-jdk8-container-2 -p 5556:8080 spring-mvc-tomcat8-jdk8-image
```

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621075923603.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621075923603.png)

Sau khi chạy `docker build -t spring-mvc-tomcat7-jdk7-image .` thì sửa docker file

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621080150102.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621080150102.png)

Sau đó build như trên

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621080521402.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621080521402.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621080255181.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621080255181.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621080329902.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621080329902.png)

### **2. Summary**

## **11. Use Case 7 Mounting Volumes**

### **1. Mounting Log Volumes**

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621081809204.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621081809204.png)

Dockerfile

```bash
# This file is used to create a docker image.
# The image name created in the previous use case.
FROM pictolearn/tomcat7-jdk7

#Set Catalina HOME and JAVA_OPTS
ENV CATALINA_HOME /opt/tomcat
ENV PATH $PATH:$CATALINA_HOME/bin
ENV JAVA_OPTS="-Xms1024m -Xmx1024m -Xss8192k -XX:PermSize=500m -XX:CMSInitiatingOccupancyFraction=50 -XX:+ExplicitGCInvokesConcurrent -XX:+CMSClassUnloadingEnabled -XX:+UseConcMarkSweepGC -XX:+UseParNewGC -XX:NewRatio=1 -XX:SurvivorRatio=1  -Dorg.apache.cxf.JDKBugHacks.imageIO=false"

EXPOSE 8080
EXPOSE 8009

# Need a war file from the host to be mounted you can do so here. This instruction tells docker that content in those directories does not go in images and 
# can be accessed from other containers using the --volumes-from command line parameter. You have to run the container using -v 
#/path/on/host:/path/in/container to access directories from the host.
VOLUME "/opt/tomcat/webapps"
VOLUME "/opt/tomcat/logs"

#The WORKDIR instruction sets the working directory for any RUN, CMD, ENTRYPOINT, COPY and ADD instructions that follow it in the Dockerfile.
WORKDIR /opt/tomcat

# Launch Tomcat
CMD ["/opt/tomcat/bin/catalina.sh", "run"]
```

script

```bash
#Step 1: Building an image
#Syntax: docker build -t <image-name> <location of dockerfile>
-------------------------------------------------------------------
docker build -t spring-mvc-tomcat7-jdk7-volume-sample .

#Step 2: List all the images
#Syntax: docker images
-------------------------------------------------------------------
docker images

#Step 3: Run a container from the image with a volume mount
#Container volume is the logs directory for example or war directory
Example:  docker run -itd  -p <host-port>:<container-port> -v <host-volume-absolute-path>:<container-volume-path>  --name=<container-name> <image-id>
---------------------------------------------------------------------------------------------
docker run -itd  -p 3333:8080  -v F:/pictolearn/Docker/logs:/opt/tomcat/logs -v F:/pictolearn/Docker/webapps:/opt/tomcat/webapps  --name="tomcat-container-log" spring-mvc-tomcat7-jdk7-volume-sample
```

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621082243069.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621082243069.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621082508367.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621082508367.png)

Vào setting của icon docker

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2026.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2026.png)

choose F folder

You will see

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2027.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2027.png)

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2028.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2028.png)

Disable smart firewall ⇒ Chỉnh norton smart firewall thành 1h

Tạo folder log và webapp

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2029.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2029.png)

Afterwards, we copy file .war into webapp folder

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621083734602.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621083734602.png)

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2030.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2030.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621083647677.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621083647677.png)

## **12. Use Case 8 Microservices using Docker Machine and Docker Compose**

### **1. Introduction to Docker-Machine**

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2031.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2031.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621085105449.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621085105449.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621085129604.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621085129604.png)

So basically what you're going to be doing is you're going to be running virtual machines on your current

computer beat the PC or the Mac

### **2. MAC Only Pre-requisite for installing Docker Machine**

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621085429623.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621085429623.png)

download

scripts

```bash
*****************************************************************
Docker - machine: Windows and MAC
*****************************************************************

#Create 2 Docker machines (Remember both are virtual PCs running with different IPs)
------------------------------------------------------------------------

Windows: docker-machine create -d hyperv --hyperv-virtual-switch "vs-1" hyperv-vm-1
MAC: docker-machine create --driver virtualbox --virtualbox-disk-size "20000" hyperv-vm-1

Windows: docker-machine create -d hyperv --hyperv-virtual-switch "vs-1" hyperv-vm-2
MAC: docker-machine create --driver virtualbox --virtualbox-disk-size "20000" hyperv-vm-2

#Verify if docker-machine is running on an IP
------------------------------------------------------------------------
docker-machine ip hyperv-vm-1
docker-machine ip hyperv-vm-2

#Run the following command and whatever output you get run it again
------------------------------------------------------------------------
docker-machine env hyperv-vm-1
docker-machine env hyperv-vm-2

#Run the output of the last line of the command which is there before.
------------------------------------------------------------------------
 & "C:\Program Files\Docker\Docker\Resources\bin\docker-machine.exe" env hyperv-vm-1 | Invoke-Expression
 & "C:\Program Files\Docker\Docker\Resources\bin\docker-machine.exe" env hyperv-vm-2 | Invoke-Expression

#Verify the docker-machine is active.
----------------------------------------
docker-machine ls

Turning OFF and ON docker-machine
-------------------------------------
docker-machine stop hyperv-vm-1
docker-machine stop hyperv-vm-2
docker-machine start hyperv-vm-1
docker-machine start hyperv-vm-2

Remove docker-machine (Turn off docker-machine on hyper-v manager for windows before executing this command, for MAC no extra steps are required)
docker-machine rm -f <name-of-machine>

*****************************************************************
Docker - compose commands to follow (Common for MAC and Windows)
Manual Reference: https://docs.docker.com/compose/reference/
*****************************************************************
Step-1 # Builds the image
-------------------------------------------------------------------
docker-compose build

#Build a specific image
docker-compose build <service-name>

#Builds and run the containers
docker-compose up --build -d

Step-2 # View the image (All started and stopped containers)
-------------------------------------------------------------------
docker-compose ps 

Step-3 # Run the image in detached/non-detached mode (use -d) 
-------------------------------------------------------------------
docker-compose up -d
docker-compose up
docker-compose up -d <service-name>

Step-4 # View logs and Tail logs
-------------------------------------------------------------------
# View logs
docker-compose logs <service-name>

# Tail logs
docker-compose  logs -ft <service-name>

Step-5 # Login to the container
-------------------------------------------------------------------
docker-compose run <service-name> /bin/bash 

Step-6 # Stops all containers related to the compose file
--------------------------------------------------
docker-compose stop

#Stop and start specific container
docker-compose stop <service-name>

#Stop and remove containers
docker-compose down
```

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621085758640.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621085758640.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621085941165.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621085941165.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621090059492.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621090059492.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621090257358.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621090257358.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621090355142.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621090355142.png)

Với địa chỉ 100 thì chưa access được

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621090618015.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621090618015.png)

So nginx can run in both container

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621090757672.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621090757672.png)

### **3. Windows only Pre-requisite for Installing Docker Machine**

[https://docs.docker.com/machine/install-machine/](https://docs.docker.com/machine/install-machine/)

### **Install Docker Machine**

1. Install [Docker](https://docs.docker.com/engine/install/).
2. Download the Docker Machine binary and extract it to your PATH.
    
    If you are running **macOS**:
    
    ```
    $ base=https://github.com/docker/machine/releases/download/v0.16.0 &&
      curl -L $base/docker-machine-$(uname -s)-$(uname -m) >/usr/local/bin/docker-machine &&
      chmod +x /usr/local/bin/docker-machine
    
    ```
    
    If you are running **Linux**:
    
    ```
    $ base=https://github.com/docker/machine/releases/download/v0.16.0 &&
      curl -L $base/docker-machine-$(uname -s)-$(uname -m) >/tmp/docker-machine &&
      sudo mv /tmp/docker-machine /usr/local/bin/docker-machine &&
      chmod +x /usr/local/bin/docker-machine
    
    ```
    
    If you are running **Windows** with [Git BASH](https://git-for-windows.github.io/):
    
    ```
    $ base=https://github.com/docker/machine/releases/download/v0.16.0 &&
      mkdir -p "$HOME/bin" &&
      curl -L $base/docker-machine-Windows-x86_64.exe > "$HOME/bin/docker-machine.exe" &&
      chmod +x "$HOME/bin/docker-machine.exe"
    
    ```
    
    > The above command works on Windows only if you use a terminal emulator such as Git BASH, which supports Linux commands like chmod.
    > 
    
    Otherwise, download one of the releases from the [docker/machine release page](https://github.com/docker/machine/releases/) directly.
    
3. Check the installation by displaying the Machine version:
    
    `$ docker-machine version
    docker-machine version 0.16.0, build 9371605`
    

Vào ô search nhập turn windows feature on off

[https://techcommunity.microsoft.com/t5/itops-talk-blog/step-by-step-enabling-hyper-v-for-use-on-windows-10/ba-p/267945](https://techcommunity.microsoft.com/t5/itops-talk-blog/step-by-step-enabling-hyper-v-for-use-on-windows-10/ba-p/267945)

Click check in Hyper-V

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2032.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2032.png)

Check container và hyper-v => restart

Windows/ Search Hyper-V manager

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2033.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2033.png)

Create new virtual switch manager by click on it

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2034.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2034.png)

chọn external and click CREATE

Nhập như trên chọn lại External network là 6025

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2035.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2035.png)

chọn yes

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2036.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2036.png)

### **4. Windows only Setting up 2 Docker Machines**

Run powershell with administration

> vs-1: is virtual machine that we have created in previous chapter
> 

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2037.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2037.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621101804758.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621101804758.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621102014423.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621102014423.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621102352697.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621102352697.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621102553765.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621102553765.png)

run với port 32771 cũng chạy

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621102830276.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621102830276.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621102928224.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621102928224.png)

### **5. Docker-compose Basics and Use case set up**

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621114801536.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621114801536.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621114918380.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621114918380.png)

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2038.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2038.png)

Tag and push to the docker hub

Now Docker composed this used to create micro services are run services inside of Docker machines.

Vào eclipse import project java mysql

pom.xml

```xml
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
	<modelVersion>4.0.0</modelVersion>

	<groupId>docker-mysql-connector</groupId>
	<artifactId>docker-mysql-connector</artifactId>
	<version>1.0.0-SNAPSHOT</version>
	<packaging>jar</packaging>

	<name>docker-mysql-connector</name>
	<url>http://maven.apache.org</url>

	<properties>
		<project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
	</properties>

	<dependencies>
		<dependency>
			<groupId>mysql</groupId>
			<artifactId>mysql-connector-java</artifactId>
			<version>6.0.6</version>
		</dependency>
	</dependencies>

	<build>
		<plugins>
			<plugin>
				<artifactId>maven-assembly-plugin</artifactId>
				<version>2.6</version>
				<configuration>
					<descriptorRefs>
						<descriptorRef>jar-with-dependencies</descriptorRef>
					</descriptorRefs>
				</configuration>
			</plugin>
		</plugins>
	</build>
</project>
```

Dockerfile

```docker
FROM pictolearn/ubuntu-jdk8

#Author of the Docker File
# MAINTAINER Pictolearn Note: MAINTAINER has been deprecated for LABEL, 
# LABEL is a key value pair 
LABEL "Maintainer"="Pictolearn"

ADD . /usr/local/docker-mysql-connector
RUN cd /usr/local/docker-mysql-connector && mvn assembly:assembly
CMD ["java", "-cp", "/usr/local/docker-mysql-connector/target/docker-mysql-connector-1.0.0-SNAPSHOT-jar-with-dependencies.jar", "org.pictolearn.docker.mysql.MySQLConnection"
```

Import existing maven project

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2039.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2039.png)

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2040.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2040.png)

So just to take you back to that picture you're going to go back to that picture which I gave which

is the use case picture which is going to give you a clear description as you can see we created two

documentaries with two different IP addresses these are dummy IP addresses.

One has a Microsoft is running which is called My sql and another is a Java container and standalone

javascript called web.

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2041.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2041.png)

=> 2 dịa chỉ Ip máy ảo khác nhau

docker-compose

```yaml
version: '3.1' #version of Docker-compose
services: #Specifies the micro-service you want to run
  db: # create an image by the name mysql
    # NOTE: As of June, 2018 this has been updated to use the version of mysql 5.7.22  
    image: mysql:5.7.22 # specify the image to download from docker hub, 
    ports: ["3306:3306"] # expose ports to docker-machine , same as the EXPOSE command
    hostname: db  #specify the name of a host which can be used by a container running on the same docker machine
    environment: # specify the password and default database to connect to, note that the default root user will be picked up.
        - MYSQL_ROOT_PASSWORD=root
        - MYSQL_DATABASE=Users
    container_name: mysqldatabase
  web: # create an image by the name web
    build: docker-mysql-connector 
    image: docker-mysql-connector
    hostname: web
    tty: true   # same as the "-t" option used in docker build "-t" 
    depends_on: #Specifies that this container should start up after mysql is build and has started
      - db
    links:  # you will specify this name or the alias name db:<alias> in the java code to connect, note you will not use localhost
      - db:db
    environment: #Specifies the environment variables
      - AWS_ACCESS_KEY=123456
```

### **6. Working with Docker-compose**

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621121400556.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621121400556.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621121508189.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621121508189.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621121523296.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621121523296.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621121637021.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621121637021.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621121702955.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621121702955.png)

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2042.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2042.png)

Nhập vào store in va... để nhập pass test

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621122108119.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621122108119.png)

Build specific id

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621122204427.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621122204427.png)

Lý do có url vì

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2043.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2043.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621122547856.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621122547856.png)

copy the last command

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621122658172.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621122658172.png)

Link can be: `String url = "jdbc:mysql://mysql-1:3306/Users?autoReconnect=false&useSSL=false";` but we have `link` in docker-compose => use `db`

Sau khi sửa lại url trong java có chỉ có db: mới chạy đúng vì đang mount trực tiếp

=> This make easier to deploy selective microservices

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621122942098.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621122942098.png)

```java
package org.pictolearn.docker.mysql;

import java.net.InetAddress;
import java.sql.Connection;
import java.sql.DriverManager;
import java.util.Map;

/**
 * MYSQL connection checker, tries to connect to mysql database.
 *
 */
public class MySQLConnection {
	public static void main(String[] args) throws Exception {
		String ipAddr = InetAddress.getLocalHost().getHostName();
		System.out.println("Printing IP address of the host " + ipAddr);
		Map<String, String> env = System.getenv();
		for (String envName : env.keySet()) {
			System.out.format("%s=%s%n", envName, env.get(envName));
		}
		Thread.sleep(10000);

		boolean connected = false;
		while (!connected) {
			try {
				
				// Note the way the mysql container is used here.
				String url = "jdbc:mysql://db:3306/Users?autoReconnect=false&useSSL=false";
				String user = "root";
				String password = "root";
				System.out.println("Connecting to URL " + url);
				// Load the Connector/J driver
				Class.forName("com.mysql.cj.jdbc.Driver").newInstance();
				// Establish connection to MySQL
				Connection conn = DriverManager.getConnection(url, user, password);
				System.out.println("Connection was successful");
				connected = true;
			} catch (Exception e) {
				System.err.println("Error connecting to database");
				e.printStackTrace();
				Thread.sleep(5000);
			}
		}

	}
}
```

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621123631306.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621123631306.png)

stop all

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621123846810.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621123846810.png)

### **7. Summary**

## **13. Use Case 9 Microservices with Docker, Spring Boot and Hibernate with MYSQL**

### **1. Introduction and Initial Set up**

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621132323492.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621132323492.png)

script

```bash
*****************************************************************
Docker - compose commands to follow (Common for MAC and Windows)
Manual Reference: https://docs.docker.com/compose/reference/
*****************************************************************
Step-1 # Builds the image
-------------------------------------------------------------------
docker-compose build

#Build a specific image
docker-compose build <service-name>

#Builds and run the containers
docker-compose up --build -d

Step-2 # Run the image in detached/non-detached mode (use -d) 
-------------------------------------------------------------------
docker-compose up -d
docker-compose up
docker-compose up -d <service-name>

Step-3 # View the image (All started and stopped containers)
-------------------------------------------------------------------
docker-compose ps 

Step-4 # View logs and Tail logs
-------------------------------------------------------------------
# View logs
docker-compose logs <service-name>

# Tail logs
docker-compose  logs -ft <service-name>

Step-5 # Login to the container
-------------------------------------------------------------------
docker-compose run <service-name> /bin/bash 

Step-6 # Stops all containers related to the compose file
-------------------------------------------------------------------
Use a RESTFul Client to test the APIs

Step-7 # Stops all containers related to the compose file
--------------------------------------------------
docker-compose stop

#Stop and start specific container
docker-compose stop <service-name>

#Stop and remove containers
docker-compose down
```

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2044.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2044.png)

Dockerfile

```bash
#Install from the same image built i usecase - 8
FROM pictolearn/ubuntu-jdk8

# add the directory to the path
ADD . /usr/local/pictolearn

# Run maven
RUN cd /usr/local/pictolearn && mvn clean package

#Spring boot initiation
CMD ["java","-jar","-DlogPath=/usr/local/pictolearn", "/usr/local/pictolearn/target/docker-compose-pictolearn-1.0.0-SNAPSHOT.jar"]
```

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2045.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2045.png)

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2046.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2046.png)

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2047.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2047.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621133234462.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621133234462.png)

import to eclipse

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2048.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2048.png)

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2049.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2049.png)

![](assets/Pasted%20image%2020220724022210.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621135320324.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621135320324.png)

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2050.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2050.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621135448819.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621135448819.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621135638775.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621135638775.png)

Gọi post and get

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2051.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2051.png)

body lấy từ file post.json, type is application/json

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621140015916.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621140015916.png)

Connect to db

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2052.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2052.png)

### **2. Building Spring Boot Microservice with Docker**

## **14. Use Case 10 Service Discovery and Load Balancing**

### **1. Use Case 10 Scaling up Microservices, Service Discovery and Load Balancing**

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621140251007.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621140251007.png)

scripts

```bash
*****************************************************************
Step-1 # Run Powershell as administrator on WINDOWS or terminal on MAC
-------------------------------------------------------------------
docker-machine ps -a

*****************************************************************
Step-2 # Docker machine activation
-------------------------------------------------------------------
docker-machine env hyperv-vm-1
WINDOWS (Copy and execute the last line): # & "C:\Program Files\Docker\Docker\Resources\bin\docker-machine.exe" env hyperv-vm-1 | Invoke-Expression

Step-3 # Run the image in detached/non-detached mode (use -d) 
-------------------------------------------------------------------
docker-compose up -d
docker-compose up
docker-compose up -d <service-name>

docker-compose scale <service-name>=<total containers>
Ex: docker-compose scale web=2

Step-4 # View logs and Tail logs
-------------------------------------------------------------------
# View logs
docker-compose logs <service-name>

# Tail logs
docker-compose  logs -ft <service-name>

Step-5 # Login to the container
-------------------------------------------------------------------
docker-compose run <service-name> /bin/bash 

Step-6 # Stops all containers related to the compose file
--------------------------------------------------
docker-compose stop

#Stop and start specific container
docker-compose stop <service-name>

#Stop and remove containers
docker-compose down
```

### **2. Quick Code Overview**

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621141227030.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621141227030.png)

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2053.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2053.png)

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2054.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2054.png)

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2055.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2055.png)

Dockerfile

```docker
# This file is used to create a docker image.
FROM pictolearn/tomcat8-jdk8

#Author of the file
MAINTAINER pictolearn

#install maven for debugging
RUN apt-get -y install maven lsof

#Set Catalina HOME and JAVA_OPTS
ENV CATALINA_BASE /opt/tomcat
ENV CATALINA_HOME /opt/tomcat
ENV PATH $PATH:$CATALINA_HOME/bin
ENV JAVA_OPTS="-Xms1024m -Xmx1024m -Xss8192k -XX:PermSize=500m -XX:CMSInitiatingOccupancyFraction=50 -XX:+ExplicitGCInvokesConcurrent -XX:+CMSClassUnloadingEnabled -XX:+UseConcMarkSweepGC -XX:+UseParNewGC -XX:NewRatio=1 -XX:SurvivorRatio=1  -Dorg.apache.cxf.JDKBugHacks.imageIO=false"

#Expose this a port to the host machine.
EXPOSE 8080
EXPOSE 8009

#The WORKDIR instruction sets the working directory for any RUN, CMD, ENTRYPOINT, COPY and ADD instructions that follow it in the Dockerfile.
WORKDIR /opt/tomcat

# add the directory to the path
ADD . /usr/local/pictolearn

RUN mkdir -p /usr/local/pictolearn/logs

# Run maven
RUN cd /usr/local/pictolearn && mvn clean package

# Move the war file to the tomcat folder once it is done.
RUN  cp /usr/local/pictolearn/target/pictolearn-dispatcher.war /opt/tomcat/webapps/pictolearn-dispatcher.war

# Launch Tomcat
CMD ["/opt/tomcat/bin/catalina.sh","run"]
```

pom.xml trong dispatcher

```xml
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
	<modelVersion>4.0.0</modelVersion>

	<groupId>pictolearn-web</groupId>
	<artifactId>pictolearn-web</artifactId>
	<version>1.0.0-SNAPSHOT</version>

	<name>org.pictolearn.redis</name>
	<url>http://maven.apache.org</url>

	<properties>
		<project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
		<java.version>1.8</java.version>
	</properties>

	<parent>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-starter-parent</artifactId>
		<version>1.4.1.RELEASE</version>
	</parent>

	<dependencies>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-web</artifactId>
		</dependency>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-actuator</artifactId>
		</dependency>

		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter</artifactId>
			<exclusions>
				<exclusion>
					<groupId>org.springframework.boot</groupId>
					<artifactId>spring-boot-starter-logging</artifactId>
				</exclusion>
			</exclusions>
		</dependency>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-data-jpa</artifactId>
		</dependency>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-log4j2</artifactId>
		</dependency>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-test</artifactId>
		</dependency>
		<!-- https://mvnrepository.com/artifact/mysql/mysql-connector-java -->
		<dependency>
			<groupId>mysql</groupId>
			<artifactId>mysql-connector-java</artifactId>
			<version>6.0.4</version>
		</dependency>
		<!-- https://mvnrepository.com/artifact/org.hibernate/hibernate-core -->
	</dependencies>

	<build>
		<plugins>
			<plugin>
				<groupId>org.apache.maven.plugins</groupId>
				<artifactId>maven-surefire-plugin</artifactId>
				<configuration>
					<skipTests>true</skipTests>
				</configuration>
			</plugin>
			<plugin>
				<groupId>org.springframework.boot</groupId>
				<artifactId>spring-boot-maven-plugin</artifactId>
			</plugin>
			<plugin>
				<artifactId>maven-failsafe-plugin</artifactId>
				<executions>
					<execution>
						<goals>
							<goal>integration-test</goal>
							<goal>verify</goal>
						</goals>
					</execution>
				</executions>
			</plugin>
		</plugins>
	</build>
</project>
```

### **3. Demo**

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2056.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2056.png)

Make sure your windows enable hyper-v and run powershell with administration

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621150319843.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621150319843.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621150437551.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621150437551.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621150542598.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621150542598.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621150717085.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621150717085.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621151018304.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621151018304.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621151039038.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621151039038.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621151149163.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621151149163.png)

Sau đó vào mysql chỉnh sửa connection

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621151310652.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621151310652.png)

Mysql run on port 8888

Test connection

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2057.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2057.png)

Click store in val... ⇒  nhập pass ấn test

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2058.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2058.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621151649782.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621151649782.png)

So what I'm going to do here is and is going to say send and it's a success for introspect the headers

it's going to tell you which machine it actually hit.

So in this case it's 172 19 0.3.

So what I'm going to do right now as I'm going to go and check into my school database to make sure

there's an entry as I see it got inserted.

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2059.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2059.png)

### scale up the app

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621153402519.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621153402519.png)

And the reason why we have a dispatcher is to be able to route to one of these.

So that said give it a few minutes until it starts up.

And typically for logging from all these containers we use tools like loudly that is a tool cloggy our

diner trays or at Dynamix higher performance monitoring tools.

You can see the random ip

![Hands%20on%20Course%20for%20Java%20Developers/Untitled%2060.png](Hands%20on%20Course%20for%20Java%20Developers/Untitled%2060.png)

![https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621153544505.png](https://github.com/Duy-Phuong/docker-docs/raw/master/docker-java.assets/image-20200621153544505.png)

scale down

## **15. Summary, Docker Cheatsheets, Feedback**

### **1. All Powerpoints and Docker Cheatsheet**

### **2. Summary and Feedback**