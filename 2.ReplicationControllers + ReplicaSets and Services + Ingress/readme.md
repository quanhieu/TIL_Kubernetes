# ReplicationControllers + ReplicaSets and Services + Ingress

## ReplicationControllers

```
# Apply
k apply -f replication.yml

# Get replications
k get rc

# Describe replication
k describe rc nginx

# Get pods include more information
k get pods -w -o wide

# Delete
k delete rc nginx
```

## ReplicaSet

```
# Apply
k apply -f replicaSet.yml

# Get replicaSet
k get rs

# Describe replicaSet
k describe rs frontend

# Delete
k delete rs frontend
```

## Service

```
# Apply
k apply -f service.yml

# Get all service
k get service -A

# Describe service
k describe svc my-service

# Get endpoints in service
k get ep my-service
```

- ### Curl from container to service in the same namespace

```
# Scale nginx replica to 1
k scale rc nginx --replicas=1

# Get service
k get svc
## Take CLUSTER-IP as 10.98.234.32


# Init ubuntu
kubectl run -i --tty ubuntu --image=ubuntu:20.04 -- bash

# Exec inside kube container
k exec --stdin --tty ubuntu -- sh

# Update and install Curl
apt update && apt install curl -y

# Curl to service
curl 10.98.234.32:9999
curl my-service:9999
curl my-service.default.svc.cluster.local:9999


# Check log pod nginx
k get pods
k logs nginx-q69zg
```
