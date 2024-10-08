---
title: 运维指南
sidebar_position: 1
---

# 运维指南

本章节旨在帮助管理员和运维人员有效地管理和维护DGIOT。在本章节中，我们将探讨各种管理任务，并提供全面的指导和最佳实践，以确保您的DGIOT物联网平台平稳、高效地运行。

## 登录

打开google或其他浏览器，输入运行 dgiot 的网关地址和端口号，即可进入到管理控制台页面，默认端口号为 8085。

访问地址，http://x.x.x.x 其中，x.x.x.x 代表安装物联网平台安装的IP地址。

页面打开后，进入登录界面，用户可使用初始用户名与密码登录（管理员 用户名：dgiot_dev，管理员密码：dgiot_dev）。

如果页面无法打开，请在终端执行以下指令进行检测：

* 使用 `ping` 命令测试网络是否能通。
* 使用 `telnet` 命令测试端口1883、18083、能否访问。
* 执行如下指令查看“dgiot”的进程状态。

```
$ systemctl status dgiot
```