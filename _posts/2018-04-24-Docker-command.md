---
layout: post
title:  "Docker基础命令"
categories: Docker
tags:  Docker基础
author: PPJoin
---

* content
{:toc}

安装完 Docker 后,可以安装 `portainer` 来进行管理,当然也还是要熟悉一下基本命令.

## 搜索所有 centos 镜像
```bash
docker search centos
```




## 下载 centos 镜像

```sh
docker pull hidetarou2013/centos6-apache
```

## 查看所有镜像

```sh
docker images
```

## 删除某镜像

```sh
docker rmi hidetarou2013/centos6-apache
```

## 创建数据卷

名称为 `portainer_data` ,里面的文件一般在 `/var/lib/docker/volumes/` 目录下,可以供容器挂载
```sh
docker volume create portainer_data;
```

## 从镜像创建容器

容器名 `centos` 端口 `80` , `1013` , `55555` , `1194` , `8888` , 基础镜像 `hidetarou2013/centos6-apache`

```sh
docker run --name=centos -d -p 80:80 -p 1013:1013 -p 55555:55555 -p 1194:1194 -p 8888:8888 hidetarou2013/centos6-apache
```

## 列出所有容器

```sh
docker ps -a
```

## 进入某容器的命令行

```sh
docker exec -it centos /bin/sh
```

## 停止容器

```sh
docker stop centos
```

## 删除容器

```sh
docker rm -f centos
```
