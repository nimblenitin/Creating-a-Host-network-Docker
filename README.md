# Creating-a-Host-network-Docker

Docker network host, also known as Docker host networking, is a networking mode in which a Docker container shares its network namespace with the host machine. The application inside the container can be accessed using a port at the host's IP address (e.g., port 80)

Steps to create a container on a Host network-

```
1. Create and start a container as a detached process and use the host networking driver
$ sudo docker run --rm -d --network host --name nginx_container1 nginx

2. Access the nginx container by browsing http://localhost:80/

3. Inspect the container to check the NetworkMode under the HostConfig
$ sudo docker container inspect nginx_container1

4. Verify which process is bound to port 80 using the netstat command
$ sudo netstat -tulpn | grep :80

5. Examine all the network interfaces, and verify that a new network has not been created
$ ip addr show

6. Stop the container using the following command:
$ sudo docker container stop nginx_container1

```
