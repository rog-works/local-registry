Local docker registry
===

# Requirements

* Docker
* docker-compose

# Environment

* host: 192.168.33.12

# Usege

```shell
$ cd /path/to/workspace

$ git clone git@github.com/rog-works/local-registry.git 

$ cd local-registry

$ docker-compose up -d
```

* for Client

```shell
$ vim /etc/docker/daemon.json
{ "insecure-registries": ["192.168.33.12:5001"] }

$ vim docker-compose.yml
version: '3'
services:
  app:
    image: 192.168.33.12:5001/hoge/fuga:latest

$ docker-compose build app

$ docker-compose push app
```
