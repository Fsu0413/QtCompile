---
title: "Current failures"
draft: false
weight: 3
---

## Qt 5.12 WebAssembly builds can't built with OpenSSL

Both `qsslsocket_opensslpre11.cpp` and `qsslsocket_openssl11.cpp` includes `qlibrary.h` which is not usable in WebAssembly platform.  
Since `-openssl` and `-openssl-linked` both use this file, so we can only use `-no-ssl`.......

I didn't try with Qt 5.15 series, but `qsslsocket_openssl.cpp` in Qt 5.15 includes `qlibrary.h` as well...

I didn't try with Qt 6.2 onwards.

Update 2022.11.6:  
I gave up supporting SSL on WebAssembly and will remove this item later.

## QDoc after Qt 5.12 cannot use static linked clang when using MSVC

It uses `libclang_static.lib` but clang don't provide this one.  
I have decided not provide LLVM-based QDoc until I find a way to static link it.

Update 2020.11.3:  
`libclang_static.lib` is packed seprately using script by Qt guys.  
Thanks "lixinwei" on QTCN.org for telling me related info. [Original post](http://www.qtcn.org/bbs/job.php?action=topost&tid=85983&pid=200952) (Sorry, it's in Chinese)

## Command line too long when building Qt 6.2 series for MinGW

See {{% QtBug 96339 %}} - workaround using CMake 3.20.2

## QtOpcUa issues

QtOpcUa is currently not compatible with OpenSSL 3.0 series.  
Temporarily disabling QtOpcUa build until the Qt guys update their open62541 version.  
This change takes place since building and packaging of Qt 6.2.3.

But seems like that open62541 guys doesn't treat this as issue despite the increasing popularity of OpenSSL 3.0 series.  
Version 1.3.3 has released without any fix about OpenSSL 3.0.  
~~I don't know if we can bring QtOpcUa back in Qt 6.4...~~

Update 2022.11.6:  
open62541 hasn't release any version after 1.3.3 so there is no OpenSSL 3.0 support on open62541 of QtOpcUa 6.4.  
There is a merged Pull Request on Github which added OpenSSL 3.0 support. Reference: [Github Pull Request](https://github.com/open62541/open62541/pull/5349).  
I will restart building with QtOpcUa when this change is got integrated in next released version of open62541.

## Various failures building higher version of QtWebEngine on Qt 6.2.4

QtWebEngine 6.3.2 on Qt 6.2.4 fails on macOS when using Xcode 14.1. It was OK using Xcode 14.0.1. Probably because QtWebEngine 6.3.2 is incompatible with macOS Ventura SDK.  
QtWebEngine 6.4.0 on Qt 6.2.4 fails on macOS and Windows. All of them succeeds inside `gn` and outside it. Different failure occurs on Windows and macOS.

I'm tired of investigating them and will distribute Qt 6.2 series without QtWebEngine.  
QtWebEngine has not released as LTS since Qt 6.2.4 and the Qt guys are simply taking QtWebEngine from later version (6.3, etc) for their 6.2 LTS series releases.  
But no one else knows what version Qt guys are using for their Qt 6.2 LTS Releases except for the official packagers, as the QtWebEngine version is always different than the binary files.

## Qt 5.15.7 with QtWebEngine 5.15.11 build fails on macOS 11

Reason is unknown.
