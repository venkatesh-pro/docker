To See the docker is runing or not
```
docker ps
```
To See the docker all container, including the stoped
```
docker ps -a
```

### docker run vs start
Docker run will create a container and start will run the stoped container
```
docker start <NAME>
```
### Docker Attached & Detached Container
Attacher => it is, when we run it will not exit the command promt
Detached => it is, when we run it will exit the command promt and it run in background

To change docker run to datached we can use: -d
```
docker run -p 3000:80 -d <ID>
```

To see the console.log , we can change to attach mode
```
docker attach <NAME>
```
But for docker start , we can't see logs because it is automaticallly detached mode, so we can change it into
```
docker start <NAME>
docker logs <NAME>
``` 
by using this we can see all previous logs
```
docker logs -f <NAME>
``` 
it is to see the future logs

### Deleting Images and Containers
Delete container
```
docker rm <NAME>
```
### To see all Images
```
docker images
```
Delete Image
```
docker rmi <ID>
```
--rm => automatically remove the container when it exits
```
docker run -p 3000:8000 -d --rm <ID>
```
### Naming and Tagging Container and Images
when u run container it will generate automatic name, so we can change it
```
docker run -p 3000:8000 -d --rm --name venkat <ID>
```
to stop container
```
docker stop venkat
```
### Name and Tag in Image

![20b690c3-647b-45b0-bf08-71f6af03b4c1](https://user-images.githubusercontent.com/74946135/179891771-48fce328-019e-400e-ae22-4378eec80ee5.jpg)

```
docker build -t goals:anything .
```
```
docker run -p 3000:8000 -d --rm --name venkat goals:anything
```