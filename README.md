## [Kubernetes Overview Diagrams](https://shipit.dev/posts/kubernetes-overview-diagrams.html)

### Trịnh Quốc Việt

## [Chinh phục Kubernetes từ số 0](https://viblo.asia/s/chinh-phuc-kubernetes-tu-so-0-GJ59jLJaKX2)

## [K8S Basic - Kubernetes dành cho người mới bắt đầu](https://viblo.asia/s/k8s-basic-kubernetes-danh-cho-nguoi-moi-bat-dau-pgjLN088432)

### Quân Huỳnh
## [Kubernetes Series](https://viblo.asia/s/kubernetes-series-bq5QL8QGlD8)

## [Kubernetes Patterns](https://viblo.asia/s/kubernetes-patterns-aGK7jPPx5j2)

## [Kubernetes Practice](https://viblo.asia/s/kubernetes-practice-rLZDX4DgZk0)

## [Service Mesh on Kubernetes](https://devopsvn.tech/service-mesh-on-kubernetes)

<br />

## [Xuanthu lab Kubernetes](https://xuanthulab.net/kubernetes/)

## Youtube

- [Xuanthulab](https://www.youtube.com/playlist?list=PLwJr0JSP7i8D-QS50lYsXpAg-jYoqxMVy)

- [FullstacKAGE](https://www.youtube.com/playlist?list=PL28xQzrHZLIWeRkVqP4NMpdySu279CoQj)

  + [Google Kubernetes Engine là gì? Kiến thức cơ bản (GKE CI/CD Phần 1)](https://www.youtube.com/watch?v=TQf3mpngNXE)
  + [Hands-on Google Kubernetes Engine, Infrastructure as Code, GitHub Actions (Part II)](https://www.youtube.com/watch?v=kaXEuToIFik)


<br />

## Tool

### [Kube color](https://github.com/hidetatz/kubecolor)

```
sudo apt -y install kubecolor
```

Or

```
VERSION=latest      
go install -ldflags="-X main.Version=${VERSION}" github.com/kubecolor/kubecolor/cmd/kubecolor@${VERSION}
```

### [k9s](https://k9scli.io/)

```
sudo apt install k9s
```

Or

```
curl -sS https://webi.sh/k9s | sh
```

### [Docker color](https://github.com/devemio/docker-color-output)

```
sudo add-apt-repository ppa:dldash/core
sudo apt update
sudo apt install docker-color-output
```

### [NFS Storage](https://viblo.asia/p/k8s-phan-3-cai-dat-storage-cho-k8s-dung-nfs-RnB5pAw7KPG)

### [Ceph Storage](https://github.com/ceph/ceph)

### [Long horn](https://viblo.asia/p/k8s-phan-4-cai-dat-storage-cho-k8s-dung-longhorn-1Je5EAv45nL)

### [Harbor Registry](https://viblo.asia/p/k8s-phan-11-xay-dung-private-docker-registry-phuc-vu-cicd-voi-kubernetes-Qbq5QRQRKD8)

### [Rancher](https://viblo.asia/p/k8s-phan-2-cai-dat-kubernetes-cluster-va-rancher-m68Z0BL95kG)

### [Self-hosted PaaS for Kubernetes - Otomi](https://otomi.io/)

### [Argo CD](https://github.com/argoproj/argo-cd/)


### [Switch between clusters and namespaces in kubectl by kubectx + kubens](https://github.com/ahmetb/kubectx)

<br />

## Setup k8s clusters

[Comparison of the Kubernetes Engines](https://www.kloia.com/blog/comparison-of-the-kubernetes-engines)

```yml
Tools on the Cloud: EKS, AKS, GKE, Kops

Tools for On-Premise Environments: Kubespray, Kubeadm, RKE (RKE1 | RKE2), K3S
```

[Tự động cài đặt Kubernetes cluster với RKE, rút gọn kubectl command với kubectx và kubens](https://viblo.asia/p/tu-dong-cai-dat-kubernetes-cluster-voi-rke-rut-gon-kubectl-command-voi-kubectx-va-kubens-ByEZkoO2ZQ0)

[Hướng dẫn cách sử dụng ssh-copy-id để copy public key lên server](https://viblo.asia/p/huong-dan-cach-su-dung-ssh-copy-id-de-copy-public-key-len-server-bJzKmVjDZ9N)

### Setup k8s by Ansible + RKE2

[rke2-ansible](https://github.com/rancherfederal/rke2-ansible)

[ansible-role-rke2](https://github.com/lablabs/ansible-role-rke2)

### Setup k8s by Ansible + RKE

[DEPLOY A KUBERNETES CLUSTER USING ANSIBLE](https://buildvirtual.net/deploy-a-kubernetes-cluster-using-ansible/)
  _ [github here](https://github.com/buildvirtual-git/kubernetes/tree/main/ansible-deploy-k8s)

[Kubespray](https://github.com/kubernetes-sigs/kubesprayhttps://github.com/kloia/rke-ansible)

[Ansible RKE playbook - vagrant](https://github.com/LukeMwila/local-kubernetes-setup-with-rke-and-vagrant)

[Ansible role to deploy Kubernetes using Rancher Kubernetes Engine](https://github.com/cedadev/rke-ansible)

[Ansible RKE playbook - aws](https://github.com/kloia/rke-ansible)

[KubeInit](https://github.com/Kubeinit/kubeinit)

<br />

## Aliases

```
# kubecolor
alias k="kubecolor"

# kubernetes
# alias k='kubectl'
alias ku='kubectl'

# minikube
alias m='minikube'
alias mini='minikube'

# docker
di() {
  docker images "$@" | docker-color-output
}

dps() {
  docker ps "$@" | docker-color-output
}

dcps() {
  docker compose ps "$@" | docker-color-output
}
```

<br />

## Install k8s

```
# 1. .Download the latest release
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"

# 2. Download the kubectl checksum file
curl -LO "https://dl.k8s.io/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl.sha256"

# 2.1. Validate the kubectl binary
echo "$(cat kubectl.sha256)  kubectl" | sha256sum --check

#. 3. Install kubectl
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl

# 4. Test to ensure the version you installed is up-to-date
kubectl version --client --output=yaml  
```

## Instal minikube

```
# 1. Download and install minikube
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube

# 2. Start minikube
minikube start

#. 3. Minikube dashboard
minikube dashboard
```
