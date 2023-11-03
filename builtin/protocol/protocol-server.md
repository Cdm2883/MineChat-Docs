---
description: [内置]
---

# 协议提供服务器
通过`协议提供服务器`间接对`游戏服务器`进行连接, 所有与`游戏服务器`的交互发生在`协议提供服务器`.  
这意味着在MineChat客户端上只与`协议提供服务器`建立了连接, 你的所有的尝试与`游戏服务器`的交互都会交给`协议提供服务器`处理后转发给`游戏服务器`. `游戏服务器`的消息会由`协议提供服务器`处理再由`协议提供服务器`回传给MineChat客户端.
```mermaid
sequenceDiagram
    participant plugin as 协议提供服务器插件
    participant protocol_server as 协议提供服务器
    participant server as 游戏服务器
    loop over and over again
        plugin ->> protocol_server: packet
        protocol_server ->> server: packet
        server ->> protocol_server: packet
        protocol_server ->> plugin: packet
    end
```

## 📝 添加&修改服务器

## 🔧 插件配置页

## 🌍 开发`协议提供服务器`
