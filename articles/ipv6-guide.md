---
layout: article
title: 搬瓦工支持 IPv6 吗？购买前检查方法
description: 搬瓦工 IPv6 支持情况、购买前如何核对产品页，以及系统内 IPv6 无法使用时的排查步骤。
permalink: /articles/ipv6-guide.html
---

搬瓦工是否支持 IPv6 要看具体产品。官网当前多个 KVM 和 CN2 GIA E-Commerce 产品写有 routed `/64` IPv6 subnet，但部分产品可能明确标注不支持 IPv6，因此不能把某个套餐的配置套用到全部产品。

## 购买前看哪里

在具体订单页寻找：

- `IPv6: routed /64 subnet`；
- 是否需要在 KiwiVM 中启用或分配；
- 初始机房与迁移后目标机房是否支持；
- 系统镜像是否已正确配置 IPv6 网络。

## 已购买但 IPv6 不通

先在 KiwiVM 核对分配信息，再检查系统接口、地址、默认路由和防火墙。迁移或重装后还要确认旧配置没有残留。用外部 IPv6 测试点验证双向连通性，而不是只看本机是否出现地址。

[查看当前支持相关配置的 CN2 GIA E-Commerce 20G 年付产品](https://bandwagonhost.com/aff.php?aff=83193&a=add&pid=87&billingcycle=annually){: rel="nofollow sponsored" }

> **联盟链接说明：** 产品深链含推广参数并预选年付周期，作者可能获得佣金；IPv6 配置以实时订单页为准。

相关：[套餐选择](./plan-selection.html) · [机房选择](./datacenter-selection.html)

最后核对：2026-07-13。依据：[官方购物车](https://bandwagonhost.com/cart.php)。

