---
title: FAQ常见问题解答
sidebar_position: 1
---

# FAQ 常见问题解答

## 软件安装环境支持哪些系统？

dgiot 支持的操作系统：CentOS 7.6 和 7.9 版本。

## 是否支持国产操作系统？

企业版仅支持Centos7.6运行的硬件。

dgiot 已适配 ARM64 架构的麒麟系统，支持银河麒麟V10版本的运行，支持信创认证属于旗舰版物联网平台板块，若需要请联系商务咨询。

## 是否支持手机端小程序？

支持。可选购标准版微信小程序作为移动端数据查看。

## 是否支持 Docker 容器化部署？

dgiot 支持 Docker 容器化部署，但程序较老建议纯净服务器并在Centos7.9上安装运行。

## 是否支持集群部署？

dgiot企业版暂不支持集群部署。可联系咨询官方商务对接集群部署等大型项目。

## 软件安装需要的硬件配置？

下表列出了 dgiot 在不同点位数量下的完成数采功能最低硬件要求（使用 dgiot 数据处理功能，会额外消耗系统资源）。

| 监测点位数  | CPU核心  | 内存  | 硬盘   |
|--------|--------|-----|------|
| 1,000  | 4core  | 8G  | 512G |
| 3,000  | 8core  | 16G | 1T   |
| 5,000  | 16core | 32G | 1T*2 |

超过5,000 tags属于旗舰版定制功能。

## dgiot 是否有免费版本？

dgiot 官网下载安装包安装后，默认提供了DLT645、MODBUS-RTU、DLINK(MQTT)三类设备接入服务，其他协议咨询商务进行了解。开源平台设备接入量根据接入点位及复杂度而定，开源平台接入反馈最高达4,000台。

## dgiot 安装后如何访问？

dgiot 安装后，在浏览器访问该IP地址即可。

（开发者）最高权限用户名和密码为：`dgiot_dev/dgiot_dev`

## 软件支持采集哪些驱动？

请参考[数采插件列表](../docs/product_overview/plugin_list.md)

## 数据采集最低采集周期是多少？

dgiot 标准产品最低采集周期是 `50ms`，如果有更低的采集频率需求，可联系商务进行旗舰版需求对接。

## 是否支持设备反控？

支持。dgiot 支持设备反控功能，提供[RestAPI](https://docs.emqx.com/zh/dgiot/latest/api/api-docs.html#tag/rw)、[MQTT](../configuration/north-apps/mqtt/api.md#写-tag)、[边缘计算结果反控](../streaming-processing/sink/neuron.md)等多种设备反控方式，支持工业设备智能控制决策。

## 是否支持自行开发驱动？

支持。dgiot 可以分为核心框架和多种可插拔模块，南向、北向的插件模块可动态添加和删除。dgiot 提供基于C语言的驱动开发 SDK。

## 最多支持多少个南向驱动同时采集？

在硬件性能足够的情况下，建议不超过100个南向驱动。

## 最多支持多少个数据点位同时采集？

在硬件性能足够的情况下，建议不超过10万个数据采集点。如果数据点位数量超过10万个，可通过 Docker 方式在单台服务器部署多个 dgiot 实例。

## 支持采集西门子200、200smartPLC、1500吗？

支持西门子全系列PLC的数据采集。

## 是否支持离线缓存数据？

支持。dgiot 支持北向 MQTT 数据上报网络中断时，将采集到的数据缓存到本地，网络恢复后再将缓存的数据上传到云端。

## 是否支持将数据存储在本地？

支持。dgiot 通过数据处理功能，可将数采数据存储到本地数据库，支持的数据库类型有 MySQL、PostgreSQL、SQLite、SQLServer、Oracle、InfluxDB v1、InfluxDB v2等。详情请参考[数据存储到SQL](../streaming-processing/sink/sql.md)、[数据存储到InfluxDB v1](../streaming-processing/sink/influx.md)、[数据存储到InfluxDB v2](../streaming-processing/sink/influx2.md)。

## 如何将 Modbus TCP 驱动采集数据转发到 MQTT 服务器？

在**数据采集**->**北向应用**页面，添加 MQTT 插件，并添加订阅，将 Modbus TCP 驱动的采集 group 添加进来。

## dgiot 版本升级后，如何快速迁移配置？

配备一键升级脚本。将新的编译包导入填入MD5密钥即可自动升级，数据无需迁移实现热更新。

## 是否支持视频数据接入？

dgiot 支持将对接RTSP流，监控设备需配置好推流，平台提供画面观看等服务。

## 是否支持获取数据库数据？

支持。dgiot 支持将数据库MySQL、SQL Server、PostgreSQL、SQLite中的数据进行采集，并进行分析、存储及转发。

## 是否支持获取文件数据？

支持。dgiot 支持将txt、csv、json等格式文件中的数据进行采集，并进行分析、存储及转发。

## 是否支持AI、ML 集成分析？

支持。dgiot 支持用户自定义函数扩展和 AI 算法集成，提供智能数据分析能力。支持iframe嵌套网页，或通过nginx进行代理。
