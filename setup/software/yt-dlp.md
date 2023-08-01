---
title: yt-dlp
description: Youtube downloader
published: true
date: 2023-08-01T14:42:38.787Z
tags: 
editor: markdown
dateCreated: 2023-08-01T14:35:07.890Z
---

# yt-dlp
Installed on Njord /opt/crawl. Requires python & to install pip
```
apk add py3-pip
pip install yt-dlp
```

[Usage](https://github.com/yt-dlp/yt-dlp)
Basic
```
yt-dlp URL
```

To get files from Njord to Windows PC:
Since winscp doesn't work because of weird ssh key formats
```
scp root@192.168.1.61:/opt/crawl/file.mp4 .
```