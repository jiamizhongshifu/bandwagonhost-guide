---
layout: article
title: 搬瓦工迁移机房失败怎么办？黑名单与防火墙排查
description: KiwiVM Datacenter Migration 无法使用时，检查 IP 黑名单、套餐权限、迁移状态与旧 iptables 规则。
permalink: /articles/migration-failed.html
---

KiwiVM 迁移失败不一定是系统故障。先判断是按钮不可用、目标机房不可选、任务失败，还是迁移完成后新 IP 无法访问。

## 常见原因

- 当前套餐不支持目标机房；
- 目标机房暂时不可用或没有容量；
- 上一次迁移仍在处理或存在冷却限制；
- 当前 IP 位于黑名单；
- 迁移成功，但系统防火墙仍绑定旧 IP。

官方服务条款明确说明：IP 被列入黑名单后，Datacenter Migration 将不可用，直到该 IP **连续至少 7 天**不在任何黑名单上。

若迁移完成后完全无法连接，使用 KiwiVM Interactive Console 检查 iptables/nftables。官方排障文档指出，NAT 表中残留旧 VPS IP 是常见原因之一。

如果你需要更灵活的多机房方案，可查看[CN2 GIA E-Commerce 20G 年付产品](https://bandwagonhost.com/aff.php?aff=83193&a=add&pid=87&billingcycle=annually){: rel="nofollow sponsored" }。

> **联盟链接说明：** 产品深链保留 `aff=83193` 并预选当前产品及年付周期，作者可能获得佣金。

相关：[迁移前注意事项](./datacenter-migration.html) · [IP 黑名单处理](./ip-blacklist.html)

最后核对：2026-07-13。依据：[官方服务条款](https://bandwagonhost.com/knowledgebase/6/tos---terms-of-service.html)、[iptables 排障](https://bandwagonhost.com/knowledgebase.php?action=displayarticle&id=24)。

