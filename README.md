# Jenkins
All my work focused around setting up Jenkins and using it.

Using a dockerized version of Jenkins. Following steps from Ricardo Andre Gonzalez Gomez coourse on Jenkins and DevOps

Environment consists of a CentOS image with Docker in it which will be used to work on Jenkins

Setting up Docker.

1) Download the minimalist CentOS 7 Image available.
2) Installation on CentOs:

   sudo yum install -y yum-utils \
   sudo yum-config-manager \
      --add-repo \
      https://download.docker.com/linux/centos/docker-ce.repo

   sudo yum install docker-ce docker-ce-cli containerd.io docker-compose-plugin
   sudo systemctl start docker
   https://docs.docker.com/engine/install/centos/

3) Post installation steps:

   sudo groupadd docker \
   sudo usermod -aG docker $USER \
   newgrp docker 

4) Setting up docker-compose:

   curl -SL https://github.com/docker/compose/releases/download/v2.5.0/docker-compose-linux-x86_64 -o /usr/local/bin/docker-compose \
   sudo chmod +x /usr/local/bin/docker-compose \
   docker-compose --version \
   sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose \
   docker-compose --version
   
Setting up Jenkins:

5) Pulling the Jenkins Image:

   docker pull jenkins/jenkins \
   docker images
   
6) Create the files, directory structure and jenkins container:

    cd /home/jenkins \
    mkdir jenkins-data \
    cd jenkins-data \
    vi docker-compose.yml \
    (copy the YAML file in this repo) \
    docker-compose up -d \
    docker ps
     
7) Docker commands to remember:

    docker info \
    docker images \
    docker ps \
    docker logs <conatainerID> -f \
    docker exec -it <containerID> bash

8) Check VM IP from
    ip -a

9) Set local DNS.
  Enter IP and DNS in your machines c:/system32/drivers/etc/hosts file

10) Jenkins will run on port 8080
