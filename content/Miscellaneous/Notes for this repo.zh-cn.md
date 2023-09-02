---
title: "本仓库的一些备注"
draft: false
weight: 1
---

## 中文 / 多语言支持

虽然这个网站的维护者（Fsu0413，也就是我）是中国人，是中文母语使用者，不过此网站最初做成的时候是只有嘤文版的。  
目前我正在逐步在此网站上添加简体中文支持。

得益于 [Hugo](https://gohugo.io/) 自带的多语言支持和 ~~近期新换的~~ [Relearn](https://mcshelby.github.io/hugo-theme-relearn/) 主题，本网站 ~~近期刚刚~~ 支持多语言。  
~~目前的中文也仅仅处于刚刚开始组织语言的阶段。有一些内容还没有写完。~~  
~~不过主要内容均使用中文重新写了一遍，应该不会影响大家下载二进制文件了。~~

对网站建设有建议和意见的可以[去 GitHub 上提出 issue](https://github.com/Fsu0413/QtCompile/issues/new)。

## 网站镜像

~~最近~~ 我在中国大陆使用 Gitee Pages 服务构建了一个此网站的镜像。  
这个镜像配置的默认语言改为简体中文。

由于 Gitee 的自定义域名服务只提供给付费用户，目前中文站是在 Gitee 的域名下的。  
如果之后我对此服务感觉不错的话，我可能会付费使用这个服务。

[Gitee Pages （中国大陆，使用简体中文作为默认语言）](https://fsu0413.gitee.io/qtcompile/)  
[Github Pages （美国，使用英语作为默认语言）](https://build-qt.fsu0413.me/)

## 可复现的构建

为了实现对 Qt 的[可复现的构建](https://reproducible-builds.org/)，我使用一系列脚本进行构建和打包。  
如果您对构建方法感兴趣的话，可以参考下面的 GitHub 仓库。

[GitHub](https://github.com/Fsu0413/Fs-scripts)

但是不太好的一点是这个网站是手工编辑的。  
这个网站的源码如下：

[GitHub](https://github.com/Fsu0413/QtCompile)

## 对静态构建的备注

我不在大型项目中使用静态构建。我并不认为使用静态构建是很明智的选择。

我可以理解使用静态构建的目的是为了仅发布单一可执行程序，但是事实上有如下限制：

* 在程序不以 (L)GPLv3 许可协议发布的情况下，使用静态构建并不免费。
* 部分模块无法构建。（比如 WebEngine 之类的）
* 不能使用动态链接的插件。
* 在构建期不执行链接操作，会在后续过程中导致可能的链接问题

这边还是建议在大型项目中停止使用静态构建。相信我，这么做更加自由。

## 静态 `Lite` 构建和静态 `Full` 构建 （{{% date 2022 3 8 %}}更新）

静态 `Lite` 构建跳过了大多数 Qt 模块。只对 QtCore、QtDeclarative（QtQml 2），QtXmlPatterns 和 QtXXXExtras 进行了构建。  
对于在不静态构建整个 Qt 的情况下构建 QtIFW 来说是很有用的。

（{{% date 2022 3 8 %}}更新）Qt 5 静态 `Lite` 构建也用于我的 QQtPatcher。  
（{{% date 2021 12 4 %}}更新）因为 Qt 6 的交叉构建需要一套相同版本的 Qt 6 的主机工具，我们通过这一套静态 `Lite` 的版本的 Qt 来构建主机工具。

静态 `Full` 构建不跳过多数 Qt 模块，仅跳过无法构建通过的模块。

## 对使用旧版本 Qt 的备注

我这里只提供最新的大版本 / LTS 版本的预编译库，以前的非 LTS 的版本会在我构建并上传新版本的包之后删除。

我不明白为什么会有人不更新 Qt 到当前分支的最新版本（比如在我写这个备注的时候，5.6.1-1 已经发布了大半个月了，但是还是有相当一部分人还在用 5.6.0）。

为了稳定性？兼容性？懒得更新？还是其他原因？

* 稳定性  
我认为更新到当前分支的最新版本增加稳定性。Qt 在小版本更新时仅修复 bug。这并不是问题。
* 兼容性  
相同的大版本都是二进制兼容的。这不是需要考虑的点。
* 懒  
不要跟我比懒，我懒得跟你比。
* 其他原因  
我不知道还会有什么其他原因。

## 对于发布的压缩文件的备注

在 Windows 上，打包文件使用 `7z` 程序，使用 LZMA2 算法压缩成 `7z` 格式。  
生成压缩文件的命令行类似这样：
```
7z a -t7z -m0=LZMA2:d256m:fb273 -mmt=3 -myx -mqs -ms=on -- xxx.7z xxx
```

在 Linux 上，打包文件使用 GNU `tar` 创建，而在 macOS 上，则是使用 `bsdtar`。  
此外同时使用 `7z` 来进行 `xz` 格式的压缩。  
生成压缩文件的命令行类似这样：
```
tar -cf - xxx | 7zr a -txz -m0=LZMA2:d256m:fb273 -mmt=3 -myx -si -- xxx.tar.xz
```

要确保您使用的解压缩软件支持 LZMA2 算法。例如：  
`7z` 用户需要更新到 9.20 或者更新。  
`WinRAR` 用户需要更新到 4.00 或者更新。  
如果是其他解压缩软件，可以检查一下他们的最新版本，有可能最新版本就支持 LZMA2 算法了。

近期 Arch Linux 和 MSYS2 在将他们的包管理工具的压缩算法改为了 zstd。  
只有较新的 GNU `tar`（1.31 以及更新）和较新的 `bsdtar`（3.3.3 以及更新）直接支持 `.tar.zst` 压缩方法。  
我不会在此仓库使用 zstd，因为压缩比不如 LZMA2。

## 这份 Qt 和官方发布的 Qt 的区别（{{% date 2023 1 8 %}}更新）

我只提供供各个系统使用的 Qt 的二进制压缩文件。  
这份二进制文件应该开箱可用（Qt 5.14 及更新） / 在对 Qt 打补丁后可用（Qt 5.13 及以前）。  
（{{% date 2022 4 14 %}}更新）因为安装包经常会被怀疑捆绑不需要的软件（我不会干这种事），我永远不会使用安装包。

（{{% date 2020 6 7 %}}更新） **不需要登录 Qt 账户** ！！！这样就摆脱了他们胡说的“这可以协助优化 Qt”。

这里所有的 Qt 构建均使用 `-no-icu` 来配置。因为我觉得 ICU 在通常情况下没用，而且这东西还挺大。

在 Qt 不支持使用平台原生的借口创建 SSL 套接字的平台使用链接的 OpenSSL。  
Qt 5.12 及以前的版本的 Windows 构建使用动态（共享）链接的 OpenSSL 库。安卓构建使用静态链接的 OpenSSL 库。  
macOS 构建使用 SecureTransport 代替 OpenSSL 库。  
Qt 5.13 及以后的版本的 Windows 构建使用 SChannel 代替 OpenSSL 库。

（{{% date 2022 4 14 %}}更新）**没有调试库，这大约节省了整个 Qt 包的大半部分空间。**  
（不要在没有商业定制化的情况下请求添加这个东西，主要是我不用。注：商业定制化还没有开始运营）

没有示例程序，这大约节省了整个 Qt 包的大半部分空间。

没有文档（而且在 Qt 5.12 之后由于 `QDoc` 依赖 `clang` 导致 `QDoc` 也没有了）。因为 Qt 文档可以在 [http://doc.qt.io](http://doc.qt.io) 随时查阅，没有必要在包里面再放一份文档。

（{{% date 2023 1 8 %}}更新） **没有证书** 。这对某些非开发人员来说可能是灾难性的。  
由于二进制程序证书需要非常昂贵的价格购买，而我作为个人开发者不可能购买如此昂贵的应用程序证书来进行可信度校验。  
所以在运行我构建的 Qt 的时候，会提示程序不被信任的问题。  
此问题在我这里暂时无法解决，除非以后开始进行商务化定制，拿到收入后，再去购买证书进行校验。  
在此之前，可能会实现基于 GPG 的校验。（虽然咕咕咕了）  
（由于 Qt 5.14 以前的版本需要在安装后对 Qt 打补丁，所以无法校验。Qt 5.14 以及以后的版本可以重定位，解决了这个问题）

## 对于 Qt 5.14 以前的备注

Qt 5.14 以前的版本拒绝使用刚刚从包中解压出来的二进制文件。  
它会在 Qt Creator 里报告类似“Qt 未正确安装，请运行 ```make install``` ”这样的内容。

我在压缩包里附带了一个 QQtPatcher。解压后需要运行 QQtPatcher 一次来让 Qt 工作。

这个 QQtPatcher 的源码在 [GitHub](https://github.com/Fsu0413/QQtPatcher) 上。这是一个在共有领域发布的自由软件。

不要把这个库放在有空格或者非 ASCII 字符的路径下。  
由于 Bug 导致 qmake 的路径不能被 Qt Creator 成功解析。

## Qt offering changes 2020 （{{% date 2022 4 14 %}}更新）

Qt 宣布了 [Qt offering changes 2020](https://www.qt.io/blog/qt-offering-changes-2020)。  
下面是我对这个博客的一些想法。

首先我是有 Qt 账户的，不过安装 Qt 开发包为啥需要 Qt 账户我一直不明白。  
都是一套源码编译出来的东西，登录个 Qt 账户也不会不一样，又不会给 Qt 增加任何功能，他们说的什么“这可以协助优化 Qt”根本就是在扯淡。

LTS 只给商业许可，那么 LTS 的源码包是什么许可？  
（{{% date 2022 3 8 %}}删除） ~~如果也是商业许可的话，Qt 基本就和稳定开源软件说拜拜了。~~  
（{{% date 2022 3 8 %}}更新）按照现有的所有版本延迟一年发布的计划，举个例子一个安全补丁会延迟非常晚才被修复，尤其 Qt 公司构建的原版 Qt 更是这样。  
再说了他们的 LTS 支持时间也不算长，Windows 支持 10 年，（{{% date 2022 4 14 %}}更新） ~~CentOS~~ RockyLinux 支持 10 年，他支持 3 年。。。。

离线安装包只给商业许可，等于国内只能找网络通畅的时间（一般是早晨 8 点前）来用在线安装包安装 Qt 开源版了。

什么样的企业算小企业？  
一个人开一家空壳公司，这种企业算非常小非常小的企业吧？用这种企业来买 Qt 发布软件，共事的其他员工在私底下用开源版，每年只用 499 美元？  
这样做肯定会赔钱的。

还有，我会继续我编译 Qt 的业余工作，希望 Qt for MCUs 早日开源。

（{{% date 2023 9 2 %}}追加）前段时间有幸在公司中一个小型 MCU 项目中看到了 Qt for MCUs，是以二进制形式提供给我们的。  
它使用与桌面及移动端 Qt 完全不同的基础架构，不使用 Qt Base 等现有的自由软件。

由于我当时的开发任务与 Qt 无关，没有对该部分内容进行探究及调查，了解到的内容也就止步于此了。

## Qt 6 支持的平台（{{% date 2023 6 14 %}}更新）

参考 {{% QtBug 113979 "Qt 6.6 TQC Supported Targets" %}} 和它的前置任务。

现在我为如下平台构建 Qt 6。

Windows 11 - VS2019, x86_64, host and target  
Windows 11 - MinGW, x86_64, host and target  
macOS 13 - toolchain provided by Apple with AppleClang, x86_64 / arm64_v8a, host and target, universal  
Android - NDK, arm / x86 / arm64 / x86_64, target only. No 32bit builds after 6.3  
WebAssembly - emscripten, target only  
Linux - toolchain provided by RedHat modified by RockyLinux developers with GCC, x86_64, host only

我之后会为如下平台构建 Qt 6。

Windows 11 - VS2019, arm64, target only （咕咕咕了）

Qt 6.2 是 LTS 发布，但是在 Qt offering changes 2020 的影响下，Qt 6.2 对社区发布要比商业用户晚一年。  
我会在 Qt 6.2 添加静态构建，但是我不是很确切的知道 Qt 的那帮人要怎么处理他们的发布。。。

我会在 Qt 6.2 及以后的版本使用 OpenSSL 3 系列。

## GPG 签名 （{{% date 2021 2 6 %}}更新）

我正在找个方法用 GPG 去签名每个包，但是还没有找到好方法。  
我不想在上传包的时候还要再上传一个签名文件，我觉得浪费上传步骤。。。。

（{{% date 2021 2 6 %}}更新）还是没有找到好方法，暂时放放吧。。。

## 弃用 Windows 10 1809 之前的版本以及 32 位 Windows （重要备注！！）（{{% date 2023 3 25 %}}更新）

（{{% date 2023 3 25 %}}更新）由于 Windows 8.1 于 {{% date 2023 1 10 %}}结束生命周期。  
从 {{% date 2023 3 25 %}}开始不再支持 Windows 8.1。VS2015 和 MinGW 7.3 的构建已迁移到 Windows 10。

Qt 6 在 6.2 以前只支持 64 位 Windows 10 1809 以及以后的版本， 6.3 以后只支持最新版本的 Windows 10 （也即 2004 以后的版本，因为这些版本的系统文件均一致）。

从 {{% date 2020 6 3 %}}（Qt 5.15 发布和 Qt 5.9 结束支持）开始，Windows 8.1 上我只支持 VS2015 和 MinGW 7.3 的构建。  
Windows 10 已经变得越来越流行，而且添加更多更多的新特性。大家可以尽快切换到 Windows 10 了。

从 {{% date 2020 1 6 %}}（OpenSSL 1.0.2 系列结束支持）开始，我不再支持 Windows 8 以及更早的版本。请升级到 Windows 8.1 或更新版本。

## 对当前构建的 Qt 版本的已经决定的结束支持日期（{{% date 2023 1 7 %}}更新）

（{{% date 2022 3 4 %}}更新）Qt 公司之前突然发布了开源的 5.15.3 版本，从那以后所有事情都变了。  
我们之前的结束支持计划都没了意义。我们需要重新考虑 5.15 的结束支持日期。

注：我们在除了 WebAssembly 以外的平台上构建 OpenSSL，所有我们的构建都需要至少支持到那个 OpenSSL 支持的日期。  
当前正在使用的是 OpenSSL 1.1.1 系列和 3.0 系列。  
OpenSSL 1.1.1 系列将于 {{% date 2023 9 11 %}}结束支持，而 OpenSSL 3.0 系列则是 {{% date 2026 9 7 %}}。

由于 Qt 5.15.8 开始支持使用 OpenSSL 3.0 系列，在 OpenSSL 1.1 系列结束支持之后，我们可能会在 Qt 5.15 的安卓版构建中切换到 OpenSSL 3.0 系列。  
现在可以确定的是 Qt 5.15 有 5 年的支持，不过目前不清楚 Qt 公司是否会在 {{% date 2024 5 26 %}}之后释放 Qt 5.15 后续版本的代码。  
如果 Qt 5.15 后续版本的代码不公开的话，我们不会再升级到 OpenSSL 3.0 以后的版本。

| Qt 版本 | 构建目标 | 终止支持日期 | 备注 |
|-|-|-|-|
| 5.12 系列 | Windows | {{% date 2023 9 11 %}} | 与 OpenSSL 1.1.1 的终止支持日期保持一致。包含 VS2017/9 的 VS 版本升级。无 VS2022 构建版本。 |
| | ~~macOS~~ | ~~{{% date 2021 11 25 %}}~~ (终止支持) | ~~与 Qt 5.12 系列的终止支持日期保持一致。~~ **在 5.12 终止支持之后 Qt 又发布了一个补丁，为此我们为 macOS 主机构建做了一个额外的包。** |
| | 安卓 | {{% date 2023 9 11 %}} | 与 OpenSSL 1.1.1 的终止支持日期保持一致。会一直使用安卓 NDK r21 LTS 系列。 |
| | ~~WebAssembly~~ | ~~{{% date 2021 11 25 %}}~~ (终止支持) | ~~与 Qt 5.12 系列的终止支持日期保持一致。~~ |
| 5.15 系列 | Windows 11 with VS2019 (动态) / VS2022 | {{% date 2024 5 26 %}} | 与 Qt 开源版 5.15 系列的终止支持日期保持一致。提前更新 WebEngine 和 Script。包含 VS2019/22 的 VS 版本升级。 |
| | Windows with VS2015 / VS2017 / VS2019 (静态) / MinGW 8.1.0 | {{% date 2024 5 26 %}} | 与 Qt 开源版 5.15 系列的终止支持日期保持一致。提前更新 Script。包含 VS2017/9/22 的 VS 版本升级。 |
| | macOS | {{% date 2024 5 26 %}} | 与 Qt 开源版 5.15 系列的终止支持日期保持一致。提前更新 WebEngine 和 Script。（尽可能）包含 Xcode 和 macOS 更新 |
| | 安卓 | {{% date 2026 9 7 %}} | 与 OpenSSL 3.0 的终止支持日期保持一致。 |
| | WebAssembly | {{% date 2024 5 26 %}} | 与 Qt 开源版 5.15 系列的终止支持日期保持一致。 |
| 6.2 Series | Windows 11 with VS2019 (动态) / VS2022 | {{% date 2026 9 7 %}} | 与 OpenSSL 3.0 的终止支持日期保持一致。提前更新 WebEngine。包含 VS 版本升级。 |
| | Windows 11 with VS2019 (静态) | {{% date 2026 9 7 %}} |  与 OpenSSL 3.0 的终止支持日期保持一致。包含 VS 版本升级。  |
| | Windows 11 with MinGW 11.2.0 / MinGW-LLVM 15 | {{% date 2026 9 7 %}} |  与 OpenSSL 3.0 的终止支持日期保持一致。包含 MinGW 版本升级。  |
| | macOS (动态) | {{% date 2026 9 7 %}} | 与 OpenSSL 3.0 的终止支持日期保持一致。提前更新 WebEngine。（尽可能）包含 Xcode 和 macOS 更新 |
| | macOS (静态) | {{% date 2026 9 7 %}} | 与 OpenSSL 3.0 的终止支持日期保持一致。（尽可能）包含 Xcode 和 macOS 更新 |
| | 安卓 | {{% date 2026 9 7 %}} | S与 OpenSSL 3.0 的终止支持日期保持一致。会一直使用安卓 NDK r23 LTS 系列。 |
| | WebAssembly | {{% date 2025 9 29 %}} | 与 Qt 开源版 6.2 系列的终止支持日期保持一致。 |

商业专属的 Qt 版本开源发布日（预计）

| Qt 版本 | 商业专属发布日 | 开源发布日 |
|-|-|-|
| 5.15.11 | {{% date 2022 10 5 %}} | {{% date 2023 10 5 %}} |
| 5.15.12 | {{% date 2022 12 27 %}} | {{% date 2023 12 27 %}} |
| 5.15.13 | {{% date 2023 3 9 %}} | {{% date 2024 3 9 %}} |
| 5.15.14 | {{% date 2023 5 25 %}} | {{% date 2024 5 25 %}} |
| 5.15.15 | {{% date 2023 8 31 %}} | {{% date 2024 8 31 %}} （届时需要确认 Qt 到底是否真的发布了开源版本） |
| 6.2.6 | {{% date 2022 9 27 %}} | {{% date 2023 9 27 %}} |
| 6.2.7 | {{% date 2023 1 2 %}} | {{% date 2024 1 2 %}} |
| 6.2.8 | {{% date 2023 4 18 %}} | {{% date 2024 4 18 %}} |
| 6.2.9 | {{% date 2023 7 4 %}} | {{% date 2024 7 4 %}} |

## 之后可能会更新的内容

~~使用安卓 NDK r23 系列构建 Qt 5.15.7 以及之后的版本。~~ （构建失败了，包括 5.15.10 也失败了，将于 5.15.11 再次尝试）  
~~使用带 MinGW-w64 v9 的 GCC 11 来构建 Qt 5.15.10 以及之后的版本。~~ （5.15.10 上尝试过，失败了，将于 5.15.11 再次尝试）  

## 已有的补丁

从 {{% date 2022 3 12 %}}开始我的 Qt 构建包含部分 Qt 提供的补丁。  
多数是可以从 [Qt 下载站](https://download.qt.io/) 下载的 CVE 补丁，另外一些是可以从 Qt Gerrit 或者 KDE 下载的一些修复构建的补丁。

下面这个表列出了我构建每个版本时所应用的补丁。  
注：我不会对当前正在活跃开发的 Qt 应用补丁，而是单纯等待新版本发布。所以应用补丁的只有商业 LTS 版本和结束生命周期的版本。  
若某个补丁在所有的正在维护的版本均已附带或没有应用的打算，则该补丁将会从此表中删除。  
括号中的版本号为附带该补丁的发布版本。

| 问题 \ Qt 版本 | 5.12.12 | 5.15.10 | 6.2.5 | 6.5.3 （预计） |
|-|-|-|-|-|
| CVE-2022-25255 | [√](https://codereview.qt-project.org/c/qt/qtbase/+/396020) | 附带 | 附带 | 附带 |
| CVE-2022-27404-27405-27406 | - | [√](https://download.qt.io/official_releases/qt/5.15/CVE-2022-27404-27405-27406-qtbase-5.15.diff) （5.15.11） | [√](https://download.qt.io/official_releases/qt/6.2/CVE-2022-27404-27405-27406-qtbase-6.2.diff) （6.2.6） | 附带 |
| CVE-2022-37434 | - | [√](https://download.qt.io/official_releases/qt/5.15/CVE-2022-37434-qtbase-5.15.patch) （5.15.11） | [√](https://download.qt.io/official_releases/qt/6.2/CVE-2022-37434-qtbase-6.2.patch) （6.2.6） | 附带 |
| CVE-2023-24607 | - | [√](https://download.qt.io/official_releases/qt/5.15/CVE-2023-24607-qtbase-5.15.diff) （5.15.13） | [√](https://download.qt.io/official_releases/qt/6.2/CVE-2023-24607-qtbase-6.2.diff) （6.2.8） | 附带 |
| CVE-2023-32573 | - | [√](https://download.qt.io/official_releases/qt/5.15/CVE-2023-32573-qtsvg-5.15.diff) （5.15.14） | [√](https://download.qt.io/official_releases/qt/6.2/CVE-2023-32573-qtsvg-6.2.diff) （6.2.9） | 附带 |
| （仅限 5.15 系列）macOS 构建修复 | - | [仅限 macOS](https://invent.kde.org/qt/qt/qtlocation-mapboxgl/-/commit/5a07e1967dcc925d9def47accadae991436b9686 "KDE 提供的补丁") （5.15.14） | - | - |
| CVE-2023-32762 | - | [√](https://download.qt.io/official_releases/qt/5.15/CVE-2023-32762-qtbase-5.15.diff) （5.15.14） | [√](https://download.qt.io/official_releases/qt/6.2/CVE-2023-32762-qtbase-6.2.diff) （6.2.9） | 附带 |
| CVE-2023-32763 | - | [√](https://download.qt.io/official_releases/qt/5.15/CVE-2023-32763-qtbase-5.15.diff) （5.15.15） | [√](https://download.qt.io/official_releases/qt/6.2/CVE-2023-32763-qtbase-6.2.diff) （6.2.9） | 附带 |
| CVE-2023-33285 | - | [√](https://download.qt.io/official_releases/qt/5.15/CVE-2023-33285-qtbase-5.15.diff) （5.15.14） | [√](https://download.qt.io/official_releases/qt/6.2/CVE-2023-33285-qtbase-6.2.diff) （6.2.9） | 附带 |
| CVE-2023-34410 | - | [√](https://download.qt.io/official_releases/qt/5.15/CVE-2023-34410-qtbase-5.15.diff) （5.15.15） | [√](https://download.qt.io/official_releases/qt/6.2/CVE-2023-34410-qtbase-6.2.diff) （6.2.9） | 附带 |
| CVE-2023-37369 | - | [√](https://download.qt.io/official_releases/qt/5.15/CVE-2023-37369-qtbase-5.15.diff) （5.15.15） | [**×**](# "官方补丁冲突，依赖 Qt 6.2.9 上的一个提交，暂无发行版与项目解决冲突。已放弃调查") （6.2.10） | 附带 |
| CVE-2023-38197 | - | [√](https://download.qt.io/official_releases/qt/5.15/CVE-2023-38197-qtbase-5.15.diff) （5.15.15） | [**×**](# "依赖 CVE-2023-37369 的补丁") （6.2.10） | **x** （6.5.3） |
