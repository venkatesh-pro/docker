```
docker build .
```
```
docker run <ID>
```
It will show error, we can't interact,because we only get attached mode from the container for the output , to listen for the input
```
docker run -i -t <ID>
```
-i => interactive
-t => for open the terminal (Allocate a pseudo-TTY)

for the docker start, we dont need -t
```
docker start -i <NAME>
```
