---
title: "Fsu0413 的原版 Qt 构建"
draft: false
archetype: "home"
---

{{% notice style="info" title="备注"  icon="fas fa-info-circle" %}}
OSDN 目前发生技术问题，上传下载均有问题。  
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

### {{% date 2023 8 5 %}}
更新 Qt 5.12.12。  
更新 Qt 5.15.10。应用 CVE-2023-37369 和 CVE-2023-38197 的补丁。  
更新 Qt 6.2.5。  
更新 Qt 6.5.2。

更新 OpenSSL 到 3.0.10 / 1.1.1v。

### {{% date 2023 6 14 %}}
更新 Qt 5.15.10 系列，附带 QtWebEngine 和 QtScript 5.15.14。  
对于所有受支持的 5.15.10 和 6.2.4 版本，应用 CVE-2023-34410 补丁。  
更新 LLVM-MinGW 到 20230603。重新构建了 Qt 6.2.4 和 Qt 6.5.1 的 LLVM-MinGW 的包。

删除原 OSDN Chamber。文件上传下载服务转移到 Project。

### {{% date 2023 6 3 %}}
对于所有受支持的 5.15.9 和 6.2.4 版本，应用 CVE-2023-33285 补丁。  
更新 Qt 5.15.9 系列，附带 QtWebEngine 和 QtScript 5.15.14。  
更新 Qt 6.5 系列至 6.5.1。  
更新 OpenSSL 到 3.0.9 / 1.1.1u。所有使用了 OpenSSL 的版本均重新构建了。  
更新 MariaDB Connector C 到 3.3.5 / 3.1.21。所有使用了 MariaDB Connector C 的版本均重新构建了。

（原计划在 {{% date 2023 5 31 %}}有一次更新。不过因为 OSDN 的服务不太稳定，加上 CVE-2023-33285 补丁发布，此更新取消了）

### 2023 年 5 月以前

[这里]({{% relref "miscellaneous/histories" %}})
