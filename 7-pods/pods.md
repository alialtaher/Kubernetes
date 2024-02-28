# PODS 
The smallest object in Kubernetes, acts as a encapsulation for a single/multi container, It can have more than one container, except if those containers are the same "Useless"


You can run two or more dependent containers inside the same pod, They can speak to each other via localhost, 
And if any one of them is dead, Others will die as well 

## how to run Pods
### CLI: 
kubectl run name --image=image_name

## Yaml 
**see nginx.yaml as an example**
kubectl apply -f nginx.yaml  


## how to show running pods
kubectl get pods 

## how to show information for running pods
kubectl describe pod pod_name

