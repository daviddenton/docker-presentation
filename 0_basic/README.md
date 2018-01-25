docker run -d -p 5000:5000 registry:2
#docker pull busybox:latest
docker tag busybox:latest localhost:5000/busybox
docker push localhost:5000/busybox
#docker rmi busybox:latest
docker pull localhost:5000/busybox:latest
docker run --name mylinux -it localhost:5000/busybox:latest
    touch helloworld.txt

# in another window...

docker ps -a
docker diff mylinux
docker inspect mylinux
docker commit mylinux localhost:5000/mylinux
docker push localhost:5000/mylinux
docker rm -f mylinux
docker rmi localhost:5000/busybox:latest localhost:5000/mylinux:latest
docker images
docker pull localhost:5000/mylinux:latest
docker run --name mylinux2 -it localhost:5000/mylinux
ls

# cleanup
docker rm  -f mylinux2
docker rmi -f localhost:5000/mylinux
