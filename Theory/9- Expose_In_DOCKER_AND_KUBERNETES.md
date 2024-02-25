# EXPOSE of docker container and Kubernetes objects

## Docker file
expose means just a documentation for which ports the application inside the container is running on

FROM busybox
ENTRYPOINT ["nginx"]
EXPOSE 80

## kubernetes
expose means just a documentation for which ports the application inside the pod/kubernetes object is running on


apiVersion: v1
kind: Pod
metadata
 name: test

spec: 
    containers:
    - name: nginx
      image: nginx
      ports:
       - containerPort: 8080  
