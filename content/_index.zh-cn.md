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

### {{% date 2024 6 22 %}}
更新 Qt 6.7.2。  
使用 llvm-mingw 18.1.8 重新构建所有使用 llvm-mingw 18 系列工具链的版本。  
更新 Visual Studio 2022 到 17.10.1。  
更新 Visual Studio 2019 到 16.11.37。  
更新 Visual Studio 2017 到 15.9.63。

### {{% date 2024 6 9 %}}
更新 OpenSSL 到 3.0.13。  
使用 llvm-mingw 18.1.7 重新构建所有使用 llvm-mingw 18 系列工具链的版本。  
更新 Visual Studio 2022 到 17.10.1。

### {{% date 2024 5 28 %}}以前

[这里](/Miscellaneous/Histories)
