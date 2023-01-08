
## [Kubernetes Series - Bài 6 - Volume: gắn disk storage vào container](https://viblo.asia/p/kubernetes-series-bai-6-volume-gan-disk-storage-vao-container-OeVKB6rrKkW)

## Deployment

```yaml
# Apply
k apply -f ./deployment.yml

# Apply and record CHANGE-CAUSE
k apply -f ./deployment.yml --record

# Apply without manifest
kubectl set image deploy nginx-deployment nginx=nginx:1.14.2

# Describe deployment
k describe deploy nginx-deployment
```

## Rollout

```yaml
# Get history deployment
k rollout history deploy/nginx-deployment

# Rollout before version
k rollout undo deploy nginx-deployment

# Preview version Rollout
k rollout history deploy/nginx-deployment --revision=2

# Rollout to version
k rollout undo deploy/nginx-deployment --to-revision=2

# Restart application deployment
k rollout restart deploy nginx-deployment


# Get replicaSet
k get rs

# Get replicaSet include more information
k get rs nginx-deployment-86cd74bb56 -o wide 

# View old manifest at yaml
k get rs nginx-deployment-86cd74bb56 -o yaml

# Describe pod
k get pods
k describe po nginx-deployment nginx-deployment-8498fb578b-8674r
```


## Deployment Strategies

```
- Recreate
- RollingUpdate
- BlueGreen
- Canary
- A/B Testing
```

## Volume Resource

- ### EmptyDir
  - Share volume between containers

```
# Apply
k apply -f volume-emptyDir.yaml

# Get pods
k get pods

# Port-forward
k port-forward pod/fortune 8888:80
or
k port-forward -n default pod/fortune 8888:80

# Exec pod
k exec -it fortune -- sh

# Exec container in pod
k exec -it fortune -c web-server -- sh

cat /usr/share/nginx/html/index.html
```

- ### gitRepo
  - Pull code from repo and mount to container

```
# Install git for minikube
docker ps
docker exec -it minikube sh
apt update && apt install git -y
```

```
k apply -f volume-gitrepo.yaml
```

- ### Host path
  - Mount data from host to container - persistent volume
  - Data save on node, where pod has been schedule
  - Just connect one node

```
k apply -f volume-hostpath.yaml
```

***

## Read more

### [Rollback deployments in Kubernetes](https://learnk8s.io/kubernetes-rollbacks)

### [Volumes kubernetes](https://kubernetes.io/docs/concepts/storage/volumes/)

