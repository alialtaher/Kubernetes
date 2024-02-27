# KubeAPI 
it is the primary management component in kubernetes cluster, responsible for authentication and authorization of requests, then led the communication with cluster components, meaning that, API server is involved in every request made to the cluster

**Example** 
Pod creation workflow:
1. user sent a request of pod creation to the KubeAPI.
2. KubeAPI leads the authentication, authorization process
3. KubeAPI creates a pod object without assigning it to a node
4. KubeAPI updates the ETCD with the new pod information 
5. KubeAPI updates the user that the POD has been created
6. The scheduler continiously monitors the API server, and notes that a new POD was created with no node assigned 
7. The scheduler idntifies the right node to place the POD on, and sends information to the KubeAPI 
8. The API server updates the record with the node name in ETCD
9. The API server passes the information about the pod to the kubelet of the desired worker node
10. The Kubelet creates the POD on the worker, and instructs the CRE to run the container image
11. The Kubelet updates the status back to the KubeAPI
12. The KubeAPI stores this information in ETCD  