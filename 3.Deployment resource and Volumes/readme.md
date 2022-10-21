
## [Kubernetes Series - Bài 6 - Volume: gắn disk storage vào container](https://viblo.asia/p/kubernetes-series-bai-6-volume-gan-disk-storage-vao-container-OeVKB6rrKkW)

```yaml
- Apply
k apply -f ./deployment.yml

- Apply without manifest
kubectl set image deploy nginx-deployment nginx=nginx:1.14

- Get history
k rollout history deploy/nginx-deployment

- Rollout
k rollout undo deploy nginx-deployment

- Rollout by version
k rollout history deploy/nginx-deployment --revision=2

- Get pods
k get pods

- View manifest in pod
k get rs nginx-deployment-547d878d89 -o yaml

- Restart
k rollout restart deploy nginx-deployment

- Describe deployment
k describe deploy nginx-deployment

- Describe pod
k describe po nginx-deployment nginx-deployment-8498fb578b-8674r

- Install git for minikube
docker ps
docker exec -it 28521fb2a846 sh
apt update && apt install git -y

- Forward pod
k get pods
k port-forward pod/fortune 8888:80

- Exec pod
k exec -it fortune -- sh
k exec -it fortune -c web-server -- sh
```
