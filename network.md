There are three way of network in docker
1. Container to WWW Communication
2. Container to Local Host Machine Communication
3. Container to Container Communication


1. We can send request to world wide web inside the container ,it works fine

2. But connecting to container and localhost doesn't work, we have to change the localhost into *host.docker.internal*

mongodb://localhost:27017/test   
to 
mongodb://host.docker.internal:27017/test   

3. Connecting container to container

creating container for mongodb
```
docker run -d --name mongodb mongo
```
so we created container for mongodb , so we have to specify the ip address of mongodb

to see the ip address of mongo
```
docker container inspect <NameOFContainermongodb>
```
we have to grap the ip address 

mongodb://host.docker.internal:27017/test   
to
mongodb://172.17.0.2:27017/test   


it is difficult to add ip address, we can connect all the container in same network, so that we don't need ip

```
docker network create favorites-net
```
```
docker run -d --name mongodb --network favorites-net mongo
```
putting other container in same network
```
docker run -d --name fav --network favorites-net -p 3000:8000 favorites-node
```
if two container in same network we can put the name of the other container to the url

mongodb://172.17.0.2:27017/test   
to 
mongodb://mongodb:27017/test   
