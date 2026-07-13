---
layout: article
title: 搬瓦工怎么重装系统？KiwiVM 重装前后检查清单
description: 搬瓦工 KiwiVM 重装 Linux 系统前如何备份，重装后如何恢复 SSH、防火墙、网站和监控。
permalink: /articles/os-reinstall.html
---

搬瓦工产品页提供 Instant OS Reload，但重装会替换现有系统环境。真正重要的不是点哪个按钮，而是确认数据能恢复。

## 重装前

1. 下载数据库、网站文件、配置、密钥和证书到站外；
2. 验证备份能打开，而不是只确认“备份任务成功”；
3. 记录域名、端口、防火墙、软件版本、定时任务和白名单；
4. 确认当前 IP 是否会保持以及哪些业务依赖它；
5. 预留维护窗口。

## KiwiVM 中的操作

登录 KiwiVM，选择 OS Reload / Install new OS，阅读数据清除提示，选择官方当前提供的系统镜像并确认。不要在仍需抢救数据时执行。

官网当前产品页常见系统包括 Debian、Ubuntu、Rocky Linux 和 AlmaLinux，具体列表取决于套餐与当时界面。优先选择仍在安全支持期内、团队熟悉的版本。

## 重装后

- 第一时间更新系统补丁；
- 建立普通管理用户与 SSH 密钥；
- 配置防火墙后再开放业务端口；
- 恢复应用和数据并验证权限；
- 检查 DNS、rDNS、监控与自动备份；
- 从外部网络做完整访问测试。

如果只是 SSH 连不上，应先看[SSH 排障流程](./ssh-troubleshooting.html)，不要直接重装。

[查看搬瓦工实时产品与系统说明](https://bandwagonhost.com/aff.php?aff=83193){: rel="nofollow sponsored" }

> **联盟链接说明：** 产品链接含 `aff=83193`，作者可能获得佣金。

最后核对：2026-07-13。依据：[官方产品页](https://bandwagonhost.com/cart.php)、[网络排障文档](https://bandwagonhost.com/kb.php?action=displayarticle&id=26)。

