# 简介

本项目**仅生成**适用于 [**Surge**](https://nssurge.com) 的**中国大陆 IP 地址列表（RULE-SET）**，即 `cncidr.txt`。使用 GitHub Actions 北京时间每天早上 6:30 自动构建，保证规则最新。

## 说明

本项目的中国大陆 IPv4 / IPv6 地址数据使用 [@Loyalsoldier/geoip](https://github.com/Loyalsoldier/geoip) 的 `text/cn.txt`（其上游为 [@17mon/china_ip_list](https://github.com/17mon/china_ip_list)）。

## 规则文件地址及使用方式

### 在线地址（URL）

> 如果无法访问域名 `raw.githubusercontent.com`，可以使用第二个地址（`cdn.jsdelivr.net`），但是内容更新会有 12 小时的延迟。

#### RULE-SET:

- **中国大陆 IP 地址列表 cncidr.txt**：
  - [https://raw.githubusercontent.com/xxhhlk/surge-rules/release/ruleset/cncidr.txt](https://raw.githubusercontent.com/xxhhlk/surge-rules/release/ruleset/cncidr.txt)
  - [https://cdn.jsdelivr.net/gh/xxhhlk/surge-rules@release/ruleset/cncidr.txt](https://cdn.jsdelivr.net/gh/xxhhlk/surge-rules@release/ruleset/cncidr.txt)

### 使用方式

关于 Surge 的详细使用方法，见[官方手册](https://manual.nssurge.com)。在 Surge 配置文件的 `[Rule]` 段加入如下规则，即可将命中中国大陆 IP 的流量直连：

```
[Rule]
RULE-SET,https://cdn.jsdelivr.net/gh/xxhhlk/surge-rules@release/ruleset/cncidr.txt,DIRECT
RULE-SET,LAN,DIRECT
FINAL,PROXY
```

> 说明：`RULE-SET,LAN,DIRECT` 与 `FINAL,PROXY` 为 Surge 内置规则/兜底策略示例，请按你的实际代理配置调整 `PROXY` 名称。

## 致谢

- [@Loyalsoldier/geoip](https://github.com/Loyalsoldier/geoip)
- [@17mon/china_ip_list](https://github.com/17mon/china_ip_list)
