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

### {{% date 2023 3 25 %}}
更新 OpenSSL 1.1.1t / 3.0.8，附带 [微小更新](https://www.openssl.org/news/secadv/20230322.txt)。  
更新 Qt 5.12.12 / 5.15.8 / 6.2.4，使用这份 OpenSSL 重新构建，其中 5.15.8 附带 QtWebEngine 5.15.13。   
更新 Qt 6.4.3 和 Qt 6.5.0-rc。

由于 Windows 8.1 结束生命周期，之前使用 Windows 8.1 构建的版本迁移到 Windows 10 10.0.19045 重新构建。  
之后的构建不会再支持 Windows 8.1。

（第二次）祝基神奄（Iroi Imagay）生日快乐！！

### {{% date 2023 2 25 %}}
更新 Qt 6.5.0-beta3 系列，使用 NDK r25c 构建，附带内建的 MySQL （MariaDB）数据库后端及插件。

### {{% date 2023 2 12 %}}
更新 Qt 6.4.2 系列，使用 NDK r25c 构建。

### {{% date 2023 2 10 %}}
更新 Qt 5.12.12 / 5.15.8 / 6.2.4 / 6.4.2 系列，附带 OpenSSL 1.1.1t / 3.0.8。  
更新 Qt 5.15 / 6.2 / 6.4 系列，附带内建的 MySQL （MariaDB）数据库后端及插件。  
使用更多 Visual Studio 版本对 Qt 5.15 系列进行静态 `full` 构建。不再继续对 Qt 5.12 进行静态 `full` 构建。

### 2023 年 1 月以前

[这里]({{% relref "miscellaneous/histories" %}})
