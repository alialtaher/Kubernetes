# KubeScheduler
Responsible for deciding where to place the workloads on Worker nodes, Replying to KubeAPI which is going to store this info in ETCD to be consumed by Kubelet.
It can decide depending on certain requirements like:
- resource requirements and limits
- Taints and Tolerations 
- Node Selectors/Affinty



