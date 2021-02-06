# Current Status

## QQtPatcher Support Status

This is a list where QQtPatcher is supported and tested on.  
Other version may work, but also may silently fail.

A valid qbp.json is needed for patching Qt 4 Series since `qmake -query` don't output the makespec.

Qt 5.14 is relocatable as announced in [New Features in Qt 5.14](https://wiki.qt.io/New_Features_in_Qt_5.14), so Qt after 5.14 won't need QQtPatcher anymore.  
I delivered QQtPatcher for earlier version of 5.14 (because of the fact that I forgot to modify QQtPatcher related code in build scripts).  
This tool won't be thoroughly tested on 5.13.  
I announced that QQtPatcher will not support Qt 5 after 5.14.

| Qt Version | -platform | -xplatform | Notes | Tested |
|-|
|4.8.7|win32-msvc2010|-|Needs qbp.json|√|
|4.8.7|win32-g++|-|Needs qbp.json|√|
|4.8.7|macx-llvm|-|Needs qbp.json|√|
|5.6.3|win32-msvc2010|-||√|
|5.6.3|win32-msvc2015|-||√|
|5.6.3|win32-g++|-||√|
|5.6.3|win32-g++|android-g++||√|
|5.6.3|macx-clang|-||√|
|5.6.3|linux-g++|-||√|
|5.6.3|linux-g++|android-g++||√|
|5.9.9|win32-msvc|-|VS2015, VS2017|√|
|5.9.9|win32-g++|-||√|
|5.9.9|win32-g++|android-g++||√|
|5.9.9|macx-clang|-||√|
|5.9.9|linux-g++|-||√|
|5.9.9|linux-g++|android-g++||√|
|5.12.10|win32-msvc|-|VS2015, VS2017, VS2019|√|
|5.12.10|win32-arm64-msvc2017|-|||
|5.12.10|win32-g++|-||√|
|5.12.10|win32-g++|android-clang||√|
|5.12.10|macx-clang|-|||
|5.12.10|macx-clang|wasm-emscripten|||
|5.12.10|linux-g++|-||√|
|5.12.10|linux-g++|android-clang||√|
|5.12.10|linux-g++|wasm-emscripten||√|

Build Hosts:

| Qt Version | -platform | Host | Compiler Version | QQtPatcher version |
|-|
|5.12.10|win32-msvc|Windows 8.1 Update|VS2015 Update 3|0.7.2|
|5.12.10|win32-msvc|Windows 10 10.0.19041|VS2017 15.9.27|0.7.2|
|5.12.10|macx-clang|macOS 10.15|AppleClang 12.0|0.7.2|
|5.12.10|linux-g++|CentOS 8.2|GCC 8.3.1|0.7.2|

## OpenSSL Status

My Qt builds is with linked OpenSSL support for most platforms.  
Here is a list of OpenSSL builds of mine.

Note:   
OpenSSL 1.1.1 series on Windows is only for Qt 5.12 series. For Qt 5.13 onwards we are using SChannel.  
MinGW builds is "-shared-and-static" so no need to build a seprate static version.

| OpenSSL Version | Platform | Build Host | Compiler Version | Architecture | Variant |
|-|
|1.1.1i|Windows|Windows 8.1 Update|VS2015 Update 3|x86||
|1.1.1i|Windows|Windows 8.1 Update|VS2015 Update 3|x86|-static|
|1.1.1i|Windows|Windows 8.1 Update|VS2015 Update 3|x86_64||
|1.1.1i|Windows|Windows 8.1 Update|MinGW 7.3.0|x86||
|1.1.1i|Windows|Windows 8.1 Update|MinGW 7.3.0|x86_64||
|1.1.1i|Windows|Windows 10 10.0.19041|VS2017 15.9.27|x86||
|1.1.1i|Windows|Windows 10 10.0.19041|VS2017 15.9.27|x86|-static|
|1.1.1i|Windows|Windows 10 10.0.19041|VS2017 15.9.27|x86_64||
|1.1.1i|Windows|Windows 10 10.0.19041|VS2017 15.9.27|x86_64|-static|
|1.1.1i|Windows|Windows 10 10.0.19041|VS2017 15.9.27|arm64||
|1.1.1i|Windows|Windows 10 10.0.19041|VS2019 16.7.7|x86||
|1.1.1i|Windows|Windows 10 10.0.19041|VS2019 16.7.7|x86_64||
|1.1.1i|Android|CentOS 8.3|ndk r21e|arm|android-21, -static|
|1.1.1i|Android|CentOS 8.3|ndk r21e|arm64|android-21, -static|
|1.1.1i|Android|CentOS 8.3|ndk r21e|x86|android-21, -static|
|1.1.1i|Android|CentOS 8.3|ndk r21e|x86_64|android-21, -static|
|1.1.1i|Android|CentOS 8.3|ndk r21e|ALL|android-21, -static|
|1.1.1i|Android|CentOS 8.3|ndk r21e|arm|android-24, -static|
|1.1.1i|Android|CentOS 8.3|ndk r21e|arm64|android-24, -static|
|1.1.1i|Android|CentOS 8.3|ndk r21e|x86|android-24, -static|
|1.1.1i|Android|CentOS 8.3|ndk r21e|x86_64|android-24, -static|

## Qt 5.12.10 Series (Previous LTS release)

| Platform | Build Host | Compiler Version | Architecture | Variant | mkspecs | Uploaded | Configuration |
|-|
|Windows|Windows 8.1 Update|VS2015 Update 3|x86||win32-msvc|√|√|
|↑|↑|↑|x86|-static|win32-msvc|√|√|
|↑|↑|↑|x86_64||win32-msvc|√|√|
|↑|Windows 10 10.0.19041|VS2017 15.9.27|x86||win32-msvc|√|√|
|↑|↑|↑|x86|-static(Lite)|win32-msvc|√|√|
|↑|↑|↑|x86|-static(Full)|win32-msvc|√|√|
|↑|↑|↑|x86_64||win32-msvc|√|√|
|↑|↑|↑|x86_64|-static(Full)|win32-msvc|√|√|
|↑|↑|↑|arm64||win32-arm64-msvc2017|√|√|
|↑|↑|VS2019 16.7.7|x86||win32-msvc|√|√|
|↑|↑|↑|x86_64||win32-msvc|√|√|
|↑|Windows 8.1 Update|MinGW 7.3.0|x86||win32-g++|√|√|
|↑|↑|↑|x86|-static(Full)|win32-g++|√|√|
|↑|↑|↑|x86_64||win32-g++|√|√|
|↑|↑|↑|x86_64|-static(Full)|win32-g++|√|√|
|Linux|CentOS 8.2|GCC 8.3.1|x86_64|-static(Lite)|linux-g++|Won't upload, only used in QQtPatcher|√|
|macOS|macOS 10.15|AppleClang 11.0|x86_64|-framework|macx-clang|√|√|
|↑|↑|↑|x86_64|-no-framework|macx-clang|√|√|
|↑|↑|↑|x86_64|-static(Lite)|macx-clang|Won't upload, only used in QQtPatcher|√|
|Android|Windows 10 10.0.19041|ndk r21d|arm|android-21|android-clang|√|√|
|↑|↑|↑|arm64|android-21|android-clang|√|√|
|↑|↑|↑|x86|android-21|android-clang|√|√|
|↑|CentOS 8.2|↑|arm|android-21|android-clang|√|√|
|↑|↑|↑|arm64|android-21|android-clang|√|√|
|↑|↑|↑|x86|android-21|android-clang|√|√|
|↑|macOS 10.15|↑|arm|android-21|android-clang|√|√|
|↑|↑|↑|arm64|android-21|android-clang|√|√|
|↑|↑|↑|x86|android-21|android-clang|√|√|
|WebAssembly|CentOS 8.2|emscripten-1.38.16|-||wasm-emscripten|√|√|
|↑|macOS 10.15|↑|-||wasm-emscripten|√|√|

## Qt 5.15.2 Series (Current LTS release for commerical version only)

| Platform | Build Host | Compiler Version | Architecture | Variant | mkspecs | Uploaded | Configuration |
|-|
|Windows|Windows 8.1 Update|VS2015 Update 3|x86||win32-msvc|√|√|
|↑|↑|↑|x86_64||win32-msvc|√|√|
|↑|Windows 10 10.0.19042|VS2017 15.9.30|x86||win32-msvc|√|√|
|↑|↑|↑|x86_64||win32-msvc|√|√|
|↑|↑|↑|arm64||win32-arm64-msvc2017|√|√|
|↑|↑|VS2019 16.8.3|x86||win32-msvc|√|√|
|↑|↑|↑|x86|-static(Full)|win32-msvc|√|√|
|↑|↑|↑|x86_64||win32-msvc|√|√|
|↑|↑|↑|x86_64|-static(Full)|win32-msvc|√|√|
|↑|↑|MinGW 8.1.0|x86||win32-g++|√|√|
|↑|↑|↑|x86|-static(Full)|win32-g++|√|√|
|↑|↑|↑|x86_64||win32-g++|√|√|
|↑|↑|↑|x86_64|-static(Full)|win32-g++|√|√|
|macOS|macOS 11.0|AppleClang 12.0|x86_64|-framework|macx-clang|√|√|
|↑|↑|↑|x86_64|-no-framework|macx-clang|√|√|
|Android|Windows 10 10.0.19042|ndk r21d|ALL|android-21|android-clang|√|√|
|↑|CentOS 8.3|↑|ALL|android-21|android-clang|√|√|
|↑|macOS 11.0|↑|ALL|android-21|android-clang|√|√|
|WebAssembly|Windows 10 10.0.19042|emscripten-1.39.8|-|-feature-threads|wasm-emscripten|√|√|
|↑|CentOS 8.3|↑|-|-feature-threads|wasm-emscripten|√|√|
|↑|macOS 11.0|↑|-|-feature-threads|wasm-emscripten|√|√|

## Qt 6.0.0 Series

<b>Note: Since Qt dropped support for 32-bit Windows, our Qt 6 builds will drop support for 32-bit Windows either.  
If there is need of static builds for non-LTS release, please contect me directly for commerical customization.</b>

| Platform | Build Host | Compiler Version | Architecture | Variant | mkspecs | Uploaded | Configuration |
|-|
|Windows|Windows 10 10.0.19042|VS2019 16.8.4|x86_64||win32-msvc|√|√|
|↑|↑|↑|x86_64|-static(Full)|win32-msvc||Wait for Qt 6.2|
|↑|↑|VS2019 16.x.x|arm64||win32-arm64-msvc||Wait for Qt 6.2|
|↑|↑|MinGW 8.1.0|x86_64||win32-g++|√|√|
|↑|↑|↑|x86_64|-static(Full)|win32-g++||Wait for Qt 6.2|
|↑|↑|↑|x86_64|-static(Lite)|win32-g++|Won't upload seprately, used in cross-compiled Qt|√|
|Linux|CentOS 8.3|GCC 8.3.1|x86_64|-static(Lite)|linux-g++|Won't upload seprately, used in cross-compiled Qt|√|
|macOS|macOS 11.0|AppleClang 12.0|x86_64|-framework|macx-clang|√|√|
|↑|↑|↑|x86_64|-no-framework|macx-clang|√|√|
|↑|↑|↑|arm64|-framework|macx-clang||Wait for Qt 6.1|
|↑|↑|↑|arm64|-no-framework|macx-clang||Wait for Qt 6.1|
|↑|↑|↑|x86_64|-static(Lite)|macx-clang|Won't upload seprately, used in cross-compiled Qt|√|
|Android|Windows 10 10.0.19042|ndk r21e|arm|android-24|android-clang||Wait for Qt 6.0.1|
|↑|↑|↑|arm64|android-24|android-clang||Wait for Qt 6.0.1|
|↑|↑|↑|x86|android-24|android-clang||Wait for Qt 6.0.1|
|↑|↑|↑|x86_64|android-24|android-clang||Wait for Qt 6.0.1|
|↑|CentOS 8.3|↑|arm|android-24|android-clang|√|√|
|↑|↑|↑|arm64|android-24|android-clang|√|√|
|↑|↑|↑|x86|android-24|android-clang|√|√|
|↑|↑|↑|x86_64|android-24|android-clang|√|√|
|↑|macOS 11.0|↑|arm|android-24|android-clang|√|√|
|↑|↑|↑|arm64|android-24|android-clang|√|√|
|↑|↑|↑|x86|android-24|android-clang|√|√|
|↑|↑|↑|x86_64|android-24|android-clang|√|√|
|WebAssembly|Windows 10 10.0.xxxxx|emscripten-1.39.8|-|-feature-threads|wasm-emscripten||Wait for Qt 6.2|
|↑|CentOS 8.x|↑|-|-feature-threads|wasm-emscripten||Wait for Qt 6.2|
|↑|macOS 10.15|↑|-|-feature-threads|wasm-emscripten||Wait for Qt 6.2|
