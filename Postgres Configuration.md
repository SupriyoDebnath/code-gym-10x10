# Postgres Configuration

This file will guide you on how to setup, install and configure a production grade postgres database in a kubernetes cluster. We have the postgres-deployment.yaml under **yamls** folder, there you can find all postgres related specifications

## Create Kuberenetes Cluster

```sh
kind create cluster --name codegym-pgcluster --config postgres-cluster-config.yaml
```

## Install Postgress

```sh
kubectl apply -f postgres-deployment.yaml --context kind-codegym-pgcluster
```

## Check Configuration

```sh
kubectl cluster-info --context kind-codegym-pgcluster
ss -tulnp | grep 30432
kubectl get all
kubectl get pv
kubectl get pvc
psql -h **_[VM IP]_** -p 30432 -U postgres -d postgres
```
