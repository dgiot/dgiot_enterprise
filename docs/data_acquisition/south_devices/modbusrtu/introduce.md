---
title: 协议介绍
sidebar_position: 1
---

Modbus是一种串行通信协议，由Modicon公司（现为施耐德电气Schneider Electric）于1979年发布，旨在为可编程逻辑控制器（PLC）提供通信支持。
如今，Modbus已经成为工业领域通信协议的业界标准，广泛应用于工业电子设备之间的连接。Modbus协议具有免费、易于部署和维护、支持多种电气接口和介质传输等特点，使得其成为工业控制系统中的首选通信协议。

Modbus RTU 协议采用二进制编码，可以在 RS-232、RS-485 或其他串行通信介质上传输数据，dgiot 的 Modbus RTU 插件增加了基于以太网 TCP 的实现，通过 DTU 设备，可实现远端设备的数据采集与控制。

---
![introduce](https://dgiot-1253666439.cos.ap-shanghai-fsi.myqcloud.com/dgiot_enterprise/zh/data_acquisition/modbus-rtu/introduce/modbusrtu.png)
## **DGIOT物联网优势**
![advantage](https://dgiot-1253666439.cos.ap-shanghai-fsi.myqcloud.com/dgiot_enterprise/zh/data_acquisition/modbus-rtu/introduce/dgiot_advantage.png)
## **Modbus协议特点**
1. **协议开放**：Modbus是一种开放标准的通信协议，可以免费使用，无需支付任何费用。
2. **广泛支持**：Modbus可以支持多种电气接口，如RS-232、RS-485等，还可以在各种介质上传输，如双绞线、光纤、无线等。
3. **简单易用**：Modbus的帧格式简单，易于理解和开发。且在排查问题时可以通过报文数据做出快速判断。
4. **报文校验**：Modbus协议还具有较好的可靠性，通过数据校验和主从方式定时收发数据等方式确保数据传输的准确性。
5. **可扩展性**：Modbus允许多个（大约240个）设备连接在同一个网络上进行通信，所以可以同时连接多个Modbus协议的设备在同一条总线上进行通讯。为复杂的工业控制场景提供了良好的扩展性。

## **485总线主从模式**
![485](https://dgiot-1253666439.cos.ap-shanghai-fsi.myqcloud.com/dgiot_enterprise/zh/data_acquisition/modbus-rtu/introduce/485.png)

## **Modbus-rtu功能码**

| 功能码 |  功能  |      数据类型      |
|:---:|:----:|:--------------:|
| 01  |  读   |       位        |
| 02  |  读   |       位        |
| 03  |  读   | 整型、字符型、状态字、浮点型 |
| 04  |  读   |   整型、状态字、浮点型   |
| 05  |  写   |       位        |
| 06  |  写   | 整型、字符型、状态字、浮点型 |
| 08  | N/A  |   重复“回路反馈”信息   |
| 15  |  写   |       位        |
| 16  |  写   | 整型、字符型、状态字、浮点型 |
| 17  |  写   |      字符型       |


## **总结**

**Modbus作为一种广泛应用的工业通信协议，具有开放性、广泛支持、简单易用和可扩展性等特点。通过了解其协议版本、工作原理以及配置与使用方式，可以更好地将Modbus应用于工业控制系统中，实现设备之间的高效通信和数据传输。**
