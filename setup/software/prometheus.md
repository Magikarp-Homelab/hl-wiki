---
title: Prometheus
description: Prometheus Setup and Guides
published: true
date: 2023-05-08T21:43:49.827Z
tags: 
editor: markdown
dateCreated: 2023-05-08T13:03:54.365Z
---

# Prometheus
Links:
* [Prometheus Proxmox VE Exporter](https://github.com/prometheus-pve/prometheus-pve-exporter)
* [Grafana Proxmox vis Prometheus](https://grafana.com/grafana/dashboards/10347-proxmox-via-prometheus/)
* [Quick Setup](https://prometheus.io/docs/prometheus/latest/getting_started/)

## Run
Start prometheus
```
cd /opt/prometheus
./start.sh
```

Start prometheus
```
cd /opt/prometheus/pve-exporter
./start.sh
```

## Notes
* Make a start script
* check options for hosting config file on github
    * together with grafana dashboards?
        * export dashboards
        * import dashboards
    * make push/pull scripts
        * shutdown prometheus service
        * pull git
        * replace config file
        * start prometheus