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
I don't know if we can bring QtOpcUa back in Qt 6.4...
