# ETCD in kuberentes

## what is ETCD 
Distributed, Reliable key/value store, simple fast and secure.

## ETCD versions 
1. first stable version 2.0 released in FEB 2015 supporting redesigned Raft consensus algorithm which supports +10K writes per second  
2. version 3.1 was released in JAN 2017.
3. in NOV 2018, ETCD was incubated in CNCF

** Note ** Changes in etcdctl commands explained below 







## Installation of ETCD**
### binaries: 
1. download from github
2. extract with tar
3. run, the service by default listens on port 2379
4. configure clients to store in etcd, The default client is etcdctl utility, we will highlight how security will be handled. 

### Pod:
1. runs inside apod in kube-system namespeace
2. mainly when you setup with kubeadm 


## ETCDCTL API V2 VS V3
etcdctl supports both versions, to show what API version you are using run: 
etcdctl --version //v2
etcdctl version   //v3

** ETCDCTL_API environment variable is used to change the version of the API **  

## commands:
** v2 **
etcdctl set key val
etcdctl get key
etcdctl backup
etcdctl cluster-health
etcdctl mk
etcdctl mkdir

** v3 ** 
etcdctl put key val
etcdctl get key
etcdctl snapshot save 
etcdctl endpoint health



## main configuration parameters: 
- advertise-client-urls: the address on which etcd listens, by default is https://localhost:2379
- initial-cluster-controller: specify the different instances of etcd for HA




## Authentication between ETCDCTL and ETCD_API
The certificate files are available in the etcd-master at the following paths
--cacert /etc/kubernetes/pki/etcd/ca.crt     
--cert /etc/kubernetes/pki/etcd/server.crt     
--key /etc/kubernetes/pki/etcd/server.key


EXAMPLE: in order to get the list of  keys in etcd: 
kubectl exec etcd-master -n kube-system -- sh -c "ETCDCTL_API=3 etcdctl get / --prefix --keys-only --limit=10 --cacert /etc/kubernetes/pki/etcd/ca.crt --cert /etc/kubernetes/pki/etcd/server.crt  --key /etc/kubernetes/pki/etcd/server.key" 