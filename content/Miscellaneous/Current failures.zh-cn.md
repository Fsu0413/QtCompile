---
title: "当前的失败项"
draft: false
weight: 3
---

## Qt 5.12 以后的 QDoc 使用 MSVC 构建时无法使用静态链接的 clang

它使用 `libclang_static.lib` 但是 clang 构建中没有这个文件。  
我决定在找到使用静态链接的 clang 方法之前，不再提供基于 LLVM 的 QDoc。

{{% date 2020 11 3 %}}更新：  
`libclang_static.lib` 是 Qt 那帮人自己使用脚本打包的。  
非常感谢 QtCN 的 lixinwei 提供相关信息。 [原帖参考](http://www.qtcn.org/bbs/job.php?action=topost&tid=85983&pid=200952)

## 使用 MinGW 构建 Qt 6.2 系列时命令行过长

参考 {{% QtBug 96339 %}} - 暂时使用 CMake 3.20.2 绕过这个问题

## QtOpcUa 的问题

目前 QtOpcUa 与 OpenSSL 3.0 系列存在兼容性问题。  
在 Qt 那帮人更新他们自己的 open62541 版本之前，暂时禁用 QtOpcUa 的构建。  
这个修改将于 Qt 6.2.3 的构建和打包时落实。

看起来 open62541 那帮人并没有把这件事当成问题，即使 OpenSSL 3.0 系列现在已经逐渐流行。  
1.3.3 版本发布但是还是没有关于 OpenSSL 3.0 的修正。  
~~我不清楚是否我们可以把 QtOpcUa 带回到 Qt 6.4 了。。。。~~

{{% date 2022 11 6 %}}更新：  
open62541 没有在 1.3.3 版本之后发布任何新版本，所以 QtOpcUa 6.4 不会有 open62541 的 OpenSSL 3.0 支持。  
目前在 GitHub 上有一个已经合入的 Pull Request 添加了 OpenSSL 3.0 支持。参考 [Github Pull Request](https://github.com/open62541/open62541/pull/5349)。  
下一个版本的 open62541 就会包含这个修改，届时我会重新启用 QtOpcUa 的构建。

{{% date 2023 1 23 %}}更新：  
open62541 于 {{% date 2022 11 14 %}}发布了 1.3.4 版本。QtOpcUa 6.5 更新附带的 open62541 附带的就是这个版本。  
我将于 Qt 6.5 的构建上重新尝试启用 QtOpcUa 模块进行构建。（{{% date 2023 1 23 %}}之前的构建中没有此模块）

## 使用更高版本的 QtWebEngine 构建 Qt 6.2.4 产生的多种多样的失败

在 macOS 上使用 Xcode 14.1 构建带有 QtWebEngine 6.3.2 的 Qt 6.2.4 会失败。使用 Xcode 14.0.1 的时候还是好的。可能是因为 QtWebEngine 6.3.2 不兼容 macOS Ventura SDK。  
在 macOS 和 Windows 上构建带有 QtWebEngine 6.4.0 的 Qt 6.2.4 会失败。在 `gn` 过程中还是好的，但是出了 `gn` 就失败。Windows 和 macOS 上的错误不同。

我懒得再调查这些错误了，以后发布 Qt 6.2 系列的时候将不带 QtWebEngine。  
QtWebEngine 自从 6.2.4 之后就没再针对 LTS 版本发布新版，而是直接拿更新的 QtWebEngine（比如 6.3 之类的）作为 6.2 LTS 系列发布。  
但是因为 QtWebEngine 的二进制文件的版本号和实际版本号不同，除了官方打包负责人之外没人知道 Qt 具体用了 QtWebEngine 的哪个版本来打包的。

{{% date 2023 3 25%}}更新：  
QtWebEngine 依然在其自己的分支上开发，但是只有 `qtwebengine-chromium` 仓库对外公开了。  
Qt 公司在他们自己的 yocto 仓库 `meta-qt6` 中记录了所有发布版本的 commit SHA1，但是在 `qtwebengine` 仓库中找不到对应的 commit。  
如果强行使用不匹配的 `qtwebengine` 和 `qtwebengine-chromium` 版本对 QtWebEngine 进行构建的话我觉得也不会通过。即使我们足够幸运构建通过了，我也不认为它能正确工作。

所以我不会再提供附带 QtWebEngine 的 Qt 6.2 LTS 系列的版本。  
现有的附带 QtWebEngine 的版本将于 {{% date 2023 3 25 %}}更新后删除。

## CVE-2023-37369 的补丁与 Qt 6.2.4 / 6.2.5 冲突

这个补丁是为 Qt 6.2.9 而做，而该版本包含了一个与 Qt 6.2.4 / 6.2.5 不兼容的修改。  
我之前基于 Qt 6.2.4 做了个补丁修复了冲突，不过这个补丁和 6.2.5 再次发生冲突。

在 Qt 6.2.9 发布之前，我不会再应用此补丁，除非有打包人员 / Linux 发行版注意到了这个问题并做成补丁。

后续有一个 CVE-2023-38197 的补丁，但是是基于 CVE-2023-37369 所做，所以同样不能应用。
