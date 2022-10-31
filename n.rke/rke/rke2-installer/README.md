### A Simple Ansible Playbook for Installation RKE2 Cluster + Let's Encrypt ClusterIssuer / TLS + Rancher Installation

&nbsp;

#### 1. Inventory

&nbsp;

```yaml
all:
  children:
    rke2-cluster-masters:
      hosts:
        10.0.3.11:
        10.0.3.12:
        10.0.3.13:
    rke2-cluster-workers:
      hosts:
        10.0.3.21:
        10.0.3.22:
        10.0.3.23:
  vars:
    ansible_user: 'root'
    #ansible_password: 'debian11'

rke2-cluster:
  children:
    rke2-cluster-masters:
    rke2-cluster-workers:
```

&nbsp;

&nbsp;

#### 2. Variables

&nbsp;

```yaml
## RKE2 Server Variables
# ./vars/all.yml

rke2_version: v1.23.5+rke2r1

cert_manager_version: v1.5.1

# The name of the cluster to be added to the Rancher.
cluster_name: rke2-test-cluster

# Cloudflare Cluster Issuer
CF_api_token: ''
CF_email: ''
CF_base_domain: 'testcluster.basitbir.site'

rancher_version: v2.6.4
rancher_domain: "rancher.{{ CF_base_domain }}"
rancher_replicas: '1'
#rancher_password: '6vluyynACmXWOrcLpcC0XH34z231MD8sz'
```

&nbsp;

&nbsp;

#### 3. Install RKE2 Cluster

&nbsp;

```bash
# Install ansible
apt update && \
apt install -y \
      ansible \
      sshpass

# Install Ansible requirements
ansible-galaxy install -r requirements.yml

# Run playbook
ansible-playbook -vv rke2-cluster.yml
```

&nbsp;

&nbsp;

#### 4. Purge RKE2 Cluster

&nbsp;

```bash
ansible-playbook -vv setup-cluster/purge-cluster.yml
```

&nbsp;

&nbsp;
