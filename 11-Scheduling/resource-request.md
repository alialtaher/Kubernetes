# Resource request 
You can declare the neeed resources of your pod to the scheduler which will use this info to decide where to schedule this job

Example: 
spec: 
  resources:
    requests: 
        memory: "4Gi" 
        cpu: 2

And you can specify a limit for resource usage of a specific pod 
spec:        
  resources:
    requests: 
        memory: "1Gi" 
        cpu: 1
  limits:
        memory: "2Gi"
        cpu: 2  

**Notes**
1. If a pod is trying to consume more CPU, the CPU will throttle, and the container cannot use more than its limit
2. if a pod is trying to consume more RAM, the pod will be terminated with OOM error 



## Default configuration
By default, K8s has no restrictions over the resources

## CPU behavior:
lets assume that we have 2 pods pod A and pod B
### case1:
No limit + No requests: Pod 1 can consume the whole resouces, pod 2 can't run 
### case2: 
Limit + No requests: Kubernetes automatically sets requests = limits   
### case3: 
Limit + requests: pods can run smoothly, if pod1 needs some resouces when pod2 is not using them, its not possible in this case
### case4:
requests + No Limit, fixing the dynamic resource sharing issue 




## Limit Range: 
A default resource request & limit to be applied to all pods in K8s cluster "At the namespace level", it affects only the newly created pods, not the old once 

1. CPU: 
apiVersion: v1
kind: LimitRange
metadata:
    name: cpu-resource-constraint
spec: 
    limits:
    - default: 
        cpu: 500m
      defaultRequest:
        cpu: 500m 
      max:
        cpu: "1"
      min:
        cpu: 100m
      type: Container      

2. Memory     
apiVersion: v1
kind: LimitRange
metadata:
    name: memory-resource-constraint
spec: 
    limits:
    - default: 
        memory: 1 Gi
      defaultRequest:
        memory: 1Gi
      max:
        memory: 1Gi
      min:
        memory: 500Mi
      type: Container       

      
      
      
      
      
      
      
## Resouce Quotes: 
name space level object that can create hard limits for requests and limits of all pods 
Example: 
spec: 
    hard: 
        requests.cpu: 4
        requests.memory: 4Gi
        limits.cpu: 10
        limits.memory: 10Gi        