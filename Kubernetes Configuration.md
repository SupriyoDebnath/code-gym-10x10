# Kubernetes Configuration

This file will guide you on how to setup, install and configure a production grade kubernetes cluster environment before installing or running applications

## Initial Cleanups

```sh
apt remove kubectl
```

## Install Kubectl

```sh
curl -L "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl" -o /usr/local/bin/kubectl
chmod +x /usr/local/bin/kubectl
```

## Check Configuration

```sh
kubectl version --client
kubectl cluster-info
```
