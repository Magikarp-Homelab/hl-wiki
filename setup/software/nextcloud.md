---
title: NextCloud
description: 
published: true
date: 2023-08-01T14:12:29.853Z
tags: 
editor: markdown
dateCreated: 2023-07-31T23:54:40.907Z
---

# Nextcloud
Cloud Service runs as a docker container on Nidavellir on 192.168.1.61 (Njord). Setup as described on [Github](https://github.com/nextcloud/all-in-one#how-to-use-this).

WebGUI runs on port 8080.

Run script in /opt/nextcloud/run_nextcloud.sh
Note: had to remove sudo, doesn't exist on alpine
```
# For Linux and without a web server or reverse proxy (like Apache, Nginx, Cloudflare Tunnel and else) already in place:
sudo docker run \
-d
--sig-proxy=false \
--name nextcloud-aio-mastercontainer \
--restart always \
--publish 80:80 \
--publish 8080:8080 \
--publish 8443:8443 \
--volume nextcloud_aio_mastercontainer:/mnt/docker-aio-config \
--volume /var/run/docker.sock:/var/run/docker.sock:ro \
nextcloud/all-in-one:latest
```

Nextcloud borg password:
```
statue shortlist virus carnival bodacious staff scabby tank
```

Nextcloud backup encryption:
```
dc80ca480639c50fc2355dd26789548d5a099705b60f1755
```