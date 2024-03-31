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

## `xz` 后门

听闻 `xz` 上游被一个深受信任的维护者添加了后门后，我虎躯一震。  
所有目前已有的调查结果表明这个后门来自一个叫 JiaT75 的家伙，而且揭露这个后门只在 x86_64 架构、使用 systemd 的 Linux 发行版上运行，用来注入 OpenSSH 以建立未认证的连接。并不是为了在压缩 / 解压缩时对文件做手脚。

此项目生成的 XZ 包并**不**使用原来的 `xz` 工具进行压缩的。而是使用（在 Windows 上）Igor Pavlov 维护的 `7z` 或者（在非 Windows 上）jinfeihan57 维护的 `p7zip`。  
但是在构建其他包时，为了解压缩类似 OpenSSL、MariaDB 以及 Qt 静态 `Lite` 的依赖包，调用的命令还是 `tar -xjf xxx.tar.xz`。这一步还是会使用到原来的 `xz` 程序。

现在我使用的所有的 Linux 构建用电脑均使用基于 RHEL 的 Rocky Linux。因为 Rocky Linux 类似 RHEL 一样不更新软件的大版本，我们可能没有受到影响。  
但是这个家伙的代码同时存在于 `libarchive`（在 macOS 和 Windows 上存在。`bsdtar` 来源于这个库）中。`libarchive` 目前已经开始重新评审这个家伙所做的代码了。

这一部分内容会在事情明朗之前一直放在这里，我将持续关注相关内容。如果有必要的话，我可能会对所有这个版本库中的内容做重新打包。

在 `xz` 的官网上 Lasse Collin（`xz` 的最初维护者）的[发文](https://tukaani.org/xz-backdoor/)中可以找到更多信息。（但是我这边需要使用魔法才可以访问）

## 免责声明

这些由 Fsu0413 构建的二进制文件 __完全未经测试__ ，使用时请自行承担风险。  
使用的代码为从 [这里](http://download.qt.io) 获取的，并且为了应对一些微小并且简单的编译 / 构建问题，所应用的补丁[见这里](/Miscellaneous/NotesForThisRepo#已有的补丁)。  
__这些包为“依原样”提供。我对您使用此二进制文件作出的任何事情不负任何责任。__  
感谢 The Qt Company Ltd. 和众多 Qt 的开发者的绝妙工作！

## 更新记录

### {{% date 2024 3 28 %}}
更新 Qt 6.6.3 和 Qt 6.7.0-rc2 版本。   
重新构建了 VS2022 和 llvm-mingw 18 的 Qt 5.15 / 6.2 / 6.5 版本。

Qt 6 正在迁移 MinGW 构建，从基于 GCC 的工具链到使用 [llvm-mingw](https://github.com/mstorsjo/llvm-mingw) 的基于 LLVM 的工具链。    
我也建议 MinGW 的使用者迁移过去，因为使用 LLVM 构建更快，生成更小的二进制文件，并且也支持 Windows on ARM（虽然我还没有调查在 WoA 上使用 llvm-mingw）。  
详情参考 {{% QtBug 107516 %}}。

### {{% date 2024 3 25 %}} 无更新
增加 Qt 5.15 部分 MySQL 后端构建失败的备注。  
简单调查 llvm 在 Windows 上的构建。

（第三次）祝基神奄（Iroi Imagay）生日快乐！！

### {{% date 2024 3 23 %}}
添加 Windows on ARM64 的 Qt 5.15 系列构建。   

### {{% date 2024 3 18 %}}以前

[这里](/Miscellaneous/Histories)
