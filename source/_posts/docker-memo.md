---
title: docker-memo
date: 2024-04-15 09:58:44
tags:
---
### What

**container**

**image** 用来创建容器的模板。包含运行应用所需的一起：代码、运行时、库、环境变量和配置文件。

### How

**创建镜像**
 
- Dockerfile
- docker build `docker build -t <image-name> .`

**运行容器**

- docker run -d -p 80:80 \<image-name>
- `docker run -d -p 80:80 -v /path/to/host:/path/to/container <image-name>` 挂载卷

**查看容器**

- docker ps


**停止容器**

- docker stop <container-id>

**WebStorm 配置 Docker**

- Settings -> Build, Execution, Deployment -> Docker -> + -> TCP Socket -> Engine API URL: tcp://localhost:2375
