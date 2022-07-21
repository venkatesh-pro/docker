![dc0d6707-4e97-4eaf-b09b-f0b1b9b0d7bf](https://user-images.githubusercontent.com/74946135/180138251-00df7909-5604-40b1-baa3-fc8588a72554.jpg)

if we add

```
VOLUME ['/app/feedback']
```

it is anonymous because it has no name for the volume, it will be remove after remove of the container

### Two types of External Data Storages:

![5754b1f1-d670-47c1-a5ad-9a35ee3ab21d](https://user-images.githubusercontent.com/74946135/180139090-aa04e83c-5d8b-4516-be20-673dc96adaab.jpg)

1. Anonymous volumes will store temporary data
2. Named volumes will store permanent data
3. Bind Mounts will use to run every time we change the code, we no need to build it again

#### How to see the volume that are present

```
docker volume ls
```

## to setup named volume

syntax is

```
feedback:/app/feedback
```

it is name of volume and where it should to be located ,after :

```
docker run -d -p 3000:80 --rm --name feedback-app -v feedback:/app/feedback feedback-node:volumes
```

## Bind Mounts

for this we have to add another volume for the code storage and we have to specify the abosolute path where the code is present

```
docker run -d -p 3000:80 --name feedback-app -v feedback:/app/feedback -v "F:\docker\volume-app:/app" feedback-node:volumes
```

if we use this cmd it will provide err
to see the error

```
docker logs <NAMEOFCONTAINER>
```

it is override the /app in container so we didnt get _node_modules_ folder, so this cmd will solve ,by adding another volume , but anonymous volume, because we don't need to save.

```
docker run -d -p 3000:80 --name feedback-app -v feedback:/app/feedback -v "F:\docker\volume-app:/app" -v /app/node_modules feedback-node:volumes
```

## We can use Nodemon in a container,when code get change

we have to change in Dockerfile

```
CMD ['npm','start']
```

building the image

```
docker build -t feedback-node:volumes .
```

running the container

```
docker run -d -p 3000:80 --name feedback-app -v feedback:/app/feedback -v "F:\docker\volume-app:/app" -v /app/node_modules feedback-node:volumes
```

what to see the nodemon logs

```
docker logs <NAMEOFCONTAINER>
```
