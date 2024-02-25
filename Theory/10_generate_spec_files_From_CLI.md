# how to generate pod spec file from CLI
let's say that we want to run a nginx webserver in Kubernetes, We can run it via CLI or yaml files, 
In terms of CLI, it is always good to have a file format where you can track changes on pod level


so, its better to use CLI for fast deployments, but we need a way to generate spec files as well


## Example
 
kubectl run nginx --image nginx --port=80 --dry-run=client -o yaml  > nginx_Pod.yaml

By using dry-run=client option, the kubectl run will not be running, it will only generate the needed requests, and using -o yaml, we will import the needed spec file in yaml format



### bonus: how to delete all of the running pods in the current NameSpace
kubectl delete pods --all  