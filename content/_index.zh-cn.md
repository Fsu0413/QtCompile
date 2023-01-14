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
使用的代码为从 [这里](http://download.qt.io) 获取的。我没有对源文件/生成的文件进行任何修改。  
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

## 更新记录（仅有嘤文）

### 2023.1.8
Update Qt 6.4.2 / Qt 5.15.8 packages.  
Update Qt 6.2.4 packages built with OpenSSL 3.0.7 with the minor fix.

Qt 6 Linux hosted cross built packages has a problem where the host tool was not properly deployed.  
This time the package is rebuilt with fix.  
Only Qt 6.2.4 Linux hosted WebAssembly package is rebuilt without other modification.

### 2022.11.20
Update all cross built package with CMake toolchain refactored. Currently it can automatically use the bundled host tool using bundled 'qt-cmake' script.  
The updated packages are following:  
Qt 6.2.4 Android / WebAssembly packages  
Qt 6.4.1 Android / WebAssembly packages

### 2022.11.19
Update Qt 6.4.1 WebAssembly macOS host with Thread feature ON. (I did only modified x86_64 build and... I am using arm64 build for base of cross builds and it's gone)

### 2022.11.18
Update Qt 6.4.1.  
Update Qt 6 WebAssembly with Thread feature ON. (Previous versions are missing this feature)   
Update Qt 6 macOS Universal builds. Future Qt 6 builds of macOS will only provide Universal builds.  
Update Qt 6.2.4 Windows VS builds with updated VS version.

### 2022.11.8
Update Qt 6.2.4 with OpenSSL 3.0.7 (Without QtWebEngine since all builds of QtWebEngine failed). Existing patches are all in.  
Update Qt 5.15.7 with OpenSSL 1.1.1s on macOS (Without QtWebEngine).

Qt 6.2.4 cross builds (Linux / macOS host) are packaged with `libexec` folder of host builds where tools like `lrelease` are lying in.

### 2022.11.6
Update Qt 5.15.7 with OpenSSL 1.1.1s (excluding macOS, compile failed in QtWebEngine). Existing patches are all in.   
Update Qt 5.12.12 with OpenSSL 1.1.1s.

### 2022 年 10 月以前

[这里]({{% relref "miscellaneous/histories" %}})
