# 简介

本项目生成适用于 [**Clash Premium 内核**](https://github.com/Dreamacro/clash/releases/tag/premium)的规则集（RULE-SET），同时适用于所有使用 Clash Premium 内核的 Clash 图形用户界面（GUI）客户端。

## 说明

本项目规则集（RULE-SET）的数据主要来源于项目 [@ACL4SSR/ACL4SSR](https://github.com/ACL4SSR/ACL4SSR/tree/master)。

本项目的规则集（RULE-SET）只适用于 Clash **Premium** 版本。Clash Premium 相对于普通版，增加了 **TUN 增强模式**，能接管设备所有 TCP 和 UDP 流量，类似 [Surge for Mac](https://nssurge.com) 的增强模式。更多高级特性请看[官方文档](https://github.com/Dreamacro/clash/wiki/Clash-Premium-Features)。

### Clash Premium 各版本下载地址

- Clash Premium **命令行**版（适用于 Windows、macOS、Linux、OpenWRT 等多种平台）：[https://github.com/Dreamacro/clash/releases/tag/premium](https://github.com/Dreamacro/clash/releases/tag/premium)
- Clash Premium **图形用户界面**版：
  - [ClashX Pro](https://install.appcenter.ms/users/clashx/apps/clashx-pro/distribution_groups/public)（适用于 macOS）
  - [Clash for Windows](https://github.com/Fndroid/clash_for_windows_pkg/releases)（适用于 Windows、macOS、Linux）
  - [Clash for Android](https://github.com/Kr328/ClashForAndroid/releases)（适用于 Android）

## 规则文件地址及使用方式

### 在线地址（URL）

- **AD列表**：
  - [https://raw.githubusercontent.com/earoftoast/clash-rules/main/AD.yaml](https://raw.githubusercontent.com/earoftoast/clash-rules/main/AD.yaml)

- **EasyList列表**：
  - [https://raw.githubusercontent.com/earoftoast/clash-rules/main/EasyList.yaml](https://raw.githubusercontent.com/earoftoast/clash-rules/main/EasyList.yaml)

- **EasyListChina列表**：
  - [https://raw.githubusercontent.com/earoftoast/clash-rules/main/EasyListChina.yaml](https://raw.githubusercontent.com/earoftoast/clash-rules/main/EasyListChina.yaml)

- **IP列表**：
  - [https://raw.githubusercontent.com/earoftoast/clash-rules/main/IP.yaml](https://raw.githubusercontent.com/earoftoast/clash-rules/main/IP.yaml)

- **ProgramAD列表**：
  - [https://raw.githubusercontent.com/earoftoast/clash-rules/main/ProgramAD.yaml](https://raw.githubusercontent.com/earoftoast/clash-rules/main/ProgramAD.yaml)

### 使用方式

关于 Clash Premium 使用方式，请查看[官方文档](https://github.com/Dreamacro/clash/wiki/Clash-Premium-Features) 或 [Lancellc's GitBook](https://lancellc.gitbook.io/clash/)。

要想使用本项目的规则集，只需要在 Clash 配置文件中添加如下 `rule-providers` 和 `rules`。

#### Rule Providers 配置方式

```yaml
rule-providers:
  AD:
    type: http
    behavior: domain
    url: "https://raw.githubusercontent.com/earoftoast/clash-rules/main/AD.yaml"
    path: ./rules/AD.yaml
    interval: 86400
    
  EasyList:
    type: http
    behavior: domain
    url: "https://raw.githubusercontent.com/earoftoast/clash-rules/main/EasyList.yaml"
    path: ./rules/EasyList.yaml
    interval: 86400
    
  EasyListChina:
    type: http
    behavior: domain
    url: "https://raw.githubusercontent.com/earoftoast/clash-rules/main/EasyListChina.yaml"
    path: ./rules/EasyListChina.yaml
    interval: 86400

  IP:
    type: http
    behavior: ipcidr
    url: "https://raw.githubusercontent.com/earoftoast/clash-rules/main/IP.yaml"
    path: ./rules/IP.yaml
    interval: 86400

  ProgramAD:
    type: http
    behavior: domain
    url: "https://raw.githubusercontent.com/earoftoast/clash-rules/main/ProgramAD.yaml"
    path: ./rules/ProgramAD.yaml
    interval: 86400
```

#### Rules 配置方式

```yaml
rules:
  - RULE-SET,AD,REJECT
  - RULE-SET,EasyList,REJECT
  - RULE-SET,EasyListChina,REJECT
  - RULE-SET,IP,REJECT
  - RULE-SET,ProgramAD,REJECT
```

## 致谢

- [@Loyalsoldier/clash-rules](https://github.com/Loyalsoldier/clash-rules)
- [@ACL4SSR/ACL4SSR](https://github.com/ACL4SSR/ACL4SSR/tree/master)
