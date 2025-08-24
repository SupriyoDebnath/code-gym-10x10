# VM Configuration

This file will guide you on how to setup and configure a production grade virtual machine before installing applications or orchestrators

## VM hosted by Hostinger VPS

> **VM for Databases** OS Ubuntu 24.04 LTS, 4core CPU, 16GB RAM, 200GB Disk Space

## Initial Cleanups

```sh
apt update
apt upgrade
apt autoremove
```

## Check Configuration

```sh
lsb_release -a
uname -a
```
