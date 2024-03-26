# Environment variables: 
## Plain text KV pairs: 
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