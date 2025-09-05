# Postgres Configuration

This file will guide you on how to setup, install and configure a production grade postgres database in a kubernetes cluster. We have the `postgres-deployment.yaml` under **yamls** folder, there you can find all postgres related specifications. Optionally, you can check the cluster configuration at `postgres-cluster-config.yaml`

## Create Kuberenetes Cluster

```sh
kind create cluster --name codegym-pgcluster --config postgres-cluster-config.yaml
```

## Install PostgreSQL

```sh
kubectl apply -f postgres-deployment.yaml --context kind-codegym-pgcluster
```

## Check Configuration

```sh
docker ps | grep codegym-pgcluster-control-plane
kubectl cluster-info --context kind-codegym-pgcluster
ss -tulnp | grep 30010
kubectl get all | grep postgres
kubectl get pv | grep postgres
kubectl get pvc | grep postgres
psql -h **_[VM IP]_** -p 30010 -U postgres -d postgres
```
