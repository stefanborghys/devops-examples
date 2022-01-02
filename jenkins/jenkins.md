# Jenkins

## Installation

Documentation: https://www.jenkins.io/doc/book/installing/docker

### 1. Create a bridge network:
`docker network create jenkins`

### 2. Allow execution of Docker commands inside Jenkins nodes:

```
docker run --name jenkins-docker \
--rm --detach --privileged \
--network jenkins --network-alias docker \
--env DOCKER_TLS_CERTDIR=/certs \
--volume jenkins-docker-certs:/certs/client \
--volume jenkins-data:/var/jenkins_home \
--publish 2376:2376 \
docker:dind \
--storage-driver overlay2
```

### 3. Create  custom Jenkins Dockerfile

see `Dockerfile`

### 4. Build 'Jenkins' Docker image

`docker build -t myjenkins-blueocean:1.1 .`

### 5. Run custom 'Jenkins' Docker image

```
docker run \
  --name jenkins-blueocean \
  --rm \
  --detach \
  --network jenkins \
  --env DOCKER_HOST=tcp://docker:2376 \
  --env DOCKER_CERT_PATH=/certs/client \
  --env DOCKER_TLS_VERIFY=1 \
  --publish 8080:8080 \
  --publish 50000:50000 \
  --volume jenkins-data:/var/jenkins_home \
  --volume jenkins-docker-certs:/certs/client:ro \
  myjenkins-blueocean:1.1
```

## Endpoints

Web: http://localhost:8080  
Info: http://localhost:50000  

## User Handbook

User Handbook: https://www.jenkins.io/doc/book/using/ 

Using Jenkins (general): https://www.jenkins.io/doc/book/using/  
Pipeline: https://www.jenkins.io/doc/book/pipeline/  
Blue Ocean: https://www.jenkins.io/doc/book/blueocean/ 

Managing Jenkins (managing of nodes and instances): https://www.jenkins.io/doc/book/managing/  
System Administration (back-up, resotre, maintain servers and nodes): https://www.jenkins.io/doc/book/system-administration/  