---
title: Apache Superset
description: 
published: true
date: 2023-08-16T13:25:08.041Z
tags: 
editor: markdown
dateCreated: 2023-08-16T13:25:08.041Z
---

# Apache Superset

Setup with docker compose according to [docs](https://superset.apache.org/docs/installation/installing-superset-using-docker-compose)

Runs on Nidavellir on 192.168.1.62:8088

Had to pull version 2.1.0 since latest is broken. This is set in the docker-compose file 'docker-compose-non-dev.yml' at the top.
Start with shell script 'start_superset_container.sh' in /opt/superset
```
docker-compose -f docker-compose-non-dev.yml pull
docker-compose -f docker-compose-non-dev.yml up -d
```