# jenkins-docker

1. docker network create jenkins
<br />
2. docker run \
  --name jenkins-docker \
  --rm \
  --detach \
  --privileged \
  --network jenkins \
  --network-alias docker \
  --env DOCKER_TLS_CERTDIR=/certs \
  --volume jenkins-docker-certs:/certs/client \
  --volume jenkins-data:/var/jenkins_home \
  --publish 2376:2376 \
  docker:dind
  <br />
3. docker build -t myJenkins .
<br />
4. docker ps
<br />
5. docker exec <container_name> cat /var/jenkins_home/secrets/initialAdminPassword
<br />
6. Open port 8080 of the container
