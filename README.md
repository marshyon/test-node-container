# Simple Node App

This simple Node application is meant to be used for testing Docker based infrastructure such as Kubernetes, Swarm, OpenShift etc. All it does is run on port 8080 and return the hostname on which 
it finds itself when running.

# Stand alone

```
node app.js
```

# Docker 

build & run locally :

```
docker build -t test-node-container .
docker run --name test-node -p 8080:8080 -d --rm test-node-container
...
# to stop and remove (because --rm was used to auto remove) running container ...
docker stop test-node 
```

push to docker and run from uploaded image :

```
docker tag test-node-container marshyon/test-node-container
docker push marshyon/test-node-container
docker run -p 9090:8080 -d --rm marshyon/test-node-container -name test-node
...
# to stop and remove (because --rm was used to auto remove) running container ...
docker stop test-node 
```

___replacing marshyon with your docker hub account name___

