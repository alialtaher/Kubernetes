# Kubernetes
labs and Documentations of my journey with CKA from mummshad course on udemy, started at 27 FEB 2024

## Core concepts - Cluster components

### ETCD
Key/val store for cluster information, well described in folder 1-etcd

### KubeAPI
The center of communication with Kubernetes cluster.

### Controller Manager
Controls the health of cluster components, contains a varity of controllers to ensure cluster/deployments/PV, etc.. health

### Kube Scheduler
Responsible for deciding where to place the workloads on Worker nodes, Not to schedule them "Kubelet responsibility" 

### Kubelet
Worker node component, Main interaction point with the master node.

### KubeProxy
Process on each node, mainly used for network routing to the pods



## Kubernetes objects
### POD
single or multicontainer kubernetes object



