# Manual scheduling
Usually, the scheduler looks for pods with empty nodeName field, looks for the suitable node for them and then binds pod to the node, otherwise, a pod with no node will stay in pending state. 

if you want to manually schedule a pod on a specific node, you can write the node name in the pod manifist file under spec section

Example: 

spec: 
    containers:
        ------------------
        ------------------
        ------------------
    nodeName: node01


you can assign this value only for new pods only, the only way to do so is by creating a binding object and send a POST request to the pods Binding API 

pod binding manifist Example: 
apiVersion: v1
kind: Binding
metadata: 
    name: nginx
target: 
    apiVersion: v1
    kind: Node 
    name: node02
