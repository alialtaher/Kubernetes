# Daemon sets
Kubernetes object ensures that a one instance of a pod is deployed on all of the nodes in the cluster
Example is kube-proxy and Networking plugins as well 


Example: 
apiVersion: apps/v1
kind: DaemonSet
metadata: 
    name: elk
spec: 
    selector: 
        matchLabels:
            app: monitoring
    template: 
        metadata:
            labels: 
                app: monitoring
        spec: 
            containers:
            - name: monitoring
              image: monitoring
              