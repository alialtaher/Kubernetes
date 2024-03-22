# Metrics server
one server per kubernetes cluster, Stores in-memory "No historical data"
Runs as a k8s component "pods, Services,..." and gathers information about cluster components utilization "pods, nodes,..." from cAdvisor "CRE utility" 

## how to enable metrics server
### Minikube installation: 
minikube addons enable metrics-server
### All other installations
git clone https://github.com/kubernetes-incubator/metrics-server.git
kubectl apply -f deploy/1.8+/
kubectl top node
kubectl top pod
