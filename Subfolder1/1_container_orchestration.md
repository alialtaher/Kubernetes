# Overview of container orchestration
Container orchestration is the process of managing the lifecycle of containers, and it's a quiet difficult task to handle in large, dynamic environments

## Example
Nginx webserver container is running with 2 replicas, container orchestration tools "Ex: Kubernetes" handles the following tasks:
 1. scheduling of the containers on the worker VMs
 2. Monitor the health of the containers, and respond to container failure issues 
 3. Monitor the health of the nodes, Making sure that the workload is migrated to the healthy worker nodes in case of cluster failure


 
 