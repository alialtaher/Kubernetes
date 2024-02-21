# Cluster components overview

## Master Node:
### Etcd: 
key/value store used for storing cluster information 
### ApiServer:
Interaction point for kubernetes cluster components, also receives administrationi commands from enduser "API,CLI" 
### Kube scheduler:
Responsible for scheduling workloads on workers
### Kube controller manager:
Controlling various aspects, including: 
 1. Node Controllers: when a node goes down
 2. Replication controller: ensure that the desired number of replicas is available
 3. Endpoint controllers
 4. Service account & Token controllers
 
### Cloud controller manager:
Runs controllers that interact with the underlying cloud providers.


## Worker Node: 
### Kubelet: 
An agent runs on each node in the cluster, makes sure that containers are running in a pod, and sends/receives statistics/instructions from Master node
### Kube_proxy:
Acts as a network proxy maintains network roles on the host and performs connection forwarding 
### Container runtime engine:
Responsible for running containers, Ex: Docker, containerd


## Important notes:
1. The API Server is the only component that connects to Etcd, all other components must go through the API server in order to access cluster state information.
2. The API server is responsible for Authentication, Authorization mechanism, All API request should be authenticated and authorized to perform the desired action

