---
title: "嗨！我是**，这是我的看片神器~"
published: 2025-09-24
pinned: false
description: "这是我的看片神器~"
tags: [Emby, Docker, docker-compose]
category: Emby
licenseName: "CC BY 4.0"
author: "YlovexLN"
draft: false
date: 2025-09-24
image: https://qiniu.ylovexln.top/images/Emby-Docker.png
pubDate: 2025-09-24
---

## 我是**，这是我的看片神器~

封面使用的是amilys大佬的Emby开心版[Docker镜像](https://hub.docker.com/r/amilys/embyserver)来部署使用

最主要的是自带[emby-erx](https://github.com/amilys/emby-erx)美化插件，效果图如封面

建议使用 `docker-compose.yml` 文件便于后期的修改

直接上 `docker-compose.yml`

```yml
services:
  emby:
    image: amilys/embyserver:latest #amilys大佬的开心版镜像
    container_name: embyserver
    restart: always
    network_mode: host #bridge也可以根据使用需求
    environment:
      - TZ=Asia/Shanghai
    volumes:
      - ./config:/config  #配置路径，根据实际路径填写
      - ./media:/media #资源路径，根据实际路径填写
    ports:
      - 8096:8096
```

运行 `docker-compose up -d`

访问 `http://设备ip:8096` 即可进入Emby-Web页面

<!--
本页封面：[Pixiv-宮水の巫女](https://www.pixiv.net/artworks/60268880)
-->
