---
title: HTTP
sidebar_position: 1
---

### Swagger地址：
https://prod.dgiotcloud.cn/dgiot_swagger/



# DGIOT开源物联网平台接口手册 2.0.0
DGIOT开源物联网平台接口手册, 高并发全连接物联网平台, 支持私有云部署的全开放的IoT产品全生命周期管理平台

在DGIoT平台的HTTP对接时，我们通常会关注于如何通过HTTP请求与DGIoT平台进行数据交互，包括发送数据到平台、从平台获取数据或执行某些操作。

### DGIoT HTTP对接概述

DGIoT平台支持通过HTTP协议进行数据的上传与下载，为开发者提供了灵活的数据交互方式。通过HTTP API，用户可以轻松实现设备数据的上报、远程控制指令的下发、数据查询等功能。

### 基本请求流程

1. **注册与认证**：
    - 在进行任何数据交互前，通常需要完成设备的注册，并获取认证所需的凭证（如Token）。

2. **构建HTTP请求**：
    - 根据API文档，构建包含必要参数（如设备ID、数据内容等）的HTTP请求。
    - 设置请求头，包括认证信息（如`Authorization: Bearer <token>`）。

3. **发送请求**：
    - 将HTTP请求发送到DGIoT平台指定的URL。

4. **处理响应**：
    - 解析服务器返回的响应数据，根据HTTP状态码和响应体内容判断请求是否成功。

### 请求示例

#### 上报设备数据（POST请求）

```
http
POST /api/devices/{deviceId}/data
Content-Type: application/json
Authorization: Bearer <token>

{
  "timestamp": "2024-09-03T12:00:00Z",
  "data": {
    "temperature": 25.5,
    "humidity": 60
  }
}
```

#### 查询设备数据（GET请求）

```http
GET /api/devices/{deviceId}/data?startTime=2023-04-01T00:00:00Z&endTime=2023-04-02T00:00:00Z
Authorization: Bearer <token>
```

### 注意事项

- **安全性**：确保在传输敏感信息时使用HTTPS协议。
- **错误处理**：合理处理HTTP请求中的错误状态码，并给出相应的用户反馈。
- **API限流**：了解并遵守DGIoT平台的API调用频率限制，防止因超出限制而导致服务被暂时禁用。
- **API版本**：关注API的版本更新，及时适配新版本的API以避免兼容性问题。

通过上述描述，您可以对DGIoT平台的HTTP对接有一个基本的了解。具体实现时，请参考DGIoT平台提供的官方API——Swagger文档并进行在线测试，以获取最准确、最详细的信息。

DGIOT物联网平台已充分考虑与第三方系统的对接，快速支持应用开发，预留相关接口并支持统一API，以便后续集成开发。相关接口包含但不限于以下六类接口。
## 设备API接口
提供API供应用进行设备管理，包含产品（设备）新增、编辑、删除设备和设备组以及读取单个或多个设备信息等操作的API服务。
## 数据API接口
提供API供应用进行设备数据查询，订阅（实时推送），删除等操作的API服务。
## 命令执行API接口
提供控制或下发命令给设备侧，包含命令发送，响应获取以及命令撤销等操作的API服务。
## 规则API接口
提供应用使用平台规则引擎的能力，包含新增、编辑、删除及查找规则等操作的API服务。
## 安全接入API接口
用于对第三方应用进行鉴权认证等操作的API服务。
## 平台扩展应用API接口
基于DGIOT物联网平台的水泵远程检测取证应用的部分API。