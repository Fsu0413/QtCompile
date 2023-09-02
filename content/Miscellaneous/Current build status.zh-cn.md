---
title: "当前构建状态"
draft: false
weight: 2
---

## QQtPatcher 支持状态

{{% notice style="warning" title="公告 QQtPatcher 结束生命周期" icon="fas fa-exclamation-triangle" %}}
QQtPatcher 将会于 Qt 5.12 停止构建的 {{% date 2023 9 11 %}}结束生命周期。   
在此之后，版本库会存档，问题将会关闭（原因为“不予处理”），不会再对其继续开发。  
QQtPatcher 相关内容将会转移到“遗留的长期支持版本系列”部分，包含此前在 QTCN 论坛上的更新历史也一并转移。
{{% /notice %}}

这是一个 QQtPatcher 支持和测试的版本的列表。  
其他版本可能工作，但是也可能静默得失败。

因为 Qt 4 的 `qmake -query` 不输出 makespec，一个有效的 qbp.json 在为 Qt 4 进行修补时是必要的。

根据 [New Features in Qt 5.14](https://wiki.qt.io/New_Features_in_Qt_5.14) 所宣布，Qt 5.14 是可重定位的，这样的话 Qt 5.14 及以后的版本不再需要 QQtPatcher。  
我在 Qt 5.14 的早期构建包中附带了 QQtPatcher（只是我忘了修改我的构建脚本里 QQtPatcher 相关的代码）。  
这个工具不会在 5.13 上彻底测试。  
我宣布 QQtPatcher 不会支持 Qt 5.14 以后的版本。

{{% QQtPatcherTable %}}

构建主机：

{{% QQtPatcherHosts %}}

## OpenSSL 状态

我的 Qt 构建在大部分平台上使用链接的 OpenSSL。  
下面是我构建 OpenSSL 的列表。

注：  
Windows 上的 OpenSSL 1.1.1 系列仅用于 Qt 5.12 系列。从 5.13 以后的 Qt 5 开始我们使用 SChannel。

OpenSSL 3 系列在 6.2.3 以及更新的 Qt 6 版本上使用。  
自从 Qt 6.2 将 tls 后端换成了插件，我们可以用多于一个的后端来构建。  
在 Windows 上我们使用 OpenSSL 和 SChannel，而在 macOS 上我们使用 OpenSSL 和 SecureTransport。

{{% OpenSSLSeries %}}

## MariaDB 状态

从 {{% date 2023 2 8 %}}开始，Qt 5.15 及以上的桌面版构建中附带 MariaDB connector/C 的动态库。
这个动态库用来构建 MySQL 数据库插件。  
不使用 MySQL 提供的库的原因有以下几个。

1. MariaDB 是真正的“原来的” MySQL
1. 使用新版 MySQL（8.0 及以后的版本）需要下载并构建整个 MySQL 数据库。而 MySQL 数据库太大，构建较费事。
1. MySQL 出自 Oracle。而 Oracle 有打击开源社区的历史。

在 Qt 5.15 版本上，我们使用 MariaDB connector/C 3.1 系列的版本。  
在 Qt 6.2 以及更高的版本上，我们使用 MariaDB connector/C 3.3 系列的版本。

{{% mariaDBSeries %}}

## Qt 构建表

**注：因为 Qt 移除了对 32 位 Windows 的支持，我们也不会为 32 位 Windows 提供 Qt 6 的构建。**
**如果需要非 LTS 版本的静态构建，请直接联系我寻求商业定制。**

{{% QtTable %}}
