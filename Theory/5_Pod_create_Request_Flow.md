# Flow diagram of object creation in Kubernetes cluster
1. Kubectl writes to the API server.
2. API server authenticates and Authorize the request
3. upon validation, API writes into the Etcd
4. The API server invokes the scheduler
5. The scheduler decides which node to place the object on and returns the response to API server
6. API server writes the response to Etcd
7. API server invokes the kubelet on the targeted node
8. Kubelet communicates with the CRE to create the container
9. Kubelet updates the status of the POD to the API
10. API writes the status to etcd.


**Note**  kubectl api-resources -o wide returns very useful output includes the resources and their api version  
**Note**  kubectl explain pods returns useful information about the needed elements in Yaml 
