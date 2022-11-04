
```yaml
# Create pod ubuntu
kubectl run -i --tty ubuntu --image=ubuntu:20.04 -- bash

cd /var/run/secrets/kubernetes.io/serviceaccount

ls
```

```yaml
# Test
kubectl run app-v1 --image=nghoangviet/lab-private-registry:latest -n test -- sleep 9999999999
```

```yaml
# Create secret
kubectl create secret docker-registry my-secret --docker-server=docker.io --docker-username=nghoangviet --docker-password='Abc!@#123'

k get secret

k describe secret my-secret

kubectl patch serviceaccount default -p '{"imagePullSecrets": [{"name": "my-secret"}]}'

k describe sa default

kubectl run app-v1 --image=nghoangviet/lab-private-registry:latest -n default -- sleep 9999999999

k get po -w

k get ns
```

```yaml
# Create namespace
k create ns developer

k get ns

k get sa -n developer

# Create service account
k create sa dev -n developer
k get sa -n developer
```

```yaml
# apply role rbac

k apply -f ./rbac/role.yaml
k apply -f ./rbac/role-binding.yaml

k get role -n developer
```

```yaml
# apply Pod Security

k apply -f ./run-as-root.yaml
k apply -f ./run-as-user.yaml

k apply -f ./run-pod-readonly.yaml
```

```yaml
# Network Security
minikube start --cni cilium

k get po -n kube-system
k get daemonset -n kube-system

k get networkpolicy
```

```yaml
k run nginx --image=nginx 
k run ubuntu --image=ubuntu:20.04 -- sleep 9999999999

k get pod -o wide
k exec -it ubuntu sh

k get nodes -o wide

k apply -f ./deny-all.yaml -n default
```

## [Network Policy editor and generate yaml](https://editor.cilium.io/)