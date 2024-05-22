{
  "title": "Fsu0413 的原版 Qt 构建",
  "archetype": "home",
  "description": "个人构建的 Qt 4 以后的版本，附带内置的 SSL。包含多种选项。"
}

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

## Windows 电脑坏了

### {{% date 2024 5 20 %}}
我 Windows 系统的电脑坏了，暂时没法更新。  
目前看到的是 CVE-2024-36048 的补丁， Qt 5.15.14 with QtWebEngine 5.15.17，Qt 6.7.1 需要在我电脑修好之后再更新了。

## 免责声明

这些由 Fsu0413 构建的二进制文件 __完全未经测试__ ，使用时请自行承担风险。  
使用的代码为从 [这里](http://download.qt.io) 获取的，并且为了应对一些微小并且简单的编译 / 构建问题，所应用的补丁[见这里](/Miscellaneous/NotesForThisRepo#已有的补丁)。  
__这些包为“依原样”提供。我对您使用此二进制文件作出的任何事情不负任何责任。__  
感谢 The Qt Company Ltd. 和众多 Qt 的开发者的绝妙工作！

## 更新记录

### {{% date 2024 5 12 %}}
重新构建了所有的 Qt 6 静态版本。删掉了里面的内置 OpenSSL。  
原因是有[报](https://github.com/Fsu0413/QtCompile/issues/25)[告](https://github.com/Fsu0413/QtCompile/issues/22)说没了 OpenSSL 的头文件，Qt 用不了。

使用 llvm-mingw 18.1.5 重新构建除 Qt 6.7 外的使用 llvm-mingw 18 系列工具链的版本。

重新构建了 Qt 5.15 MinGW （GCC 11.2.0 及以后，LLVM 的所有）版本，修复一个导致 MySQL （MariaDB）插件没有构建的问题。

### {{% date 2024 4 19 %}}
更新 Qt 6.2.8。  
使用 llvm-mingw 18.1.4 重新构建所有使用 llvm-mingw 18 系列工具链的版本。

鉴于现在已经没有更多计划的 Qt 6 构建，我把“Qt 6 支持的平台”章节从备注页中删掉了。   
最初的 Qt 6.0 已经发布超过 3 年了，所有计划的构建目标都已经达成了。这个章节已经没用了。

### {{% date 2024 4 17 %}}以前

[这里](/Miscellaneous/Histories)
