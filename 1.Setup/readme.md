# Setup

## [Install and Set Up kubectl on Linux](https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/)

```
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"

sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl

kubectl version --client
```

## [Install minikube](https://minikube.sigs.k8s.io/docs/start/)

```
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64

sudo install minikube-linux-amd64 /usr/local/bin/minikube
```

```
# start
minikube start

# or start 2 node with profile local-cluster
minikube start --nodes 2 -p local-cluster

# dashboard
minikube dashboard

# manage cluster
minikube pause
minikube unpause
minikube stop
minikube config set memory 9001
minikube delete --all
```

## [Use Docker driver for Minikube](https://minikube.sigs.k8s.io/docs/drivers/docker/?utm_source=j2team&utm_medium=url_shortener&utm_campaign=f2ea6746)

```
minikube start --driver=docker

# To make docker the default driver
minikube config set driver docker
```

# Demo

[pod.yml](./pod.yml)

```yml
# Check network
netstat -tupln

# Get kube config
cat ~/.kube/config

# Create pod
kubectl run nginx --image nginx

# Create pod by yaml
kubectl apply -f ./pod.yml

# get pods list
kubectl get pods

# Describe pod
kubectl describe pod nginx-2

# Label pod
kubectl label pod nginx-2 env=production

# Re-check
kubectl describe pod nginx-2

# Filter by label
kubectl get pods -l env
kubectl get pods -l env=production
kubectl get pods -l env=production,run=nginx --show-labels

# Create namespace
kubectl create namespace test-namespace

# Get namespace
kubectl get namespaces

# Get pods by namespace
k get pods -n default

# Get all resource in a namespace
k get all -n kube-system

# Get pods at all namespace
kubectl get pods -A

# Delete pods
kubectl delete pod nginx nginx-2
```

# Alias

```

# kubecolor => sudo apt -y install kubecolor
alias k="kubecolor"

# kubernetes
# alias k='kubectl'
alias ku='kubectl'
# minikube
alias m='minikube'
alias mi='minikube'

# cloudflare-warp
alias warp='warp-cli connect'
alias warp_on='warp-cli connect'
alias warp-off='warp-cli disconnect'
```

# Monitor

```
Minikube dashboard

K9s

Rancher

Lens kubernetes - k8slens
```
