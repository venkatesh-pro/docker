There are three way of network in docker
1. Container to WWW Communication
2. Container to Local Host Machine Communication
3. Container to Container Communication


We can send request to world wide web inside the container ,it works fine

But connecting to container and localhost doesn't work, we have to change the localhost into *host.docker.internal*