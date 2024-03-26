# Deployment Rollout
When you first create a deployment, it triggers a rollout, a new rollout creates a new revision.
In the future, when the application is upgraded, a new rollout is triggered, leading to a new revision. 


This helps us keep track of the changes made to our deployment and enables us to rollback to a previous version if anything goes wrong 


## Rollout commands
- To view status of your rollout: kubectl rollout status deploy/deployment_name
- To see the revisions and the history of the rollout: kubectl rollout history deploy/deployment_name


## Deployment startegy: 
1. recreate: Destroy all running replicas, then upgrade. "Causing downtime" 
2. Rolling update: one replica go down, updated then move the next one. "Default strategy" 

## How rolling-update strategy works? 
It works by creating a new replicaset, create/destroy a replica from the new/old replicaset, doing so until the old replicaset is empty. 


## Commands: 
**create**    kubectl create -f deployment.yaml
**Get**       kubectl get deploy
**Update**    kubectl apply -f new-deployment.yaml or kubectl set image deploy/deployname imagename
**Status**    kubectl rollout status deploy/deployment name
**Rollback**  kubectl rollout undo deploy/deployment name