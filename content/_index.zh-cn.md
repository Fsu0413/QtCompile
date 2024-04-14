{
  "title": "Fsu0413 的原版 Qt 构建",
  "archetype": "home"
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

## 免责声明

这些由 Fsu0413 构建的二进制文件 __完全未经测试__ ，使用时请自行承担风险。  
使用的代码为从 [这里](http://download.qt.io) 获取的，并且为了应对一些微小并且简单的编译 / 构建问题，所应用的补丁[见这里](/Miscellaneous/NotesForThisRepo#已有的补丁)。  
__这些包为“依原样”提供。我对您使用此二进制文件作出的任何事情不负任何责任。__  
感谢 The Qt Company Ltd. 和众多 Qt 的开发者的绝妙工作！

## 更新记录

### {{% date 2024 4 13 %}}
使用 NDK r26d 重新构建所有使用 NDK r26 系列工具链的版本。

（第 32 次）祝我生日快乐！

### {{% date 2024 4 6 %}}
使用 llvm-mingw 18.1.3 重新构建所有使用 llvm-mingw 18 系列工具链的版本。

### {{% date 2024 4 3 %}}
更新 Qt 6.7.0 版本。

### 2024 年 4 月以前

[这里](/Miscellaneous/Histories)
