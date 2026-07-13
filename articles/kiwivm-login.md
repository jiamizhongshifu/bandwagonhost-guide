---
layout: page
title: KiwiVM 怎么登录？三种密码不要混淆
description: 搬瓦工 Client Area、KiwiVM 控制面板与 Linux root 三种登录方式和密码区别。
permalink: /articles/kiwivm-login.html
---

搬瓦工新手最容易混淆三套凭据：Client Area、KiwiVM 和 Linux root。它们管理的层级不同，不能互相替代。

| 凭据 | 用来做什么 | 在哪里修改 |
|---|---|---|
| Client Area | 购买、账单、服务和工单 | Client Area 账户资料 |
| KiwiVM | 启停、控制台、重装、迁移等 | KiwiVM Password Modification |
| root / SSH | 登录 Linux 系统执行命令 | 系统内或 KiwiVM Root Password Reset |

## 最稳妥的登录路径

登录 Client Area，进入 Services → My Services，选择对应 VPS，再点击 KiwiVM Control Panel。官方文档说明，并非必须单独设置 KiwiVM 密码，始终可以从 Client Area 自动进入；单独密码适合需要直接登录控制面板的情况。

忘记 root 密码时，可在 KiwiVM 使用 Root Password Reset，但修改后应更新密码管理器。更推荐配置 SSH 公钥，并避免使用容易猜测的密码。

还没有服务时，可从[搬瓦工官方购买入口](https://bandwagonhost.com/aff.php?aff=83193){: rel="nofollow sponsored" }查看当前套餐。

> **联盟链接说明：** 购买入口含推广参数，作者可能获得佣金。

相关：[KiwiVM 使用教程](./kiwivm-guide.html) · [SSH 连不上排查](./ssh-troubleshooting.html)

最后核对：2026-07-13。依据：[官方新手指南](https://bandwagonhost.com/kb.php?action=displayarticle&id=30)。

