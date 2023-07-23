---
title: "之前的历史"
draft: false
weight: 4
---

## {{% date 2023 5 22 %}}
对于所有受支持的 5.15.9 和 6.2.4 版本，应用 CVE-2023-32762 和 CVE-2023-32763 补丁。  
为 macOS 的 5.15.9 版本应用 mapbox-gl-native 构建问题的补丁。

## {{% date 2023 5 20 %}}
更新 macOS 到 13.3.1。更新 Xcode 到 14.3。  
更新 Qt 5.15.9 统一二进制主机构建以及 arm64 主机版交叉构建。   
更新 Qt 6.2.4 和 6.5.0 的 UCRT 版本的 MinGW-w64 GCC 构建。

对于所有受支持的 5.15.9 和 6.2.4 版本，应用 CVE-2023-32573 补丁。

## {{% date 2023 5 11 %}}
使用 OSDN 项目代替 Chamber （或者叫做 PersonalForge）提供文件服务。Chamber 不会再更新并将于一段时间后删除。

## {{% date 2023 5 9 %}}
更新 Qt 5.15.9 / 6.5.0。  
删除 Qt 6.4 系列。

OpenSSL 于 {{% date 2023 4 20 %}}发布的 [微小更新](https://www.openssl.org/news/secadv/20230420.txt) 仅适用于 ASM 构建的 OpenSSL 二进制文件。  
由于我构建的 OpenSSL 均为非 ASM 构建，所以对我的构建没有影响。此更新不会被应用到我构建的版本中。

## {{% date 2023 3 25 %}}
更新 OpenSSL 1.1.1t / 3.0.8，附带 [微小更新](https://www.openssl.org/news/secadv/20230322.txt)。  
更新 Qt 5.12.12 / 5.15.8 / 6.2.4，使用这份 OpenSSL 重新构建，其中 5.15.8 附带 QtWebEngine 5.15.13。   
更新 Qt 6.4.3 和 Qt 6.5.0-rc。

由于 Windows 8.1 结束生命周期，之前使用 Windows 8.1 构建的版本迁移到 Windows 10 10.0.19045 重新构建。  
之后的构建不会再支持 Windows 8.1。

（第二次）祝基神奄（Iroi Imagay）生日快乐！！

## {{% date 2023 2 25 %}}
更新 Qt 6.5.0-beta3 系列，使用 NDK r25c 构建，附带内建的 MySQL （MariaDB）数据库后端及插件。

## {{% date 2023 2 12 %}}
更新 Qt 6.4.2 系列，使用 NDK r25c 构建。

## {{% date 2023 2 10 %}}
更新 Qt 5.12.12 / 5.15.8 / 6.2.4 / 6.4.2 系列，附带 OpenSSL 1.1.1t / 3.0.8。  
更新 Qt 5.15 / 6.2 / 6.4 系列，附带内建的 MySQL （MariaDB）数据库后端及插件。  
使用更多 Visual Studio 版本对 Qt 5.15 系列进行静态 `full` 构建。不再继续对 Qt 5.12 进行静态 `full` 构建。

## {{% date 2023 1 28 %}}
更新 Qt 6.5.0-beta2 包。（含有 QtOpcUa）  
更新 Qt 6.2.4 静态 `full` 构建。提供一个对 {{% QtBug 102877 %}} 的绕过方案。

## {{% date 2023 1 23 %}}
更新 Qt 6.5.0-beta1 包。（没有 QtOpcUa）  
更新 Qt 6.2.4 / Qt 6.4.2，在 Windows 上带上静态的 `libgcc` 。之前的版本依赖 `libgcc` 的 DLL。受影响的版本是所有的交叉构建版和静态 `full` 构建。

## {{% date 2023 1 8 %}}
更新 Qt 6.4.2 / 5.15.8 包。  
更新 Qt 6.2.4 包，构建时使用带 [微小更新](https://www.openssl.org/news/secadv/20221213.txt) 的 OpenSSL 3.0.7。

此前 Qt 6 Linux 主机版的交叉构建包存在问题，导致主机工具没有正确部署。  
本次的包修复了此问题。

## {{% date 2022 11 20 %}}
更新所有的交叉构建包，重构 CMake 工具链。现在可以用包里附带的 `qt-cmake` 脚本自动调用在同一个包中分发的主机工具了。  
Qt 6.2.4 / 6.4.1，安卓 / WebAssembly 包全部进行了更新。

## {{% date 2022 11 19 %}}
更新 Qt 6.4.1 WebAssembly macOS 主机构建，打开线程功能。（我之前只修改了 x86_64 构建，然后在我构建统一架构版本时用了 arm64 当基础，然后这个功能就不见了）

## {{% date 2022 11 18 %}}
更新 Qt 6.4.1。  
更新 Qt 6 WebAssembly 构建，打开线程功能。（之前的版本缺失这个功能）  
更新 Qt 6 macOS 统一架构构建。以后的 Qt 6 macOS 构建均会是统一架构构建。  
更新 Qt 6 Windows VS 构建，升级 VS 版本。

## {{% date 2022 11 8 %}}
更新 Qt 6.2.4，附带 OpenSSL 3.0.7（不再附带 QtWebEngine 因为所有的 QtWebEngine 构建均失败了）。现有补丁全部应用。  
更新 Qt 5.15.7，附带 OpenSSL 1.1.1s（不附带 QtWebEngine）。

Qt 6.2.4 的 Linux 和 macOS 主机交叉构建版在打包时额外附带主机版的 `libexec` 文件夹。一些诸如 `lrelease` 一类的工具在这个文件夹里面。

## {{% date 2022 11 6 %}}
更新 Qt 5.15.7，附带 OpenSSL 1.1.1s（macOS 除外，QtWebEngine 编译失败了）。现有补丁全部应用。  
更新 Qt 5.12.12，附带 OpenSSL 1.1.1s。

网站重新构建，更换主题为有更好多语言支持的 [Relearn](https://mcshelby.github.io/hugo-theme-relearn/) 。  
网站添加简体中文。

## {{% date 2022 10 4 %}}
更新 Qt 6.4.0。  
更新 Qt 6.2.4 静态构建，使用静态运行时。以前的版本不使用静态运行时。  
更新 Qt 6.2.4 LLVM-MinGW 构建。使用 LLVM 15。

删除 Qt 6.3 系列的构建。

## {{% date 2022 9 16 %}}
更新 Qt 6.2.4 和 5.15.6，附带更新的 CVE-2022-37434 的补丁。Qt 6.2 系列重新构建，附带 QtWebEngine 6.3.2。  
升级到 Xcode 14，重新构建所有的 Qt 6.2 以上的 macOS 主机 / 交叉构建。

## {{% date 2022 9 12 %}}
更新 Qt 6.2.4 / 6.3.2 WebAssembly 包。现在启用了预编译头文件支持。  
更新 Qt 6.2.4 / 6.3.2 LLVM-MinGW 包。现在启用了 WMF 支持。  
更新 Qt 6.4.0-beta4。所有原来在 6.3 上的配置全部可用。使用 RockyLinux 9 进行 Qt 6.4.0 的 Linux 交叉构建主机。WebAssembly 和 LLVM-MinGW 包都使用了今天更新的配置进行构建。

## {{% date 2022 9 11 %}}
更新 Qt 6.3.2，使用 OpenSSL 3.0.5。  
更新 Qt 6.2.4，附带 CVE-2022-37434 的补丁。  
更新 Qt 5.15.6，附带 OpenSSL 1.1.1q。所有的已有补丁全部都在。添加了 CVE-2022-27404-27405-27406 和 CVE-2022-37434 的补丁。  
更新 Qt 5.12.12 macOS 主机版安卓构建。上一版误使用了 CommandLineTools 当作主机构建工具链，而不是 Xcode。

## {{% date 2022 8 23 %}}
更新 Qt 5.12.12， 使用 OpenSSL 1.1.1q。  
更新 Qt 6.2.4，附带 Qt 官方提供的 CVE-2022-27404-27405-27406 的补丁和 OpenSSL 3.0.5。  
更新 Qt 6.3.1 WebAssembly 构建，使用 emsdk 3.1.6。

Qt 5.15.5 没有更新，原因是 Qt 官方提供的 CVE-2022-27404-27405-27406 的补丁与 Qt 5.15.5 的代码基准冲突。  
我会等 5.15.6，并且如果这个补丁与 5.15.6 还是冲突的话，我将发布不带这个补丁的版本。

Qt 6.3.1 不会更新。等 6.3.2 发布。

## {{% date 2022 6 29 %}}
更新 Qt 5.15.5，附带 OpenSSL 1.1.1p 和 QtWebEngine 5.15.10。  
~~macOS 11 主机目前出现故障，构建无法更新。可能是 VirtualBox 的问题。目前正在调查。~~ VirtualBox 的更新解决了这个问题。

## {{% date 2022 6 26 %}}
删除 GitHub 链接，在中国大陆并不稳定。  
更新 Qt 5.12.12，使用 OpenSSL 1.1.1p。  
更新 Qt 6.2.4 / 6.3.1，使用 OpenSSL 3.0.4。

Qt 5.15.5 暂时没有更新。之前构建的版本没有安全补丁。

## {{% date 2022 4 13 %}}
上传 Qt 6.3.0 版本。  
上传 Qt 5.15 / Qt 6.2，带 CVE 补丁。

祝我生日快乐！

## {{% date 2022 3 25 %}}
上传 Qt 6.2.4 版本。  
更新 Qt 5.12 / 5.15 版本，使用 OpenSSL 1.1.1n / 3.0.2。

祝基神奄（Iroi Imagay）生日快乐！

## {{% date 2022 3 11 %}}
上传 Qt 5.12.12 / 5.15.3-5 VS2017+ 版本。

## {{% date 2022 3 9 %}}
上传 5.12.12 macOS （额外版本） / 安卓版本，包含 CVE-2022-25255 补丁。  
上传 Qt 5.15.3，附带 QtWebEngine 5.15.8 和 QtScript 5.15.8，包含 CVE-2022-25255 和 CVE-2022-25643 补丁。  
（VS 版本现在还没做完。在制作过程中 VS 更新了，需要重新构建）

（{{% date 2023 1 14 %}}补充修改）修改免责声明，后续代码会包含官方发布的 CVE 补丁。  
Qt 5.12.12 的本地代码中已经包含 CVE 补丁，更新的构建会一直包含 CVE 补丁。  
Qt 5.15.3 的本地代码中已经包含 CVE 补丁。并且补丁会在每次 Qt 版本更新过程中都会进行应用。更新的构建会一直包含 CVE 补丁。  
Qt 6.2.4 将会在最近的开源发布中包含 CVE 补丁。我会等 Qt 6.2.4 的官方发布，而不应用补丁。

## {{% date 2022 2 9 %}}
上传 6.2.3 所有版本。  
更新 VS2017 / VS2019 / VS2022 到各自的最新版。  
上传 VS2022 构建的 Qt 6.2.3。

## {{% date 2022 1 7 %}}
上传 Qt 5.15.2，附带 QtWebEngine 5.15.8 和 QtScript 5.15.8。  
上传 VS2022 构建的 Qt 5.15.2。

## {{% date 2021 12 29 %}}
上传 5.12.12 安卓 / 5.12.12 Windows / 5.15.2 安卓 / 6.2.2 安卓版，使用OpenSSL 1.1.1m。  
Windows 主机版升级了 QQtPatcher 到 0.8.1，支持更多 5.12 特有的硬编码路径补丁。

## {{% date 2021 12 7 %}}
上传 6.2.2 macOS 和 Windows 版本。附带 QtPdf。  
从 Qt 6 开始 QtPdf 并不自动随着 QtWebEngine 进行构建，需要手动启用。

上传 6.2.2 macOS arm64 版本。

## {{% date 2021 12 5 %}}
上传 Qt 5.15.2 附带 QtWebEngine 5.15.7 和 QtScript 5.15.7。  
删除 5.15.2 Windows arm64 版本，原因是官方并未支持。  
由于 Xcode 13 下的编译错误，macOS 版本的 Qt 5.15 和 5.12 交叉构建版本将会保持在 macOS 11 和 Xcode 12.5.1。

上传 Qt 6.2.2 系列版本，包括 MinGW 版本。  
更新 MinGW-w64 v9 附带 GCC 11.2.0。这个版本也是 Qt 官方现在在用的。  
为了构建 Qt 6.2.2 升级了安卓 SDK。

删除所有 Qt 6.1.3 的版本。相同配置的 6.2 系列已经全部可用了。

## {{% date 2021 12 4 %}}
上传 Qt 5.12.12。  
删除 5.12.10 Windows arm64 版本，原因是这个版本从大约一年以前就开始编译失败了。

由于 Qt 5.12 系列已经结束生命周期，并且 macOS 和 WebAssembly 版本不使用 OpenSSL，这次构建是这些平台的最后一次构建。  
其他使用 OpenSSL 的构建将会持续构建到 OpenSSL 1.1.1 系列结束生命周期，也就是 {{% date 2023 9 11 %}}。

## {{% date 2021 10 19 %}}
上传 Qt 6.2.0，使用 [mstorsjo 的基于 LLVM 的 MinGW-w64 工具链](https://github.com/mstorsjo/llvm-mingw)。  
目前只实现了 x86_64 的构建，包含 UCRT 和 msvcrt 两个版本。

这个构建使用了更新的 v9 版本的 MinGW-w64，以前的基于 GCC 8.1.0 的版本还在用 v6。  
如果想尝试一些新事物的话，我推荐使用这个版本。

## {{% date 2021 10 3 %}}
上传 Qt 6.2.0。

## {{% date 2021 9 29 %}}
上传 Qt 6.2.0-rc2。

## {{% date 2021 9 11 %}}
上传 Qt 5.15.2 附带 QtWebEngine 5.15.6 和 QtScript 5.15.6。  
上传 Qt 5.15.2 VS2017+ 版本，更新 VS 版本。

## {{% date 2021 9 4 %}}
上传 Qt 6.1.3。  
更新 OpenSSL 1.1.1l。  
重新构建 5.15.2 和 5.12.11 安卓版，使用 OpenSSL 1.1.1l。  
重新构建 5.12.11 Windows 版，使用 OpenSSL 1.1.1l。（MinGW 64位版本除外，构建失败了）

## {{% date 2021 7 2 %}}
上传 Qt 6.1.2。

## {{% date 2021 6 25 %}}
再次将包上传到 OSDN 因为 OSDN 有更好的在中国大陆的下载体验。

## {{% date 2021 6 19 %}}
上传 Qt 5.15.2 附带 QtWebEngine 5.15.5 和 QtScript 5.15.5。  
更新 Qt 5.12.11 附带 QtWebEngine。为了 QtWebEngine 降级 macOS 至 10.15.7，之后的 Qt 5.12 系列全部使用 macOS 10.15 构建。

## {{% date 2021 6 9 %}}
上传 Qt 6.1.1，包括之前没有构建通过的安卓版本。

## {{% date 2021 5 28 %}}
上传 Qt 5.12.11 （Windows ARM64 版本没有上传，因为编译失败了）  
用于编译 Linux 版本的发行版就地重装为 RockyLinux，除了发行版本身之外所有配置和环境均保留

## {{% date 2021 5 13 %}}
上传 Qt 5.15.2 附带 QtWebEngine 5.15.4 和 QtScript 5.15.4。  
重新构建 5.15.2 安卓版本，使用 OpenSSL 1.1.1k。

## {{% date 2021 5 11 %}}
上传 6.1.0 （桌面端） **安卓版构建失败了**  
Qt 6.1 系列直接附带所有 addon。我不用每次手工下载 addon 了。

## {{% date 2021 4 9 %}}
上传包含 addon 的 6.0.3。  
下载站使用 [Hugo](https://gohugo.io) 重新生成，使用 [techdoc](https://thingsym.github.io/hugo-theme-techdoc/) 主题。（[amWiki](http://amwiki.org/doc/) 是基于 GitHub Atom 的，而且已经好久没更新了）

## {{% date 2021 3 15 %}}
上传包含 addon 的 6.0.2。（之前的版本没有 addon）  
重新构建 5.15.2 安卓版本，使用 NDK r21e。  
重新构建 5.12.0 VS2019 版本，使用更新的 VS2019 和更新的 OpenSSL。

我今后将会提供包含所有 addon 的 Qt6。之前的动态/共享构建为 `Lite` 版本。之后将不会有 `Lite` 版本的动态/共享构建。

## {{% date 2021 3 9 %}}
上传 VS2019 和 macOS 11 的 Qt 5.15.2 附带 QtWebEngine 5.15.3 版本。  
Windows SDK 更新到最新版，为 10.0.19041。  
上传 5.12.10 安卓版本，使用 NDK r21e。

## {{% date 2021 3 4 %}}
上传 6.0.2 构建。  
VS2019 更新到最新版本，为 16.9.0。  
更新 macOS 为 11.2.2。  
**由于编译失败，安卓版本未使用链接的 OpenSSL 支持。**

## {{% date 2021 2 21 %}}
上传 6.0.1 Windows 主机的安卓版构建。  
**由于编译失败，安卓版本未使用链接的 OpenSSL 支持。**

## {{% date 2021 2 6 %}}
上传 6.0.1 版本，添加 MinGW 版本（Windows 主机的安卓版构建没有更新）  
VS2019 更新到最新版本，为 16.8.4。  
更新 macOS 为 11.1。  
**由于编译失败，安卓版本未使用链接的 OpenSSL 支持。**

## {{% date 2021 1 3 %}}
上传 6.0.0 Linux 主机的安卓版构建。  
**由于编译失败，安卓版本未使用链接的 OpenSSL 支持。**

## {{% date 2021 1 2 %}}
上传 6.0.0 macOS 主机的安卓版构建。  
重新构建 6.0.0 Windows 和 macOS 构建，使用 strip 的二进制。  
注：安卓 API Level 在 Qt 6.0.0 开始切换到 android-24。  
**由于编译失败，安卓版本未使用链接的 OpenSSL 支持。**

## {{% date 2020 12 20 %}}
上传 6.0.0 Windows 和 macOS 构建。

## {{% date 2020 12 17 %}}
上传 5.15.2 构建。（所有构建都没有 QtWebEngine，因为编译失败了）  
macOS 更新到 11.0.1。  
VS2017/2019 更新到各自的最新版本，分别是 15.9.30 / 16.8.3。

## {{% date 2020 11 11 %}}
上传 5.12.10 构建。  
macOS 更新到 10.15.7，Xcode 升级到 12.0。  
VS2019 升级到最新版本，为 16.7.7。

**注：** 此次更新引入了一些为了适配 Qt6 做出的修改，此次更新的压缩文件解压后的文件夹名将不带有构建日期。
如果使用脚本操作本库的童鞋，请修改脚本。

## {{% date 2020 9 12 %}}
上传 5.15.1 构建。
macOS 更新到 10.15.6 （19G2021）。
VS2017/2019 更新到各自的最新版本，分别是 15.9.27 / 16.7.3。

## {{% date 2020 7 7 %}}
~~同时上传所有的成果到 GitHub Release，作为 SourceForge 的镜像。~~ （已弃用）

## {{% date 2020 6 19 %}}
更新安卓 NDK 到 r21d。  
使用新版 NDK 重新构建所有安卓包。

## {{% date 2020 6 18 %}}
上传 Qt 5.12.9 构建。

## {{% date 2020 6 4 %}}
上传 Qt 5.15.0 macOS 版本 （Qt 5.12.8 macOS 版本 WebEngine 编译不过，要等 5.12.9）  
Qt 5.15.0 Android 版本 macOS host 重传

## {{% date 2020 6 3 %}}
从 Qt 5.15.0 和 Qt 5.12.9 开始，Qt WebEngine 将会支持 proprietary codecs。  
上传 5.15.0 系列。（ **所有包括交叉构建在内的 macOS 版本均没有上传。构建环境正在进行修复** ）  
Qt 5.15.0 系列上使用更新的 MinGW-w64，附带 GCC 8.1.0，并切换 MinGW-w64 w/ GCC 8.1.0 的构建环境为 Win10。  
上传 Qt 5.9.9 VS2017 版，使用更新的 VS2017 版本  
上传 Qt 5.12.8 WebAssembly 版，更新 emsdk  
上传 Qt 5.12.8 安卓版，更新 NDK r21b （包含 macOS 主机的交叉构建）。  
删除 5.14 系列，macOS 版本除外（macOS 版本将会在 Qt 5.15 构建完成并上传后删除）

由于 Qt 5.9 系列已经结束生命周期，不会再有 Qt 5.9 的构建了。  
也就是说这次的构建是这些包的最后一次构建了。  
Qt 5.9 系列的构建脚本和环境都爆破了。

## {{% date 2020 5 18 %}}
上传 5.15.0-rc2 系列。（ **所有包括交叉构建在内的 macOS 版本均没有上传。构建环境有问题了** ）  
升级 Win10 到 19041 （2004）

## {{% date 2020 4 25 %}}
上传 5.15.0-beta4 系列。（ **所有包括交叉构建在内的 macOS 版本均没有上传。构建环境有问题了** ）

## {{% date 2020 4 12 %}}
上传 5.15.0-beta3 系列。（ **所有包括交叉构建在内的 macOS 版本均没有上传。构建环境有问题了** ）

## {{% date 2020 4 11 %}}
上传 5.12.8 系列。（ **所有包括交叉构建在内的 macOS 版本均没有上传。构建环境有问题了** ）

## {{% date 2020 4 3 %}}
上传 5.14.2 系列。（macOS 版本没有提供，由于 QtWebEngine 编译出错）

## {{% date 2020 3 26 %}}
上传 5.15.0-beta2 系列。（静态 `Full` 版本编译失败了）  
~~在 Coding.net 上建立网站镜像，以更快浏览网页。~~ （不好使了）

## {{% date 2020 3 6 %}}
上传 5.12.7 使用 NDK r21 的安卓版本。
上传 5.15.0-beta1 系列版本。（VS2017 和 VS2019 动态构建还没有提供，QtWebEngine编译出错了）

## {{% date 2020 2 6 %}}
上传 Windows on ARM64 的构建。（目前只支持使用 VS2017 构建 5.12 及更新版本）

## {{% date 2020 2 5 %}}
上传 Qt 5.12.7 系列。（本来 Qt 5.12.7 在 {{% date 2020 1 31 %}}就发布了，但是我没注意到。。。）  

注：QQtPatcher 在构建完成后进行过一波更新（到 0.7.0）。  
多数修改影响 Windows 构建，所以我只重新压缩了 Windows 的包。  
其余的包没有重新压缩，保持原样。

## {{% date 2020 2 3 %}}
添加新的使用 MinGW 构建 Qt 5.12 系列的静态 `Full` 版本包的配置。  
上传 Qt 5.12.6 的 MinGW 静态 `Full` 构建。

## {{% date 2020 2 2 %}}
Qt5.12.6 的 VS2017 和 VS2019 版本重新构建，使用新版 VS。  
解决 5.12.6 的静态 `Full` 版本没有附带 OpenSSL 库的问题。

## {{% date 2020 2 1 %}}
Linux 主机全面切换到 CentOS 8。影响 Android 和 WebAssembly 构建。  
现在只有 5.14 系列成功的构建及上传了。  
CentOS 7 和 Ubuntu 16.04 的环境都爆破了。

更新 Qt 5.14.1 系列。  
使用 CentOS 8 重新构建所有 Linux 主机的 Android 和 WebAssembly 版本。  
由于 OpenSSL 包里没有主机工具，多数 OpenSSL 包没有重新构建。

## {{% date 2020 1 16 %}}
由于脚本 bug，Qt 5.6 的静态 `Full` 构建的包缺少了 OpenSSL 库。目前通过手工重新压缩补回。  
包并没有重新构建。  
（Qt 5.12 系列将于 OpenSSL 1.1 系列或者 Qt 5.12 系列更新后进行修复）

## {{% date 2020 1 5 %}}
使用 OpenSSL 1.0.2 系列的包重新构建，使用 OpenSSL 1.0.2u。  
包括所有的 Qt 4 的包和非 macOS 的 Qt 5.6/5.9 包。

由于 OpenSSL 1.0.2 已经结束生命周期，不会再有 Qt 4 和 Qt 5.6 的构建了。  
也就是说这次的构建是这些包的最后一次构建了。  
Qt 4 和 5.6 系列的构建脚本和环境都爆破了。

## {{% date 2019 12 26 %}}
Windows 8.1 的构建环境搞定了，正好删除 Windows Server 2008 R2 的构建环境。  
更新所有在 Windows 8.1 上构建的包。  
因 Windows SDK 版本原因编译失败的 QtSpeech 模块和 QtConnectivity 模块得以重新加入。

## {{% date 2019 12 22 %}}
更新 Qt 5.9.9 和 5.14.0 的包。  
（由于 Configure 过程中发生错误，Qt 5.14.0 的安卓版本暂缺）

## {{% date 2019 12 5 %}}
增加对 macOS 构建的支持，目前支持 Qt 4.8.7 / 5.6.3 / 5.9.8 / 5.12.6 / 5.13.2

Qt 4.8.7 / 5.6.3 使用 OS X 10.10 构建  
Qt 5.9.8 / 5.12.6 使用 macOS 10.14 构建  
Qt 5.13.2 使用 macOS 10.15 构建

## {{% date 2019 12 2 %}}
上传了我从出差归来之后构建的所有包。  
现在上传的 Qt 5.12 以后的版本附带 OpenSSL 1.1 系列的动态库。此前因疏忽而没有在构建时附带。

## {{% date 2019 11 22 %}}
在我返回中国之后预计的更新。。。  
Qt 5.12 系列 => 5.12.6  
Qt 5.13 系列 => 5.13.2 -> 准备移动到 Qt 5.14 系列  
OpenSSL 1.0.2 系列 => OpenSSL 1.0.2t （影响 Qt 4.8/5.6/5.9 系列）  
OpenSSL 1.1.1 系列 => OpenSSL 1.1.1d （影响 Qt 5.12/5.13 系列）  
VS2017 => 15.9.17  
VS2019 => 16.3.10  
Android NDK => r20b

操作系统升级。。。。  
Win10 => 10.0.18363  
CentOS 7 => 7.7.1908 （应该构建 CentOS 8 的环境了吧？现在 WebAssembly 的包使用 Ubuntu 16.04 LTS 进行构建。如果我们移动到 CentOS 8 它将使用更新的软件）  
macOS 10.14 => 10.15

OpenSSL 1.0.2 结束生命周期后，Qt 4.8/5.6 的构建将会停止（时间是 {{% date 2019 12 31 %}}）  
Qt 5.9 系列结束生命周期后，Qt 5.9 的构建将会停止（时间是 {{% date 2020 5 31 %}}）  
Windows 7 结束生命周期后，将不会再有构建在 Windows 7 (Server 2008 R2) 上运行（时间是 {{% date 2020 1 11 %}}）。现有的 Windows 7 上的构建会迁移到 Windows 8.1 (Server 2012 R2)

## {{% date 2019 8 26 %}}
发现了一个打包的 bug。影响 5.12 以后的所有版本。  
5.12.5 版本上会修复这个问题。

## {{% date 2019 8 3 %}}
使用 [amWiki](http://amwiki.org/doc/) 重新构建网站。  
因为 [amWiki](http://amwiki.org/doc/) 有内置的目录，所以没有必要再手写一遍下载内容列表了。

## {{% date 2019 7 13 %}}
因为之前发现的 QQtPatcher 的 bug， __所有__ 的包都重做了。  
VS2017 更新至 15.9.14。  
VS2019 更新至 16.1.6。

## {{% date 2019 7 9 %}}
WebAssembly 版本更新至 Qt 5.12.4 和 5.13.0。

## {{% date 2019 7 8 %}}
Android 版本更新至 Qt 5.12.4 和 5.13.0。 __因为修改构建脚本的问题文件名为 NDK r20，实际上是使用 NDK r19c 构建的，r20 构建不过__  
Android 版本全部重新构建，使用 OpenSSL 1.0.2s 和 OpenSSL 1.1.1c。  
重新整理了一下主页，防止安卓和 Wasm 平台版本找不到

## {{% date 2019 7 6 %}}
Windows 版本 Qt5.13.0 上传。 __SSL 后端为 SChannel！！！！不是 OpenSSL 了！！！！__

## {{% date 2019 7 5 %}}
Windows 版本重新构建，使用 OpenSSL 1.0.2s 和 OpenSSL 1.1.1c。  
Windows 版本更新至 Qt 5.12.4。

## {{% date 2019 5 26 %}}
使用更新的 VS 版本重新构建 VS2017 和 VS2019 的包。

## {{% date 2019 5 19 %}}
更新了配置，重新构建了 Linux 主机的安卓版本的包。  
上传 Linux 主机的 WebAssembly 版本的包。  
SF.net 恢复，文件重新上传到 SF.net。

（为什么我不能在 OSDN 上使用 SFTP 去管理文件？）

## {{% date 2019 5 15 %}}
更新了配置，重新构建了 Windows 版本的包。  
由于中国大连的中国电信暂时无法访问 SF.net，文件在 OSDN 上重新传了一份。

## {{% date 2019 4 22 %}}
上传 5.9.8 和 5.12.3 的 VS2015 版本的包。

## {{% date 2019 4 20 %}}
完成 5.9.8 和 5.12.3 系列版本。

## {{% date 2019 4 19 %}}
删除旧包。  
上传自 2019 年 3 月以来的所有新构建的包。

## 2017 年以前（黑历史，仅有嘤文）

{{% expand title="展开" %}}

是的，我想写一些东西，但是不知道怎么写。。。

### {{% date 2016 7 23 %}}
Upload 5.6.1-1/5.7.0 VS2015 static builds again due to link issue.

From now on, I will not link MySQL/PostgreSQL/ODBC(unix-like only)/OpenSSL in the static packages.  
The configure scripts may be like this:
```
configure xxxxx -static -openssl -qt-sql-sqlite -no-sql-mysql -no-sql-psql -no-sql-odbc(for unix-like)/-qt-sql-odbc(for windows)
```

I'm anti of static builds, see the notes for details.

### {{% date 2016 7 17 %}}
Upload all files to Mega.nz for users who are not in China.

### {{% date 2016 7 16 %}}
Upload 4.8.7 macOS shared packages.  
Upload 4.8.7 Linux shared packages.

### {{% date 2016 7 15 %}}
From now on, I will distribute the config.status(for Unix-like system) or configure.cache(for Windows) in the compressed packages.  
config.status contains all my commands when calling configure, while configure.cache only contains the parameters passed to configure.exe.  
Upload 4.8.7 VS2015 Shared packages. (And are the first and second packages which have configure.cache)  
Update note to suit Qt4.  
Update note about QtBinPatcher.  
Upload 4.8.7 VS2010 Shared packages.  
Update note about old-version Qt.

### {{% date 2016 7 4 %}}
Upload 5.6.1-1 VS2015 Static packages.  
Upload 5.6.1-1 Android(Windows x86_64 host) Shared packages.  
Upload 5.6.1-1 VS2010 Shared packages __just for the unreconstructed people using Windows XP__.  
Update note.

### {{% date 2016 7 3 %}}
Upload 5.6.1-1 VS2015 Shared packages.  
Upload 5.6.1-1 MinGW Shared packages.  
Upload 5.6.1-1 Linux packages.  
Upload 5.6.1-1 macOS packages.  
Removed 5.6.1 packages.  
Upload 5.6.1-1 Android(Linux x86_64 host) Shared packages.  
Upload 5.6.1-1 Android(macOS x86_64 host) Shared packages.

### {{% date 2016 6 29 %}}
Upload 5.7.0 Android(Windows x86_64 host) Shared packages.

### {{% date 2016 6 28 %}}
Upload 5.7.0 Android(Linux x86_64 host) Shared packages.  
Upload 5.7.0 Android(macOS x86_64 host) Shared packages.

### {{% date 2016 6 27 %}}
Update Disclaimer.

### {{% date 2016 6 22 %}}
Upload 5.7.0 VS2015 Static packages.  
Upload 5.7.0 MinGW Shared packages.  
VS2015-clang packages failed to build, thus cannot upload.

### {{% date 2016 6 19 %}}
Upload 5.7.0 VS2015 Shared packages.  
Upload 5.7.0 macOS packages.

### {{% date 2016 6 18 %}}
Upload 5.7.0 Linux packages.  
Removed 5.6.0 packages.  
Upload 5.6.1 VS2015 Static packages.

### {{% date 2016 6 13 %}}
Initial commit, includes builds of Qt 5.6.0, part of 5.6.1 and 5.7.0-RC.

{{% /expand %}}
