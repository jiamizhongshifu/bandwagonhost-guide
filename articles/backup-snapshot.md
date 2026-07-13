---
layout: page
title: 搬瓦工备份与快照怎么用？别把平台备份当唯一副本
description: 搬瓦工 KiwiVM 自动备份、快照与站外备份的区别，以及重装、迁移和退款前的恢复检查。
permalink: /articles/backup-snapshot.html
---

搬瓦工当前多个产品页列出自动备份和快照功能，但官方服务条款仍明确建议用户实施自己的备份方案并定期验证恢复能力。平台备份不是数据安全的唯一副本。

## 三层备份更可靠

1. **应用备份**：数据库导出、配置、上传文件和密钥；
2. **整机快照/平台备份**：用于升级失败或系统损坏时快速恢复；
3. **站外副本**：保存到另一供应商、本地设备或对象存储。

## 什么时候必须备份

- OS Reload 或手动安装系统前；
- Datacenter Migration 前；
- 防火墙、内核、数据库重大升级前；
- 提交退款或取消服务前；
- 发现磁盘、文件系统或安全异常时。

退款获批后，相关服务、数据、快照和备份可能被立即且不可逆地删除。因此“后台里还有快照”不等于退款后仍可找回。

[查看包含当前备份与快照说明的 E-Commerce 20G 年付产品](https://bandwagonhost.com/aff.php?aff=83193&a=add&pid=87&billingcycle=annually){: rel="nofollow sponsored" }

> **联盟链接说明：** 产品深链含 `aff=83193`，作者可能获得佣金。具体保留周期以 KiwiVM 为准。

相关：[系统重装](./os-reinstall.html) · [退款条件](./refund-policy.html)

最后核对：2026-07-13。依据：[官方产品页](https://bandwagonhost.com/cart.php)、[服务条款](https://bandwagonhost.com/knowledgebase/6/tos---terms-of-service.html)。

