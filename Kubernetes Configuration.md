# Kubernetes Configuration

This file will guide you on how to setup, install and configure a production grade kubernetes cluster environment before installing or running applications. We will use **`kind`** for running kubernetes cluster

## Initial Cleanups

```sh
apt remove kubectl
```

## Install Kubectl

```sh
curl -L "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl" -o /usr/local/bin/kubectl
chmod +x /usr/local/bin/kubectl
```

## Install Kind

```sh
curl -L "https://kind.sigs.k8s.io/dl/v0.29.0/kind-linux-amd64" -o /usr/local/bin/kind
chmod +x /usr/local/bin/kind
kind create cluster --name hello-world
```

## Check Configuration

```sh
kubectl version --client
kubectl cluster-info
kubectl get all
```
