---
layout: page
title: 搬瓦工 SSH 连不上怎么办？超时与拒绝连接排查
description: 搬瓦工 SSH timeout、connection refused、主机密钥变化等问题的逐步排查方法。
permalink: /articles/ssh-troubleshooting.html
---

SSH 连不上时，错误信息比“能不能 ping 通”更有价值。先区分超时、拒绝连接和主机密钥警告，再决定修复方向。

## 三类常见错误

### Connection timed out

数据包没有完成连接。可能是本地网络、路由、IP 连通性、防火墙或错误端口。用手机热点和异地节点交叉测试，并在 KiwiVM 确认 VPS 正在运行。

### Connection refused

目标主机可达，但对应端口没有服务监听，或系统明确拒绝。通过 KiwiVM Interactive Console 检查 SSH 服务状态、监听端口和防火墙。

### REMOTE HOST IDENTIFICATION HAS CHANGED

常见于重装系统、迁移或更换 IP 后主机指纹变化。先在 KiwiVM 或可信渠道核对新指纹，确认不是中间人攻击，再删除本机旧的 `known_hosts` 记录。

## 官方推荐的进一步检查

搬瓦工官方网络排障文档建议：完全无法连接时，先检查实例状态和防火墙；迁移后若 iptables 仍引用旧 IP，可能导致锁死。可以通过 Interactive Console 临时停止防火墙进行对照，但确认根因后应重新启用并修正规则，不能长期裸奔。

如果境外正常、特定地区持续不通，再参考[IP 被封判断清单](./ip-blocked-check.html)；确认需要换地址时再看[更换 IP 流程](./ip-change.html)。

[查看搬瓦工当前套餐](https://bandwagonhost.com/aff.php?aff=83193){: rel="nofollow sponsored" }

> **联盟链接说明：** 套餐入口含推广参数，作者可能获得佣金。排障不要求购买新套餐。

最后核对：2026-07-13。依据：[网络连通性排障](https://bandwagonhost.com/kb.php?action=displayarticle&id=26)、[iptables 排障](https://bandwagonhost.com/knowledgebase.php?action=displayarticle&id=24)。

