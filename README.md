# 简介

本项目是适用于 [**Clash.Meta 内核**](https://github.com/MetaCubeX/Clash.Meta) 的去广告规则集 （RULE-SET）。

## 说明

本项目规则集（RULE-SET）的数据主要来源于项目 [@ACL4SSR/ACL4SSR](https://github.com/ACL4SSR/ACL4SSR/tree/master)，适用于 [**Clash.Meta 内核**](https://github.com/MetaCubeX/Clash.Meta)。

### Clash.Meta 各版本下载地址

- Clash.Meta **命令行**版 （适用于 Windows、macOS、Linux、OpenWRT 等多种平台）： [mihomo](https://github.com/MetaCubeX/mihomo/releases)
- Clash.Meta **图形用户界面**版：
  - [ClashX.Meta](https://github.com/MetaCubeX/ClashX.Meta/releases)（适用于 macOS）
  - [clash-verge-rev](https://github.com/clash-verge-rev/clash-verge-rev/releases)（适用于 Windows、macOS、Linux）
  - [ClashMetaForAndroid](https://github.com/MetaCubeX/ClashMetaForAndroid/releases)（适用于 Android）

## 规则文件地址及使用方式

### 在线地址（URL）

- **AD**：
  - [https://raw.githubusercontent.com/earoftoast/clash-rules/main/AD.yaml](https://raw.githubusercontent.com/earoftoast/clash-rules/main/AD.yaml)

- **EasyList**：
  - [https://raw.githubusercontent.com/earoftoast/clash-rules/main/EasyList.yaml](https://raw.githubusercontent.com/earoftoast/clash-rules/main/EasyList.yaml)

- **EasyListChina**：
  - [https://raw.githubusercontent.com/earoftoast/clash-rules/main/EasyListChina.yaml](https://raw.githubusercontent.com/earoftoast/clash-rules/main/EasyListChina.yaml)

- **EasyPrivacy**：
  - [https://raw.githubusercontent.com/earoftoast/clash-rules/main/EasyPrivacy.yaml](https://raw.githubusercontent.com/earoftoast/clash-rules/main/EasyPrivacy.yaml)

- **ProgramAD**：
  - [https://raw.githubusercontent.com/earoftoast/clash-rules/main/ProgramAD.yaml](https://raw.githubusercontent.com/earoftoast/clash-rules/main/ProgramAD.yaml)

### 使用方式

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

  EasyPrivacy:
    type: http
    behavior: domain
    url: "https://raw.githubusercontent.com/earoftoast/clash-rules/main/EasyPrivacy.yaml"
    path: ./rules/EasyPrivacy.yaml
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
  - RULE-SET,EasyPrivacy,REJECT
  - RULE-SET,IP,REJECT
  - RULE-SET,ProgramAD,REJECT
```

## 致谢

- [@Loyalsoldier/clash-rules](https://github.com/Loyalsoldier/clash-rules)
- [@ACL4SSR/ACL4SSR](https://github.com/ACL4SSR/ACL4SSR/tree/master)
