---
title: Wiki.js
description: Wikijs Setup
published: true
date: 2023-05-05T10:31:32.912Z
tags: 
editor: markdown
dateCreated: 2023-05-05T10:31:32.912Z
---

# Wiki.js
[Docs](https://docs.requarks.io/)
The wiki is setup with Github. Every 5 Minutes it sync with the repo. [Repo](https://github.com/Magikarp-Homelab/hl-wiki)

## Setup
[Docs](https://docs.requarks.io/)

### Create the containers
```
docker create --name=db -e POSTGRES_DB=wiki -e POSTGRES_USER=wiki -e POSTGRES_PASSWORD_FILE=/etc/wiki/.db-secret -v /etc/wiki/.db-secret:/etc/wiki/.db-secret:ro -v pgdata:/var/lib/postgresql/data --restart=unless-stopped -h db --network=wikinet postgres:11
docker create --name=wiki -e DB_TYPE=postgres -e DB_HOST=db -e DB_PORT=5432 -e DB_PASS_FILE=/etc/wiki/.db-secret -v /etc/wiki/.db-secret:/etc/wiki/.db-secret:ro -e DB_USER=wiki -e DB_NAME=wiki -e UPGRADE_COMPANION=1 --restart=unless-stopped -h wiki --network=wikinet -p 80:3000 -p 443:3443 ghcr.io/requarks/wiki:2
docker create --name=wiki-update-companion -v /var/run/docker.sock:/var/run/docker.sock:ro --restart=unless-stopped -h wiki-update-companion --network=wikinet ghcr.io/requarks/wiki-update-companion:latest
```

### Start the containers
```
docker start db
docker start wiki
docker start wiki-update-companion
```