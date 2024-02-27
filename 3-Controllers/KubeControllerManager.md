# Controller manager
Managing controllers in kubernetes cluster, working all to match the current state with the desired one 
- watch status 
- Remediate the status

## Main Kubernetes controllers: 
## 1.  Node Controller: 
Monitors the nodes and taking actions "Through the API server" to keep the application running 
### How: 
- watches the status of the node every "Node Monitor Period = 5 seconds" 
- if its stopped to receive a heart beats from the node, It waits for "Node Monitor Grace Period= 40 seconds" then marks the node as unreachable  
- It gives it "POD Eviction timeout=5 minutes"  to come up again, If not, It removes the pods assigned to this node and provisions them in healthy nodes **If they are a part of ReplicaSet**
 
## 2.  Replication Controller: 
Monitors the status of ReplicaSets, ensuring that the desired number of PODs are available at any point of time, If a POD dies, it creates another one 

