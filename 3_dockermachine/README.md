docker-machine create --driver virtualbox host3

docker-machine ssh host3
    touch dog.file
exit

eval "$(docker-machine env host3)"

# cleanup
docker-machine stop host2
docker-machine kill host3
docker-machine rm host2 host3