
docker build --tag myubuntu-git:auto .

docker images

docker run --rm ubuntu-git

docker run --rm ubuntu-git diff

# cleanup
docker rmi -f myubuntu-git:auto

