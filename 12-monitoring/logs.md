# POD Logs
to retrieve pod logs, we can use kubectl logs -f pod-name 

for multi-container pods, we have to specify the name of the container which we want to see its logs as a CLI argument

kubectl logs -f pod-name container-name