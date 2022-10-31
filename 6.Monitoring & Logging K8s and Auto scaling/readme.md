```yaml
# minikube list
minikube addons list


# install metrics server
minikube addons enable metrics-server

# Check installed metrics server
k top nodes
k top pods --namespace kube-system
```

```yaml
# or for other kube 
minikube addons disable metrics-server

kubectl apply -f https://github.com/kubernetes-sigs/metrics-server/releases/latest/download/components.yaml

## Fix bug Cert error
k get deploy -n kube-system

k edit deploy -n kube-system metrics-server

Edit file:
---
    - args:
        --kubelet-insecure-tls
        ...


Write edit:
:wa

Quit not apply:
:q!

# Check installed metrics server
kubectl top nodes
k top pods --namespace kube-system
```

```yaml
# Apply hpa
k autoscale deploy nginx-deployment --min=1 --max=10 --cpu-percent=50

# Check hpa
k get hpa -A

k get hpa -w
```

```yaml
# benchmark
k get node -o wide

k get svc

# test benchmark
ab -n 1000000 -c 100 http://192.168.49.2:32570/
```

```yaml
# get logs
k get pods

# get logs from pod include 1 container
k logs pod-name

# get logs from pods more than 2 containers
k logs pod-name -n name-space

k logs pod-name -c container-name -n name-space
```

```yaml
# get event
k get events

k get events | grep pod/load-generator
```
