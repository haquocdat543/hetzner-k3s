# hetzner-k3s
Setup 6 nodes k8s cluster on hetzner cloud with just ~ `32,1` euros per month

one node is ~ `5,25` euros per month
### 1. Prerequisites
* A verified Hetzner account
* [hetzner-api-token](https://docs.hetzner.com/cloud/api/getting-started/generating-api-token/) 
* [hetzner-k3s](https://github.com/vitobotta/hetzner-k3s) in `Installation` part
* [kubectl](https://kubernetes.io/docs/tasks/tools/)
### 2. Get started
#### 1. Review config file
* Replace `hetzner token` with your `real token` in `config file`
* version: v1.29.1+k3s2
* public_ssh_key_path: "~/.ssh/id_rsa.pub"
* private_ssh_key_path: "~/.ssh/id_rsa"
* use_ssh_agent: false
* masters_pool:
  * instance_type: cx21
  * instance_count: 3
  * location: nbg1
* worker_node_pools:
* - name: small-static
  * instance_type: cx21
  * instance_count: 3
  * location: nbg1
  * image: debian-11
  * autoscaling:
    * enabled: true
    * min_instances: 0
    * max_instances: 3

* Get prices and node types [here](https://www.hetzner.com/cloud/)
#### 2. Create cluster
Replace `config file` with your real config file
```
hetzner-k3s create my-config.yaml
```
After successfully created cluster. `kubeconfig` file will be downloaded in your current directory
#### 3. config cluster
```
export KUBECONFIG=./kubeconfig

```
#### 4. Test cluster
```
kubectl get nodes
```
#### 5. Deploy workloads

#### 6. Delete cluster
Replace `config file` with your real config file
```
hetzner-k3s delete my-config.yaml
```
