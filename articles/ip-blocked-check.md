---
layout: article
title: 搬瓦工 IP 被封了吗？先排除宕机、防火墙和 SSH 问题
description: 搬瓦工 ping 不通、SSH 超时时的逐步判断方法，避免误付费更换 IP。
permalink: /articles/ip-blocked-check.html
---

“SSH 超时”只能证明连接失败，不能单独证明 IP 被封。按下面顺序排查，能把问题缩小到本地网络、路由、端口、系统或 IP 层。

## 1. 先看控制面

登录 Client Area 和 KiwiVM，确认实例运行、资源没有耗尽，并尝试 Serial Console。若控制台也无法正常启动系统，应先处理 VPS 本身，而不是换 IP。

## 2. 做多网络对照

用宽带、手机热点和可信的异地探测点分别测试。结果可这样理解：

| 现象 | 更可能的方向 |
|---|---|
| 只有当前宽带不通 | 本地网络、DNS 或运营商路由 |
| Ping 不通但 SSH/网站正常 | 服务器禁用了 ICMP，不代表 IP 异常 |
| 境外可访问、特定地区持续不可访问 | 区域路由或访问限制，继续交叉验证 |
| 所有网络、所有端口都不通 | VPS 宕机、防火墙、上游或 IP 问题 |

## 3. 检查服务与防火墙

通过控制台确认 SSH 服务正在运行、端口确实监听，并检查 `iptables`/`nftables`/`ufw`。搬瓦工官方知识库也提示，迁移或 IP 变化后，错误的防火墙配置可能造成网络连接问题。

## 4. 决定是否换 IP

只有在 VPS 正常、服务正常、多个网络的对照结果又持续指向 IP/区域连通性时，才进入换 IP决策。完整步骤见[搬瓦工更换 IP 全流程](./ip-change.html)。

如果当前套餐包含免费换 IP，按产品页权益操作；否则登录[官方 IP Change 页面](https://bandwagonhost.com/ipchange.php)查看实时费用。需要新购套餐时可[查看官网实时库存](https://bandwagonhost.com/aff.php?aff=83193){: rel="nofollow sponsored" }。

> **联盟链接说明：** 上述套餐链接含推广参数，作者可能获得佣金；这不替代官方技术支持。

最后核对：2026-07-13。

