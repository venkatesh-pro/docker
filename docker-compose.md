![a2451eac-7050-42ef-a53e-7050f0c5aeac](https://user-images.githubusercontent.com/74946135/180672810-f77779eb-d38e-4eda-97a6-15a4823b6408.jpg)

for multicontainer it is little bit time consuming for create build for all container and run all container,but using docker-compose will do this for us with one configuration file

to start the docker-compose

```
docker-compose up
```

to stop the docker-compose

```
docker-compose down
```

for network we create a network to connect from one container to another container, but docker-compose will do it automatically, it will be in same network, if we need own network also we can create it

why we use : somewhere and - somewhere, that is : mean it is key value data , if it is single lined without key, then we use -

```
image: 'mongo'
    volumes:
      - data:/data/db
```
