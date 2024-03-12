---
title: "Fsu0413 的原版 Qt 构建"
draft: false
archetype: "home"
---

{{% notice style="info" title="备注"  icon="fas fa-info-circle" %}}
OSDN 目前发生技术问题，上传下载均有问题。  
目前已经删除所有 OSDN 链接，拜托各位通过 SourceForge 进行下载。

这边上传的时候发生的错误如下（通过 WinSCP 输出）：

{{% expand %}}
一般错误(服务器应该提供错误描述)。  
错误码：4  
服务器返回的错误消息：Failure


错误码4的常见原因：
- 将文件重命名为一个已经存在的文件。
- 创建一个已经存在的目录。
- 将远程文件移动到一个不同的文件系统（HDD）上。
- 将文件上传到一个满的文件系统（HDD）上。
- 达到了用户磁盘限额。
{{% /expand %}}
{{% /notice %}}

## 免责声明

这些由 Fsu0413 构建的二进制文件 __完全未经测试__ ，使用时请自行承担风险。  
使用的代码为从 [这里](http://download.qt.io) 获取的，并且为了应对一些微小并且简单的编译 / 构建问题，所应用的补丁[见这里](/Miscellaneous/NotesForThisRepo#已有的补丁)。  
__这些包为“依原样”提供。我对您使用此二进制文件作出的任何事情不负任何责任。__  
感谢 The Qt Company Ltd. 和众多 Qt 的开发者的绝妙工作！

## 更新记录

### {{% date 2024 3 12 %}}
更新 Qt 5.15.13。  
更新 Visual Studio 2022 到 17.9.2。

为 Qt 5.15 系列打上一些补丁，使之可以在更新的 MinGW-w64 和更新的安卓 NDK 上构建通过。

### {{% date 2024 2 17 %}}
更新 Qt 6.6.2。  
为所有长期支持版本的 Qt 应用 CVE-2024-25580 的补丁。  
复原安卓 API Level，原因是使用提升了的 API Level 构建 Qt 会导致低版本安卓无法安装使用这份 Qt 的程序。

删除 Windows 平台使用 MinGW-LLVM 15.0.0 的构建。

### {{% date 2024 2 7 %}}
更新 Qt 5.15、6.2.7 和 6.5.3 的安卓版，提升了 API level。  
更新 OpenSSL 到 3.0.13。

### 2024 年以前

[这里](/Miscellaneous/Histories)
