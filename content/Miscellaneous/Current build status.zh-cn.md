---
title: "当前构建状态"
draft: false
weight: 2
---

## QQtPatcher 支持状态

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
这是一个我构建 OpenSSL 的列表。

注：  
Windows 上的 OpenSSL 1.1.1 系列仅用于 Qt 5.12 系列。从 5.13 以后的 Qt 5 开始我们使用 SChannel。  
MinGW 的构建是 `-shared-and-static` 的，所以不用单独构建静态版本。

OpenSSL 3 系列在 6.2.3 以及更新的 Qt 6 版本上使用。  
自从 Qt 6.2 将 tls 后端换成了插件，我们可以用多于一个的后端来构建。  
在 Windows 上我们使用 OpenSSL 和 SChannel，而在 macOS 上我们使用 OpenSSL 和 SecureTransport。

{{% OpenSSLSeries %}}

## Qt 5.12 系列（以前的 LTS 发布版本，Qt 已经结束支持）

{{% QtTable "5.12.12" %}}

## Qt 5.15 系列（以前的 LTS 发布版本）

{{% QtTable "5.15.7" %}}

## Qt 6.2 系列（当前的商业专属的 LTS 发布版本）

**注：因为 Qt 移除了对 32 位 Windows 的支持，我们的 Qt 6 构建也移除了 32 位 Windows 的支持。**

{{% QtTable "6.2.4" %}}

## Qt 6.4 系列（当前的主线发布版本）

**注：因为 Qt 移除了对 32 位 Windows 的支持，我们的 Qt 6 构建也移除了 32 位 Windows 的支持。**  
**如果需要非 LTS 版本的静态构建，请直接联系我寻求商业定制。**

{{% QtTable "6.4.0" %}}