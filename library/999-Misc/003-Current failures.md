# Build Failures about the original packages

## Qt 5.12 wasm builds can't built with OpenSSL

Both `qsslsocket_opensslpre11.cpp` and `qsslsocket_openssl11.cpp` includes `qlibrary.h` which is not usable in wasm platform.  
Since `-openssl` and `-openssl-linked` both use this file, so we can only use `-no-ssl`.......

I didn't try with Qt 5.15 series.

## QDoc after Qt 5.12 cannot use static linked clang when using MSVC

It uses "libclang_static.lib" but clang don't provide this one.  
I have decided not provide LLVM-based qdoc until I find a way to static link it.

## Resolved and abandoned failures

### (_Resolved_) ~~Qt 5.12 with WebEngine can only be built by hand~~

~~Using build scripts will cause failure. Reason is unknown.~~

### (_Resolved in Qt 5.12.5 and 5.13.1_) ~~Android NDK r20 can't be used for building Qt~~

~~`cannot find library -lc++`~~

### (_Abandoned_) Qt 5.9.9 ~~and~~ (_Resolved in Qt 5.12.7_) ~~5.12.6~~ cannot be built using xcode 11

Some parts don't compile.  
Static `lite` version and host tools successfully built, the cross compiled version successfully built.  
5.9 series fails on QtConnectivity~~, while 5.12 series fails on QtWebEngine~~.

I think that ~~5.12 series should be fixed soon, but~~ 5.9 series may not be fixed.  
I ~~will use~~ used xcode 11 for compiling 5.12.7. QtWebEngine has successfully built. ~~Certain parts will be skipped if they don't compile.~~

### (_Resolved in Qt 5.14.1_) ~~Qt 5.14.0 cannot be built for Android with linked OpenSSL~~

~~See [QTBUG-80862](https://bugreports.qt.io/browse/QTBUG-80862)~~  
~~qmake is always using aarch64 compiler for checking the availability of OpenSSL libs and fails if target arch is not aarch64.~~

### (_Resolved_ by adding some options in command line) ~~Default compressed package is often 1.5~2 times larger than manually compressed ones~~

~~Notably in static `full` packages which often reach 150MB+.~~

~~I use more dictionary size and word size in the compress setting dialog.~~
~~Since it will use more memory, I didn't use it in scripts.~~
~~I will try to add the dictionary size and word size option in the compress command line when I have time.~~

### (_Resolved_) ~~QtWebEngine does not compile on 5.15.0 beta versions on Windows platforms~~

It was because of the 260-character limitation on Windows.  
Change the extract path on Windows solves this problem.

### (_Resolved in Qt 5.14.2_) ~~Qt 5.14.1 can't be built using NDK r21~~

~~It is said that Qt 5.14.2 resolved this issue.~~

### (_Reason is that I used NFS on macOS machines_) ~~All Qt Builds are broken on macOS 10.15.4 Update and xcode 11.4~~

~~Reason is unknown for me by now.~~  
~~I am considering reinstall the OS.~~

### (_Replaced by "All Qt Builds are broken on macOS 10.15.4 Update and xcode 11.4"_) ~~macOS version of QtWebEngine 5.14.2 does not compile~~

~~gn compile failed on macOS using xcode 11.4.~~

### (_Resolved in Qt 5.12.9_) ~~Qt WebEngine 5.12.8 cna't be built using xcode 11.4 or later~~

~~See [QTBUG-83318](https://bugreports.qt.io/browse/QTBUG-83318)~~  
~~We have to wait for 5.12.9.~~

### (_Abandoned_) Qt WebEngine 5.15.0-beta4 and later cannot be built using VS2017

Reason is unknown for me by now.  
Temporary disable the build of WebEngine for VS2017 version for now.

Qt does not provide a prebuilt binary for VS2017 anymore. I have skipped the QtWebEngine in VS2017 builds of Qt 5.15.0.

### (_Does not happen recently_) ~~Some of default compressed package is detected as malware by SF.net~~

~~Recompress it by hand solves the problem.~~
