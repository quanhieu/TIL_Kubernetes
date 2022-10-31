
## [Kubernetes Series](https://viblo.asia/s/kubernetes-series-bq5QL8QGlD8)

## [Chinh phục Kubernetes từ số 0](https://viblo.asia/s/chinh-phuc-kubernetes-tu-so-0-GJ59jLJaKX2)

## [K8S Basic - Kubernetes dành cho người mới bắt đầu](https://viblo.asia/s/k8s-basic-kubernetes-danh-cho-nguoi-moi-bat-dau-pgjLN088432)

## [Kubernetes Patterns](https://viblo.asia/s/kubernetes-patterns-aGK7jPPx5j2)

## [Xuanthu lab Kubernetes](https://xuanthulab.net/kubernetes/)

## Youtube

- [Xuanthulab](https://www.youtube.com/playlist?list=PLwJr0JSP7i8D-QS50lYsXpAg-jYoqxMVy)

- [FullstacKAGE](https://www.youtube.com/playlist?list=PL28xQzrHZLIWeRkVqP4NMpdySu279CoQj)

<br />

## Tool

### [Kube color](https://github.com/hidetatz/kubecolor)

> sudo apt -y install kubecolor

### [k9s](https://k9scli.io/)

> sudo apt install k9s

### [Docker color](https://github.com/devemio/docker-color-output)

```
sudo add-apt-repository ppa:dldash/core
sudo apt update
sudo apt install docker-color-output
```

### [NFS Storage](https://viblo.asia/p/k8s-phan-3-cai-dat-storage-cho-k8s-dung-nfs-RnB5pAw7KPG)

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
