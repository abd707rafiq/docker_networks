To enable communication between containers within the same Docker network, you can follow these steps:

1-Create a Docker network:

docker network create my-network

2-Run containers and attach them to the created network:

docker run --network my-network --name cont1 my-image

docker run --network my-network --name cont2 my-other-image

Now, containers cont1 and cont2 are in the same network and can communicate with each other.

3-To make a request from one container to another, use the container names as hostnames:

fetch('http://cont1/my-data').then(...)

Using the container name as the hostname in the URL allows Docker to resolve the IP addresses internally. 
This ensures seamless communication between containers within the same network.
