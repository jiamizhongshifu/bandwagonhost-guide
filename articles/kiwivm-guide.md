---
layout: article
title: KiwiVM 控制面板使用教程：重启、控制台、备份与迁移
description: 搬瓦工 KiwiVM 控制面板入门，介绍重启、Interactive Console、系统重装、快照、备份、流量和机房迁移。
permalink: /articles/kiwivm-guide.html
---

KiwiVM 是搬瓦工自研的 VPS 控制面板。即使 SSH 已经连不上，只要账户和控制面板正常，仍可通过 KiwiVM 查看状态、启动实例或进入 Interactive Console 排障。

## 常用功能分别解决什么问题

| 功能 | 适用场景 | 主要风险 |
|---|---|---|
| Start / Stop / Restart | 系统关机、卡死或计划维护 | 强制停止可能造成未写入数据丢失 |
| Interactive Console | SSH、防火墙或网络配置异常 | 控制台不是替代日常 SSH 的工具 |
| OS Reload | 系统严重损坏，需要全新环境 | 会清除原系统数据 |
| Backups / Snapshots | 升级或重大修改前恢复 | 仍应保留站外备份 |
| Datacenter Migration | 更换可用机房、调整线路 | IP、DNS、白名单可能需要更新 |
| Traffic Usage | 查看月流量消耗 | 异常增长应先排查入侵或攻击 |

## SSH 断开时的最短排障路径

先确认 VPS 状态为 Running，再打开 Interactive Console，检查系统是否启动、SSH 服务是否监听，以及防火墙是否阻断端口。官方文档特别指出，迁移或 IP 变化后遗留的 iptables 规则可能让 VPS 完全无法连接。

只有在数据已经备份、系统确实无法修复时，才使用 OS Reload。不要把重装当成每次网络故障的第一步。

如果你还在选购，可[查看搬瓦工当前在售套餐](https://bandwagonhost.com/aff.php?aff=83193){: rel="nofollow sponsored" }。

> **联盟链接说明：** 上述入口含 `aff=83193`，作者可能获得佣金。功能与权益以你的 KiwiVM 页面为准。

相关：[SSH 连接失败排查](./ssh-troubleshooting.html) · [系统重装教程](./os-reinstall.html) · [机房迁移](./datacenter-migration.html)

最后核对：2026-07-13。依据：[官方知识库](https://bandwagonhost.com/knowledgebase.php)。

