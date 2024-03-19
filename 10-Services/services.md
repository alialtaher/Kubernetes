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

