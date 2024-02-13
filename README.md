# hetzner-k3s
Setup k8s cluster on hetzner cloud

This guide is based on [vitobotta-guide](https://github.com/vitobotta/hetzner-k3s). Please view their guide first.
### 1. Prerequisites
* A verified Hetzner account
* [hetzner-api-token](https://docs.hetzner.com/cloud/api/getting-started/generating-api-token/) 
* [hetzner-k3s](https://github.com/vitobotta/hetzner-k3://github.com/vitobotta/hetzner-k3s) in `Installation` part
* [kubectl](https://kubernetes.io/docs/tasks/tools://kubernetes.io/docs/tasks/tools/)
### 2. Get started
#### 1. Review config file
* Replace `hetzner token` with your `real token` in `config file`
* Replace `k3s-version` with your `version` that you desire
```
hetzner-k3s releases
```
* Check for other configuration base on `default-config.yaml`. Other this link [default-config-file](https://github.com/vitobotta/hetzner-k3://github.com/vitobotta/hetzner-k3s) in `Create a cluster` part
#### 2. Create cluster
Replace `config file` with your real config file
```
hetzner-k3s create <config file>
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
hetzner-k3s delete <config file>
```
