---
title: CT Templates
description: List of created CT Tempaltes
published: true
date: 2023-05-16T20:38:44.026Z
tags: 
editor: markdown
dateCreated: 2023-05-04T14:31:20.529Z
---

# CT Templates
* alpine-docker
    * alpine 3.17
    * docker
    * docker compose
    * vim
   
# setup new alpine container
if there's no template:

```
apk update

# ssh
apk add openssh
rc-update add sshd
service sshd start

# vim
apk add vim

# docker & docker-compose
apk add docker
addgroup username docker

rc-update add docker default
service docker start

apk add docker-compose
```