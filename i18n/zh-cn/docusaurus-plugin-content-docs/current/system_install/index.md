---
title: Centos部署
sidebar_position: 1
---

## 一键部署

为快速在服务器搭建dgiot物联网平台运行所需的环境，DGIOT耗时3个月完成一键式部署脚本的编写。通过一键式部署脚本可在6分钟内部署好平台并正常使用。
鉴于不同操作系统环境部署适配的差异，暂未对所有系统进行适配。

---

## 操作系统
**Centos7.6**  或  **Centos7.9** 

项目中服务器为提供**刀片机**或**服务器**，系统为**独立部署**的**Centos7.9**操作系统。通过脚本自动配置环境变量、插件、数据库等一系列应用的安装与调试。

---

## 数据库
| 数据类型 | 名称 | 说明 |
|-----|----|----|
|  配置数据  |  postgres  |  关系数据库  |
|  状态数据  |  tdengine |  时序数据库  |
|  文件数据   | go-fast |   对象存储数据库 |

---

## 防火墙

系统需要开启端口进行数据传输，云服务默认没有开启对应端口，需要在防火墙上添加安全规则，操作如下 需要开启的端口列表如下：

| 端口名   | 连接地址 | 说明 |
|-------|----|----|
| 80    | http://prod.dgiotcloud.cn/ |  dgiot http连接  |
| 443   | https://prod.dgiotcloud.cn/ |  dgiot https证书连接  |
| 1883  | tcp://prod.dgiotcloud.cn:1883 |   mqtt tcp连接 |
| 8883  | tcp://prod.dgiotcloud.cn:8883  |   mqtt tcp 证书连接 |
| 8083  | ws://prod.dgiotcloud.cn:8083/mqtt |  mqtt websocket连接  |
| 8084  | wss://prod.dgiotcloud.cn:8084/mqtt | mqtt websocke证书连接   |

---

## 部署脚本

复制以下代码进入服务器终端执行：

```
wget -qO dgiot_install.sh https://gitee.com/dgiiot/dgiot/raw/master/dgiot_install.sh  && sh dgiot_install.sh
```

等待6分钟左右完成部署跳出**dgiot single deploy end**后, 视为部署成功：
![一键部署](https://dgiot-1253666439.cos.ap-shanghai-fsi.myqcloud.com/dgiot_enterprise/zh/system_install/centos/centos%E4%B8%80%E9%94%AE%E9%83%A8%E7%BD%B2.png  "一键部署")

![部署成功](https://dgiot-1253666439.cos.ap-shanghai-fsi.myqcloud.com/dgiot_enterprise/zh/system_install/centos/cenoes%E9%83%A8%E7%BD%B2%E5%AE%8C%E6%88%90.png  "部署成功")

---

## 其他

更多部署服务，请点击[一键部署](https://doc.dgiotcloud.cn/docs/product_doc/docs/deployment_details/)查看。

