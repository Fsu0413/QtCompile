---
title: "Fsu0413 的原版 Qt 构建"
draft: false
---

# Fsu0413 的原版 Qt 构建

## 网站镜像

最近我在中国大陆使用 Gitee Pages 服务构建了一个此网站的镜像。  
这个镜像配置的默认语言改为简体中文。

由于 Gitee 的自定义域名服务只提供给付费用户，目前中文站是在 Gitee 的域名下的。  
如果之后我对此服务感觉不错的话，我可能会付费使用这个服务。

[Gitee Pages （中国大陆，使用简体中文作为默认语言）](https://fsu0413.gitee.io/qtcompile/)  
[Github Pages （美国，使用英语作为默认语言）](https://build-qt.fsu0413.me/)

## 免责声明

这些由 Fsu0413 构建的二进制文件 __完全未经测试__ ，使用时请自行承担风险。  
使用的代码为从 [这里](http://download.qt.io) 获取的。我没有对源文件/生成的文件进行官方发布的补丁以外的任何修改。  
__这些包为“依原样”提供。我对您使用此二进制文件作出的任何事情不负任何责任。__  
感谢 The Qt Company Ltd. 和众多 Qt 的开发者的绝妙工作！

## 本版本库的一些备注

[这里]({{% relref "miscellaneous/notes for this repo" %}})

## 当前构建状况

[这里]({{% relref "miscellaneous/current build status" %}})

## 下载

参考左侧的目录。

## 当前的失败项

[这里]({{% relref "miscellaneous/current failures" %}})

## 更新记录

### 2023.1.8
更新 Qt 6.4.2 / 5.15.8 包。  
更新 Qt 6.2.4 包，构建时使用带 [微小更新](https://www.openssl.org/news/secadv/20221213.txt) 的 OpenSSL 3.0.7。

此前 Qt 6 Linux 主机版的交叉构建包存在问题，导致主机工具没有正确部署。  
本次的包修复了此问题。

### 2022.11.20
更新所有的交叉构建包，重构 CMake 工具链。现在可以用包里附带的 `qt-cmake` 脚本自动调用在同一个包中分发的主机工具了。  
Qt 6.2.4 / 6.4.1，安卓 / WebAssembly 包全部进行了更新。

### 2022.11.19
更新 Qt 6.4.1 WebAssembly macOS 主机构建，打开线程功能。（我之前只修改了 x86_64 构建，然后在我构建统一架构版本时用了 arm64 当基础，然后这个功能就不见了）

### 2022.11.18
更新 Qt 6.4.1。  
更新 Qt 6 WebAssembly 构建，打开线程功能。（之前的版本缺失这个功能）  
更新 Qt 6 macOS 统一架构构建。以后的 Qt 6 macOS 构建均会是统一架构构建。  
更新 Qt 6 Windows VS 构建，升级 VS 版本。

### 2022.11.8
更新 Qt 6.2.4，附带 OpenSSL 3.0.7（不再附带 QtWebEngine 因为所有的 QtWebEngine 构建均失败了）。现有补丁全部应用。  
更新 Qt 5.15.7，附带 OpenSSL 1.1.1s（不附带 QtWebEngine）。

Qt 6.2.4 的 Linux 和 macOS 主机交叉构建版在打包时额外附带主机版的 `libexec` 文件夹。一些诸如 `lrelease` 一类的工具在这个文件夹里面。

### 2022.11.6
更新 Qt 5.15.7，附带 OpenSSL 1.1.1s（macOS 除外，QtWebEngine 编译失败了）。现有补丁全部应用。  
更新 Qt 5.12.12，附带 OpenSSL 1.1.1s。

### 2022 年 10 月以前

[这里]({{% relref "miscellaneous/histories" %}})
