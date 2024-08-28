---
title: Modbus RTU
sidebar_position: 1
---

Modbus RTU 是 Modbus 协议的一种版本，它是基于串行通信的协议。
与 Modbus TCP 协议不同，Modbus RTU 通常用于连接在工厂生产线上的传感器、执行器和其他控制设备，是一种快速、可靠、灵活的串行通信协议，提供了可靠的数据传输和控制功能。

Modbus RTU 协议采用二进制编码，可以在 RS-232、RS-485 或其他串行通信介质上传输数据，dgiot 的 Modbus RTU 插件增加了基于以太网 TCP 的实现，通过 DTU 设备，可实现远端设备的数据采集与控制。

---

#添加插件

在 **配置** -> **南向设备**，点击添加设备来创建设备节点，输入插件名称，插件类型选择 **Modbus RTU** 启用插件。

!][11](https://dgiot-1253666439.cos.ap-shanghai-fsi.myqcloud.com/dgiot_enterprise/zh/data_acquisition/modbus-rtu/1.modbusrtu.png)