# DOCKER Revise _ CMD VS ENTRYPOINT
Both of them used to instruct the container about what to run when started 
### EX of a Docker file with CMD: 
FROM busybox
CMD ["sh"]


docker build -t base01 . 
docker container run -dt --name base01 base01 

docker ps will show in Command field: sh

### Override CMD 
docker container run -dt --name base02 base01 sleep 3000
docker ps will show in Command field: sleep 3000



### EX of a Docker file with ENTRYPOINT: 
FROM busybox
ENTRYPOINT ["ping"]

docker build -t base02 . 
docker container run -dt --name base03 base02 
docker ps will show in Command field: ping


We can't edit the entrypoint, but we can append argument to 


### Append ARGS to ENTRYPOINT container
docker container run -dt --name base04 base02 google.com

docker ps will show in Command field: ping google.com
