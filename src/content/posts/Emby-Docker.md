---
title: "我是**，这是我的看片神器~"
published: 2025-09-24
pinned: false
description: "这是我的看片神器Emby"
tags: [Emby, Docker,docker-compose]
category: Emby
licenseName: "CC BY 4.0"
author: "YlovexLN"
draft: false
date: 2025-09-24
image: https://qiniu.ylovexln.top/images/60268880_p0.jpg
pubDate: 2025-09-24
---

## 我是**，这是我的看片神器~

本页使用的是amilys大佬的Emby开心版Docker镜像来部署使用

建议使用 `docker-compose.yml` 文件便于后期的修改

直接上 `docker-compose.yml`

```yml
services:
  emby:
    image: amilys/embyserver:beta #amilys大佬的开心版镜像
    container_name: embyserver
    restart: always
    network_mode: host #bridge也可以根据使用需求
    environment:
      - PUID=0
      - PGID=0
      - TZ=Asia/Shanghai
    volumes:
      - ./config:/config  #配置路径，根据实际路径填写
      - ./media:/media #资源路径，根据实际路径填写
    ports:
      - 8096:8096
```

运行 `docker-compose up -d`

访问 `http://设备ip:8096` 即可进入Emby-Web页面
