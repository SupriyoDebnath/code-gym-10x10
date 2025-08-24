# Docker Configuration

This file will guide you on how to setup, install and configure a production grade docker environment before installing orchestrators or running applications

## Initial Cleanups

```sh
apt remove docker docker.io containerd runc
apt remove docker-engine
```

## Install Docker

```sh
curl -fsSL https://get.docker.com -o get-docker.sh
DRY_RUN=1 sh ./get-docker.sh
sh get-docker.sh
```

## Configure Docker to run on System Boot

```sh
systemctl enable docker.service
systemctl enable containerd.service
```

## Install Docker Machine

```sh
curl -L https://github.com/docker/machine/releases/download/v0.16.2/docker-machine-$(uname -s)-$(uname -m) -o /usr/local/bin/docker-machine
chmod +x /usr/local/bin/docker-machine
```

## Install Docker Compose

```sh
curl -L https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m) -o /usr/local/bin/docker-compose
chmod +x /usr/local/bin/docker-compose
```

## Check Configuration

```sh
docker version
docker run hello-world
docker-machine version
docker-compose version
```
