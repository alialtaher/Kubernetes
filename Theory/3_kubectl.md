# Kubectl with digitalocean managed cluster
Kubectl is a CLI tool used to interact with kubernetes cluster


When you create the cluster in digitalocean, A config yaml file will be generated contains information about the cluster "EX: DNS, Tokens,etc..." 
You have to either pass the config file to every command you run "EX: kubectl --kubeconfig "config.yaml" get nodes"
Or replace the contents of ~/.kube/config with the contents of this file


## Kubectl commands

kubectl get pods                         // list all of the running pods in the current namespace
kubectl run webserver --image=nginx      // Run a nginx webserver
kubectl exec -it webserver -- bash       // Execute a command inside a pod


## pod
one or more application container, and some shared resources for those containers


**Its recommended to build multicontainer pod for tightly coupled workloads**
Example: 

vi multi_container_pod.yaml

apiVersion: v1
kind: Pod
Metadata:
     name: webservers
spec: 
  containers:
    - name: nginx
      image: nginx
    - name: tomcat
      image: tomcat
then run: kubectl apply -f multi_container_pod.yaml
kubectl get pods 

name                READY       Status
webserver           2/2         Running


### how to exec into multicontainer pod:

//By default it will exec into the first container "Nginx in our case":
kubectl exec -it webserver -- CMD 
//if you wish to exec into another container, specify the name with -c option:
kubectl exec -it webserver -c tomcat -- CMD 
