---
title: Prometheus
description: Prometheus Setup and Guides
published: true
date: 2023-07-05T20:25:26.952Z
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
./build_and_start_container.sh
```

Script build_and_start_container.sh does:
```
docker stop prometheus
docker build -t prometheus .
docker run --rm --name prometheus -d -p 9090:9090 prometheus
```

Start pve-exporter
```
cd /opt/prometheus/pve-exporter
./run_pve_exporter.sh
```

Script run_pve_exporter.sh does:
```
docker run --name prometheus-pve-exporter -d -p 9221:9221 -v /opt/prometheus/pve-exporter/pve.yml prompve/prometheus-pve-exporter
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