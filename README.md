
## [Kubernetes Series](https://viblo.asia/s/kubernetes-series-bq5QL8QGlD8)

## [Chinh phục Kubernetes từ số 0](https://viblo.asia/s/chinh-phuc-kubernetes-tu-so-0-GJ59jLJaKX2)

## [K8S Basic - Kubernetes dành cho người mới bắt đầu](https://viblo.asia/s/k8s-basic-kubernetes-danh-cho-nguoi-moi-bat-dau-pgjLN088432)

## [Kubernetes Patterns](https://viblo.asia/s/kubernetes-patterns-aGK7jPPx5j2)

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

### [Faster way to switch between clusters and namespaces in kubectl](https://github.com/ahmetb/kubectx)

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

[Ansible RKE playbook](https://github.com/kloia/rke-ansible)

[KubeInit](https://github.com/Kubeinit/kubeinit)

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