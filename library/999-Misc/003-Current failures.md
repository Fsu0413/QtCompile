# Build Failures about the original packages

## Qt 6 - development releases

### CMake support of Qt 6

I have started using CMake to build Qt 6.  
CMake related problems occurres frequently during test, but I will not return to use configure and qmake to build Qt 6 anymore.  
CMake is becoming popular among projects. I think we should adopt to it on early stage.

Currently following issue is reported:

[QTBUG-88126](https://bugreports.qt.io/browse/QTBUG-88126) - CMake error when invoking with "-DFEATURE_schannel=ON -DFEATURE_openssl=OFF"

### Cannot build Qt 6.0.0-beta2 with SChannel

[QTBUG-88127](https://bugreports.qt.io/browse/QTBUG-88127) - Cannot build Qt 6.0.0 beta2 with -DFEATURE_schannel=ON

## Qt 5.12 wasm builds can't built with OpenSSL

Both `qsslsocket_opensslpre11.cpp` and `qsslsocket_openssl11.cpp` includes `qlibrary.h` which is not usable in wasm platform.  
Since `-openssl` and `-openssl-linked` both use this file, so we can only use `-no-ssl`.......

I didn't try with Qt 5.15 series.

## QDoc after Qt 5.12 cannot use static linked clang when using MSVC

It uses "libclang_static.lib" but clang don't provide this one.  
I have decided not provide LLVM-based qdoc until I find a way to static link it.

Update 2020.11.3:  
"libclang_static.lib" is packed seprately using script by Qt guys.  
Thanks "lixinwei" on QTCN.org for telling me related info. [Original post](http://www.qtcn.org/bbs/job.php?action=topost&tid=85983&pid=200952) (Sorry, it's in Chinese)
