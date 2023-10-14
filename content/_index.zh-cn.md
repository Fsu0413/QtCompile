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

### {{% date 2023 10 14 %}}
重新构建了所有安卓版本，禁用了 OpenSSL 的线程配置。  
更新 Qt 5.15.11 安卓版本，使用 OpenSSL 3.0.11。

### {{% date 2023 10 12 %}}
误删了 Qt 5.15.10 macOS 的包（带 QtWebEngine 的那个）。因为我没有保留原来的包，它永久消失了。为此带来的不便我表示抱歉。

更新 Qt 6.6.0，附带 OpenSSL 3.0.11。   
更新 Qt 6.5.3 的安卓 arm （32位）版本（重新支持）。

### {{% date 2023 10 8 %}}
更新 Qt 5.15.11 / 6.2.6 / 6.5.3，使用 OpenSSL 1.1.1w / 3.0.11。  
对于所有受支持的 5.15.11 版本，应用 CVE-2023-4863 补丁。（此补丁在 6.2.6 上有冲突）    
对于所有受支持的 5.15.11 和 6.2.6 版本，应用 CVE-2023-43114 补丁。  
更新 MariaDB Connector C 到 3.3.7 / 3.1.22。

### {{% date 2023 10 6 %}}
更新 Qt 5.12.12，使用 OpenSSL 1.1.1w。

由于 OpenSSL 1.1.1 系列已经结束生命周期，不会再有 Qt 5.12 的构建了。  
也就是说这次的构建是这些包的最后一次构建了。  
Qt 5.12 系列的构建脚本和环境都爆破了。

### 2023 年 9 月以前

[这里]({{% relref "miscellaneous/histories" %}})
