---
title: Grafana
description: Grafana Setup and Guides
published: true
date: 2023-07-05T20:22:26.635Z
tags: 
editor: markdown
dateCreated: 2023-05-16T13:02:52.812Z
---

# Grafana
Runs on svol port 3001. Data is mappen on a docker volume.

## Run
Start grafana
```
cd /opt/grafana
./run_grafana_9.5.2.sh
```

Script run_grafana_9.5.2.sh does:
```
docker run -d -p 3001:3000 --name=grafana -v grafana-storage:/var/lib/grafana grafana/grafana-enterprise:9.5.2
```