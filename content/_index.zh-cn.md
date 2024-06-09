{
  "title": "Fsu0413 的原版 Qt 构建",
  "archetype": "home",
  "description": "个人构建的 Qt 4 以后的版本，附带内置的 SSL。包含多种选项。"
}

## 免责声明

这些由 Fsu0413 构建的二进制文件 __完全未经测试__ ，使用时请自行承担风险。  
使用的代码为从 [这里](http://download.qt.io) 获取的，并且为了应对一些微小并且简单的编译 / 构建问题，所应用的补丁[见这里](/Miscellaneous/NotesForThisRepo#已有的补丁)。  
__这些包为“依原样”提供。我对您使用此二进制文件作出的任何事情不负任何责任。__  
感谢 The Qt Company Ltd. 和众多 Qt 的开发者的绝妙工作！

## 更新记录

### {{% date 2024 6 9 %}}
更新 OpenSSL 到 3.0.13。  
使用 llvm-mingw 18.1.7 重新构建所有使用 llvm-mingw 18 系列工具链的版本。  
更新 Visual Studio 2022 到 17.10.1。

### {{% date 2024 5 28 %}}
更新 Qt 5.15.14 / 6.7.1。   
为所有支持的版本应用 CVE-2024-36048 的补丁，所有包都重新构建了。   
使用 llvm-mingw 18.1.6 重新构建所有使用 llvm-mingw 18 系列工具链的版本。

升级 macOS （arm64） 到 14.5，并且更新 Xcode 到附带 AppleClang 15.0.0 的版本。

正如我在 6.2 上做的一样，我已经开始逐步终止 Qt 6.5 系列上的 QtWebEngine 支持。    
当前 macOS 上已经出现构建失败的情况，所以构建已经禁用，并且不会再于 macOS 平台上再次启用。    
如果 MSVC 也出现这个情况的话，我也会直接给它禁止掉。

### {{% date 2024 5 12 %}}
重新构建了所有的 Qt 6 静态版本。删掉了里面的内置 OpenSSL。  
原因是有[报](https://github.com/Fsu0413/QtCompile/issues/25)[告](https://github.com/Fsu0413/QtCompile/issues/22)说没了 OpenSSL 的头文件，Qt 用不了。

使用 llvm-mingw 18.1.5 重新构建除 Qt 6.7 外的使用 llvm-mingw 18 系列工具链的版本。

重新构建了 Qt 5.15 MinGW （GCC 11.2.0 及以后，LLVM 的所有）版本，修复一个导致 MySQL （MariaDB）插件没有构建的问题。

### {{% date 2024 4 19 %}}以前

[这里](/Miscellaneous/Histories)
