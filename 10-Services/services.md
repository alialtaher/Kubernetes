# Services
Enables communication between pods, it is also responsible for external communications with the pods

## service types
1. NodePort 
2. ClusterIP "Default" 
3. LoadBalancer



## NodePort Service: 
type of service that acts as a traffic forwarder, it listens to the traffic on a port, and sends the traffic to the targeted pod on another port
it has 3 main ports "From a service perspective": 
1. target port: on pod level, which port your app is listening on "optional variable, value is the same as port if not declared
2. port: the port on the service "Mandatory" 
3. Node Port "30000 - 32767": the port on the worker node hosting the application "auto choose if not declared 

**Example in service.yaml**

## MultiPod services: 

### PODS are on the same node: 
If they match the labels, service will forward the traffic to all of them randomly 
### PODS are on different nodes:
If they match the labels, service will span across all of the nodes, and it will forward the traffic to the pods on the same node 


## ClusterIP services
The default service type in k8s, used mainly to group a set of pods and provide an interface for commumication
it helps for scalability, HA, and SDLC management 
for Example, we have a front end and back end tiers. we can group the backend in one service in order to provide a single connection string


## LoadBalancer services 
K8s supports the LB of the Cloud providers like azure, AWS, and GCP.
it helps to forward the traffic to the NodePort services

If you run a loadbalancer services in a non-supported environment, it will have a Nodeport effect


