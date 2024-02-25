# Kubernetes commands VS arguments
**
entrypoint in docker = command in Kubernetes
CMD in docker = arguments in Kubernetes
**


## how to pass command on Kubernetes manifies file
### using commands option:
apiVersion: v1
kind: Pod
metadata
 name: test

spec: 
    containers:
    - name: busybox
      image: busybox
      commands: ["sleep", "3600"]

### using args option:
apiVersion: v1
kind: Pod
metadata
 name: test

spec: 
    containers:
    - name: busybox
      image: busybox
      args: ["sleep", "3600"]

### using commands and args combination:
apiVersion: v1
kind: Pod
metadata
 name: test

spec: 
    containers:
    - name: busybox
      image: busybox
      commands: ["sleep"]
      args: ["3600]

## usecases
img entrypoint      img command     container command       container argument      final
--------------------------------------------------------------------------------------------------------
sleep               3600            not set                 not set                 sleep 3600
--------------------------------------------------------------------------------------------------------
sleep               3600            ping -c5 google.com     not set                 ping -c5 google.com
--------------------------------------------------------------------------------------------------------
sleep               3600            not set                 5000                    sleep 5000
--------------------------------------------------------------------------------------------------------
sleep               3600            ping                    yahoo.com               ping yahoo.com