# ReplicationControllers + ReplicaSets

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

***
# Networking in kubernetes

***

## Services

### Default service - ClusterIP type

```
$ cd networking

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
## Take <CLUSTER-IP> as 10.98.234.32


# Init ubuntu
kubectl run -i --tty ubuntu --image=ubuntu:20.04 -- bash

# Exec inside kube container
k exec --stdin --tty ubuntu -- sh

# Update and install Curl
apt update && apt install curl -y

# Curl to service
curl <CLUSTER-IP>:<port>
curl 10.98.234.32:9999
curl my-service:9999
curl my-service.default.svc.cluster.local:9999


# Check log pod nginx
k get pods
k logs nginx-q69zg

# Port-forward
k port-forward svc/my-service 7777:9999
```

### NodePort type

```
## Apply
k apply -f service-node-pod.yml

# Get node internal-ip
k get nodes -o wide

# Test
<INTERNAL-IP>:<nodePort>
192.168.49.2:30007
```

<br>

# Ingress

```
# Minikube List addon
minikube addons list
minikube addons list | grep ingress

# Minikube Enable ingress
minikube addons enable ingress
```

```
# Apply
k apply -f ingress.yml

# Get ingress
k get ingress

# Override
sudo !!
nano /etc/hosts

## Add to /etc/hosts
192.168.49.2    example.com.vn

# Test
example.com.vn
```

```
# Get pod include namespace ingress-nginx
k get po -n ingress-nginx

# Exec inside ingress-nginx
k exec -it ingress-nginx-controller-5959f988fd-kckt9 -n ingress-nginx -- sh

cat /etc/nginx/nginx.conf
```

# Load Balancer

`
Just run on cloud with static IP included
`

```
$ cd networking/load-balancer

# Create pod
k apply -f pod.yml

# Create load balancer
k apply -f service.yaml
```
