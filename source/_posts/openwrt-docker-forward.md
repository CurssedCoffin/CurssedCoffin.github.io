---
title: Openwrt下外部网络无法访问Docker内部容器
tags: [Openwrt, Docker, Network]
categories: [故障解决]
mathjax: false
date: 2025-09-02 18:25:46
---

# 简述
openwrt默认配置下可能存在docker0下的容器可以访问外部网络，但外部网络（LAN）无法访问容器的情况
<!-- more -->
# 解决
默认配置下Docker已允许br-lan接口访问内部容器，防火墙侧原因导致。在 网络 - 防火墙 - 常规设置 - 转发 处设置为 **接受** 即可。