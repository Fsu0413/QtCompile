---
title: "Fsu0413 的原版 Qt 构建"
draft: false
---

# Fsu0413 的原版 Qt 构建

## 停止使用 Notepad++

{{% date 2023 1 25 %}} Notepad++ 发布的版本中，添加了一个“功能”，里面要求用户同意并接受其中关于中国的虚假、不正确和误导性的政治言论。  
如果用户不同意、不接受的话，在使用 Notepad++ 编辑文字时会被添加随机字符。

作为中国人，我在此声明：  
**中国的各个省、直辖市、自治区和特别行政区，包括港澳台、新疆和西藏，都是中国领土的一部分。**   
**我拒绝接受一切不尊重中国国家主权及领土完整的言论。**

我（Fsu0413）作为来自中国的中国码农，不会再使用 Notepad++，也不会再支持 Notepad++ 用户。  
我也呼吁我的网站的所有用户停止使用 Notepad++ 并寻找替代方案。

我不会对替代方案提供任何建议。  
现在外面有 [非常多的基于 Scintilla 的编辑器](https://www.texteditors.org/cgi-bin/wiki.pl?ScintillaEditorFamily) ，我相信你一定会找到你想要的那个。

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

### {{% date 2023 5 22 %}}
对于所有受支持的 5.15.9 和 6.2.4 版本，应用 CVE-2023-32762 和 CVE-2023-32763 补丁。  
为 macOS 的 5.15.9 版本应用 mapbox-gl-native 构建问题的补丁。

### {{% date 2023 5 20 %}}
更新 macOS 到 13.3.1。更新 Xcode 到 14.3。  
更新 Qt 5.15.9 统一二进制主机构建以及 arm64 主机版交叉构建。   
更新 Qt 6.2.4 和 6.5.0 的 UCRT 版本的 MinGW-w64 GCC 构建。

对于所有受支持的 5.15.9 和 6.2.4 版本，应用 CVE-2023-32573 补丁。

### {{% date 2023 5 11 %}}
使用 OSDN 项目代替 Chamber （或者叫做 PersonalForge）提供文件服务。

### {{% date 2023 5 9 %}}
更新 Qt 5.15.9 / 6.5.0。  
删除 Qt 6.4 系列。

OpenSSL 于 {{% date 2023 4 20 %}}发布的 [微小更新](https://www.openssl.org/news/secadv/20230420.txt) 仅适用于 ASM 构建的 OpenSSL 二进制文件。  
由于我构建的 OpenSSL 均为非 ASM 构建，所以对我的构建没有影响。此更新不会被应用到我构建的版本中。

### 2023 年 3 月以前

[这里]({{% relref "miscellaneous/histories" %}})
