# Node Selectors
A property to be set on a POD level, identifies the right node to schedule the pod on 
## Steps 
1. Label your node: kubectl label nodes nodename key=val
2. add the selector to the pod manifist
    spec:
        nodeSelector: 
            key:value


It has limitations for the number of selectors and processing, so we are going to use node affinity to be able to acheive more complex requirments 
