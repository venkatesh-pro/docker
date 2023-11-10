we won't use docker compose to push images to docker hub

we use cmd

docker build -t query-nodejs ./backend

then need to re-tag for docker hub
docker tag query-nodejs venkateshprodocker/querydocu

after tag will create a new image and we push that image to docker hub
docker push venkateshprodocker/querydocu:tagname



for frontend we follow same procedure but we server build it in nginx 
see the Dockerfile.prod file