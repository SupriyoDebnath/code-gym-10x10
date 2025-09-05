# Redis Configuration

This file will guide you on how to setup, install and configure a production grade redis cache in a kubernetes cluster. We have the redis-deployment.yaml under **yamls** folder, there you can find all redis related specifications. Optionally, you can check the cluster configuration at `redis-cluster-config.yaml`

## Create Kuberenetes Cluster

```sh
kind create cluster --name codegym-rdcluster --config redis-cluster-config.yaml
```

## Install Redis

```sh
kubectl apply -f redis-deployment.yaml --context kind-codegym-rdcluster
```

## Check Configuration

```sh
docker ps | grep codegym-rdcluster-control-plane
kubectl cluster-info --context kind-codegym-rdcluster
ss -tulnp | grep 30020
kubectl get all | grep redis
kubectl get pv | grep redis
kubectl get pvc | grep redis
redis-cli -h **_[VM IP]_** -p 30020
```
