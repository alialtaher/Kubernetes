# Replicaset
A kubernetes object that tries to match the desired state with the current state
Desired state: it's what you decalre when you create the replicaset, EX: 3 pods running with nginx image
Current state: it's what objects are currently running, EX: 3 pods of nginx according to the desired state

**If for some reason, A pod running as a member of a replicaset, stopped for any reason, resulting in desired state not matching to the current state, The replicaset will run a new pod to fix the issue**

## how to create Replicasets

### YAML: 
apiVersion: apps/v1
kind: ReplicaSet
metadata:
  name: frontend
  labels:
    app: guestbook
    tier: frontend
spec:
  replicas: 3
  selector:
    matchLabels:
      tier: frontend
  template:
    metadata:
      labels:
        tier: frontend
    spec:
      containers:
      - name: php-redis
        image: gcr.io/google_samples/gb-frontend:v3

### how to run a replicaset
kubectl apply -f frontend-rs.yaml
kubectl get rs
kubectl get pods

