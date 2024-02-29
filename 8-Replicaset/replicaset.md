# ReplicaSet and Replication Controller

## Differences between Replication controller and Replicaset
- the RC was replaced by RS 
- RC api version is v1, RS api version is apps/v1 
- RS supports selectors while RC don't 

## Replicaset
we can use matchLabels tag to onboard already running POD into the replicaset

## how to scale replicaset
- updating def file and run kubectl replace -f def_file.yml 
- or run kubectl scale --replicas=6 -f def_file.yml  // not saved in the file

## update a replicaset
- kubectl edit // not persistent
- update the file and kubectl replace -f

**Important notes** 
- when updating a rs with a running replicas, you have to create those pods manually kubectl delete pod $(kubectl get pods | awk {'print $1'} | grep -vi name | grep rsname*)
- how i got the running rs yaml file: 
  kubectl scale rs --replicas=5 rs_name --dry-run=client -o yaml > new-rs.yaml
  update the replicas count to 5 in new-rs.yaml
  run kubectl replace -f new-rs.yml
  or kubectl scale --replicas=2 -f new-replica-set.yaml  -o yaml


  