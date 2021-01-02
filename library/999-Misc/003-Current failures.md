# Build Failures about the original packages

## Issues about Qt 6

I have started using CMake to build Qt 6.  
CMake related problems occurres frequently during test, but I will not return to use qmake to build Qt 6 anymore.  
CMake is becoming popular among projects. I think we should adopt to it on early stage.

Currently following issue is reported to Qt:

<del>[QTBUG-89515](https://bugreports.qt.io/browse/QTBUG-89515) - static build of Qt 6.0.0 using MinGW failes on 2 tools</del> (Closed, affects static builds on Windows of Qt 6.0.0)  
<del>[QTBUG-89530](https://bugreports.qt.io/browse/QTBUG-89530) - compile error on qsslsocket_schannel.cpp when using MinGW</del> (Closed, affects MinGW builds of Qt 6.0.0)  
<del>[QTBUG-88126](https://bugreports.qt.io/browse/QTBUG-88126) - CMake error when invoking with "-DFEATURE_schannel=ON -DFEATURE_openssl=OFF"</del> (Closed)  
<del>[QTBUG-88127](https://bugreports.qt.io/browse/QTBUG-88127) - Cannot build Qt 6.0.0 beta2 with -DFEATURE_schannel=ON</del> (Closed)

MinGW version and Windows hosted cross build version should wait for 6.0.1.  
Build and package script of other versions are currently under investigation.

Linked OpenSSL support on Android is currently broken, due to following issue.

[QTBUG-89473](https://bugreports.qt.io/browse/QTBUG-89473) - Cannot build Android with -openssl-linked (Closed but fix is on dev branch, not 6.0 branch)

One should wait for 6.1.0 for linked OpenSSL support on Android.

## WebEngine of Qt 5.15.2 does not build on macOS 11 and Windows 10

See [this post](http://www.qtcn.org/bbs/read.php?tid=85733&ds=1#201581) (Sorry, it's in Chinese)  
I will not distribute binaries with WebEngine of Qt version 5.15.2.

## Qt 5.12 wasm builds can't built with OpenSSL

Both `qsslsocket_opensslpre11.cpp` and `qsslsocket_openssl11.cpp` includes `qlibrary.h` which is not usable in wasm platform.  
Since `-openssl` and `-openssl-linked` both use this file, so we can only use `-no-ssl`.......

I didn't try with Qt 5.15 series, but `qsslsocket_openssl.cpp` in Qt 5.15 includes `qlibrary.h` as well...

## QDoc after Qt 5.12 cannot use static linked clang when using MSVC

It uses "libclang_static.lib" but clang don't provide this one.  
I have decided not provide LLVM-based qdoc until I find a way to static link it.

Update 2020.11.3:  
"libclang_static.lib" is packed seprately using script by Qt guys.  
Thanks "lixinwei" on QTCN.org for telling me related info. [Original post](http://www.qtcn.org/bbs/job.php?action=topost&tid=85983&pid=200952) (Sorry, it's in Chinese)
