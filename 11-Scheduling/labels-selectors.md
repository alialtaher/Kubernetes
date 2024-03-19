# Labels and Selectors

## Labels
Standard method to group objects together 


## Selectors
Select objects based on a specific label



## How to use? 
### Labels: 
kubectl run ubuntu --image=ubuntu --labels env=dev,app=s01

### Selectors: 
kubectl get pods --selector env=dev,app=s01

## how Kubernetes objects use labels and selectors
objects use labels and selectors to connect different objects together 

Example: Replicaset use labels and selectors to function correctly 