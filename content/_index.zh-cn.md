---
title: "Fsu0413 的原版 Qt 构建"
draft: false
---

# Fsu0413 的原版 Qt 构建

## 中文 / 多语言支持

虽然这个网站的维护者（Fsu0413，也就是我）是中国人，是中文母语使用者，不过此网站最初做成的时候是只有嘤文版的。  
目前我正在逐步在此网站上添加简体中文支持。

得益于 [Hugo](https://gohugo.io/) 自带的多语言支持和近期新换的 [Relearn](https://mcshelby.github.io/hugo-theme-relearn/) 主题，本网站近期刚刚支持多语言。  
目前的中文也仅仅处于刚刚开始组织语言的阶段。有一些内容还没有写完。  
不过主要内容均使用中文重新写了一遍，应该不会影响大家下载二进制文件了。

对网站建设有建议和意见的可以去 GitHub 上提出 issue。

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

### 2022.11.6
Update Qt 5.15.7 with OpenSSL 1.1.1s (excluding macOS, compile failed in QtWebEngine). Existing patches are all in.   
Update Qt 5.12.12 with OpenSSL 1.1.1s.

### 2022.10.4
Update Qt 6.4.0.  
Update Qt 6.2.4 static builds with static runtime. Previous versions are without it.  
Update Qt 6.2.4 llvm-mingw builds built with llvm 15.

Qt 6.3 builds are removed.

### 2022.9.16
Update Qt 6.2.4 / 5.15.6 with updated patch of CVE-2022-37434. Qt 6.2 are rebuilt with QtWebEngine 6.3.2.  
Update to Xcode 14 and rebuild all of macOS hosted Qt 6.2 onwards.

### 2022.9.12
Update Qt 6.2.4 / 6.3.2 WebAssembly packages. They are currently built using PCH.  
Update Qt 6.2.4 / 6.3.2 llvm-mingw packages. They are currently built with WMF support.  
Update Qt 6.4.0-beta4. All configuration from previous 6.3 are available. RockyLinux 9 is used for Qt 6.4.0 Linux hosted build. WebAssembly and llvm-mingw packages are built using updated configuration today.

### 2022.9.11
Update Qt 6.3.2 with OpenSSL 3.0.5.  
Update Qt 6.2.4 with patch of CVE-2022-37434.  
Update Qt 5.15.6 with OpenSSL 1.1.1q. Existing patch are all in. Patch of CVE-2022-27404-27405-27406 and CVE-2022-37434 are added.  
Update Qt 5.12.12 macOS hosted Android builds which erroneously used CommandLineTools instead of Xcode as host build toolchain.

### 2022 年 8 月以前

[这里]({{% relref "miscellaneous/histories" %}})
