
Build the jenkins docker 

```docker
    docker build -t myjenkins-blueocean:1.1
```

then run it as follows. The jenkins is run with user root so that the docker deamon socket could shared by jenkins container to start node docker agents 

```docker
docker run --name jenkins-blueocean --rm --detach --user root  --publish 8080:8080 --publish 50000:50000  --volume $HOME/jenkins:/var/jenkins_home   --volume jenkins-docker-certs:/certs/client:ro  -v /var/run/docker.sock:/var/run/docker.sock -v $PWD:/home/  myjenkins-blueocean:1.2
```
