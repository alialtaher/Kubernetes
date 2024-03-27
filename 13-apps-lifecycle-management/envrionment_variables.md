# Environment variables: 

## way1- Plain text KV pairs: 
In order to pass a KV pair as a container arg, you can add a list of env variables as shown in the following example

**Example:**  
apiVersion: v1
kind: Pod
metadata: 
    name: nginx
spec: 
    containers:
      - name: nginx
        image: nginx
        env: 
         - name: appstack-code
           value: XYZ001
        

## way2- ConfigMap:
Used to pass configuration data in the form of KV pairs to Kubernetes, Inject the configmap in the object definition for the values to be available in the object RUNTIME environment 


**Example:** 
### Configmap definition: 
APP_COLOR: Blue
APP_MODE: prod

### POD definition: 
apiVersion: v1
kind: Pod
metadata: 
    name: nginx
spec: 
    containers:
      - name: nginx
        image: nginx
        envFrom: 
         - configMapRef:


### How to create a configMap

1. impertive: kubectl create configmap config-name --from-literal=key=value 
2. declarative: 
        *apiVersion: v1*
        *data:*
          *key1: value1*
          *key2: value2*       
        *kind: ConfigMap*
        *metadata:*
            *name: appconfig*

### How to inject into a POD: apiVersion: v1
kind: Pod
metadata: 
    name: nginx
spec: 
    containers:
      - name: nginx
        image: nginx
        envFrom:
        - configMapRef:
          name: appconfig 


