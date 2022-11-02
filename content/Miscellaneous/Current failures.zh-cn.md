---
title: "当前的失败项"
draft: false
weight: 3
---

## 无法在 Qt 5.12 WebAssembly 构建中使用 OpenSSL

`qsslsocket_opensslpre11.cpp` 和 `qsslsocket_openssl11.cpp` 两方均包含了 `qlibrary.h` 头文件，不过该文件在 WebAssembly 平台上无法使用。  
因为 `-openssl` 和 `-openssl-linked` 都使用了这个文件，我们只能使用 `-no-ssl` 了。。。

我没有在 Qt 5.15 系列再次尝试这件，但是在 Qt 5.15 中 `qsslsocket_openssl.cpp` 还是包含了 `qlibrary.h` 头文件。。。

我没有在 Qt 6.2 以及以后再次尝试这件。

## Qt 5.12 以后的 QDoc 使用 MSVC 构建时无法使用静态链接的 clang

它使用 `libclang_static.lib` 但是 clang 构建中没有这个文件。  
我决定在找到使用静态链接的 clang 方法之前，不再提供基于 LLVM 的 QDoc。

2020 年 11 月 3 日更新：  
`libclang_static.lib` 是 Qt 那帮人自己使用脚本打包的。  
非常感谢 QtCN 的 lixinwei 提供相关信息。 [原帖参考](http://www.qtcn.org/bbs/job.php?action=topost&tid=85983&pid=200952)

## 使用 MinGW 构建 Qt 6.2 系列时命令行过长

参考 {{% QtBug 96339 %}} - 暂时使用 CMake 3.20.2 绕过这个问题

## QtOpcUa 的问题

目前 QtOpcUa 与 OpenSSL 3.0 系列存在兼容性问题。  
在 Qt 那帮人更新他们自己的 open62541 版本之前，暂时禁用 QtOpcUa 的构建。  
这个修改将于 Qt 6.2.3 的构建和打包时落实。

看起来 open62541 那帮人并没有把这件事当成问题，即使 OpenSSL 3.0 系列现在已经逐渐流行。  
1.3.3 版本发布但是还是没有关于 OpenSSL 3.0 的修正。  
我不清楚是否我们可以把 QtOpcUa 带回到 Qt 6.4 了。。。。