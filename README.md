# kubectl-topnode

## Features

A simple bash script to filter 'kubectl top pods' by node

## Setup

```bash
curl -Lo kubectl-topnode https://github.com/stelios9t/kubectl-topnode/raw/main/kubectl-topnode
sudo mv kubectl-topnode /usr/local/bin/
chmod +x /usr/local/bin/kubectl-topnode
```

## Usage

```bash
kubectl get nodes
NAME                 STATUS   ROLES           AGE   VERSION
kind-control-plane   Ready    control-plane   57m   v1.33.1
kind-worker          Ready    <none>          56m   v1.33.1
kind-worker2         Ready    <none>          56m   v1.33.1

kubectl-topnode kind-worker
default              test-6bc6b589d7-75hrv                        0m           13Mi
default              test-6bc6b589d7-pf6xv                        0m           13Mi
default              test-6bc6b589d7-psxbr                        0m           13Mi
kube-system          kindnet-brsst                                2m           12Mi
kube-system          kube-proxy-5brhq                             2m           12Mi
kube-system          metrics-server-757fd7d849-4g9jr              8m           23Mi

kubectl-topnode kind-worker3
Error from server (NotFound): nodes "kind-worker3" not found
```

## Alias

```bash
echo "alias ktn='kubectl-topnode'" >> ~/.bashrc
source ~/.bashrc

ktn kind-worker
default              test-6bc6b589d7-75hrv                        0m           13Mi
default              test-6bc6b589d7-pf6xv                        0m           13Mi
default              test-6bc6b589d7-psxbr                        0m           13Mi
kube-system          kindnet-brsst                                2m           12Mi
kube-system          kube-proxy-5brhq                             2m           12Mi
kube-system          metrics-server-757fd7d849-4g9jr              8m           23Mi
```
