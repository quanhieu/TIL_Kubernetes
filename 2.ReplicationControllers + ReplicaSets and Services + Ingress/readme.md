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

```
# Init ubuntu
kubectl run -i --tty ubuntu --image=ubuntu:20.04 -- bash

apt update && aot install curl -y


```