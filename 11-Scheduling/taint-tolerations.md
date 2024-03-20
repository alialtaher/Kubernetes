# Taint and Tolerations 
- Pod and node relationship, set restrictions on what pods can be scheduled on a node. 
- Taints are placed on the node, Tolerations are on the pod level. 
- Pod must be tolerant to the taint in order to be scheduled on the node.  


## How to taint? 
Kubectl taint nodes node_name k=v:taint-effect

### Taint effect: 
Defines a strategy for dealing with non-tolerance pods
1. NoSchedule: Pods will never be scheduled on the pods 
2. PreferNoSchedule: Try to avoid placing pods on the node
3. NoExecute: No pods will be scheduled and currently running non-tolerant pods will be evicted from the node  


## How to tolerate? 
spec: 
    tolerations:
        - key: "app"
          operator: "equal"
          value: "blue"
          effect: "NoSchedule" 


## How to remove taint from a node? 
kubectl taint node nodename k=v:action- 