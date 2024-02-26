# Labels and Selectors
## labels: 
key/value pairs attached to Kubernetes objects to make it easy to describe instance functionality/placement
EX: 
pod labels are env=prod identifies that the pod is running in prd environment

## Selectors: 
used to select Kubernetes objects that matches a specific label value
EX:
Select pods that runs into dev environement 
kubectl get pods -l env=dev


## how to show labels: 
kubectl get pods --show-labels \\ by default run=podname label is attached

## how to label a pod:
kubectl label pod pod1 key=value

## how to use selectors: 
kubectl get pods -l env=dev
kubectl get pods -l env!=dev


## how to add a label ti a running pod:
kubectl label pod pod_name key=value 

## how to remove a label from a running pod:
kubectl label pod pod_name key-



# YAML part

## how to label a pod in YAML Spec file
metadata: 
    labels: 
        key1 : val1
        key2 : val2

        
