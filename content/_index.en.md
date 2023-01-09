---
title: "Fsu0413\'s Original Qt builds"
draft: false
---

# Fsu0413's Original Qt builds

## Chinese / Multilingual Support

This website was English only since when it was initially built, although the maintainer of this website (me, Fsu0413) is a Chinese native speaker from the PRC.  
Currently I am gradually adding Simplified Chinese support on this website.

Recently this website has gained multilingual support thanks to the built-in multilingual support of [Hugo](https://gohugo.io/) and the recently switched [Relearn](https://mcshelby.github.io/hugo-theme-relearn/) theme.  
Current Chinese support is in the stage of writing texts. There is a bunch of things which are not finished.  
But the main contents are rewritten using Chinese, which shouldn't bother us for downloading binaries.

If there are any constructive advices, feel free to create issue on Github.

## Disclaimer

These binaries built by Fsu0413 are __TOTALLY UNTESTED__. Use at your own risk.  
The code used is downloaded from [here](http://download.qt.io), I made no changes to the source/generated files.  
__THESE PACKAGE ARE PROVIDED "As is", I have no responsibility that you mess up your things with this binaries.__  
Thanks for The Qt Company Ltd. and the programmers of Qt for their fantastic work!!

## Notes for this repo

[Here]({{% relref "miscellaneous/notes for this repo" %}})

## Current build status

[Here]({{% relref "miscellaneous/current build status" %}})

## Downloads

Please refer to the content lists in the left area.

## Current failures

[Here]({{% relref "miscellaneous/current failures" %}})

## Update History

### 2023.1.8
Update Qt 6.4.2 / Qt 5.15.8 packages.  
Update Qt 6.2.4 packages built with OpenSSL 3.0.7 with the minor fix.

Qt 6 Linux hosted cross built packages has a problem where the host tool was not properly deployed.  
This time the package is rebuilt with fix.  
Only Qt 6.2.4 Linux hosted WebAssembly package is rebuilt without other modification.

### 2022.11.20
Update all cross built package with CMake toolchain refactored. Currently it can automatically use the bundled host tool using bundled 'qt-cmake' script.  
The updated packages are following:  
Qt 6.2.4 Android / WebAssembly packages  
Qt 6.4.1 Android / WebAssembly packages

### 2022.11.19
Update Qt 6.4.1 WebAssembly macOS host with Thread feature ON. (I did only modified x86_64 build and... I am using arm64 build for base of cross builds and it's gone)

### 2022.11.18
Update Qt 6.4.1.  
Update Qt 6 WebAssembly with Thread feature ON. (Previous versions are missing this feature)   
Update Qt 6 macOS Universal builds. Future Qt 6 builds of macOS will only provide Universal builds.  
Update Qt 6.2.4 Windows VS builds with updated VS version.

### 2022.11.8
Update Qt 6.2.4 with OpenSSL 3.0.7 (Without QtWebEngine since all builds of QtWebEngine failed). Existing patches are all in.  
Update Qt 5.15.7 with OpenSSL 1.1.1s on macOS (Without QtWebEngine).

Qt 6.2.4 cross builds (Linux / macOS host) are packaged with `libexec` folder of host builds where tools like `lrelease` are lying in.

### 2022.11.6
Update Qt 5.15.7 with OpenSSL 1.1.1s (excluding macOS, compile failed in QtWebEngine). Existing patches are all in.   
Update Qt 5.12.12 with OpenSSL 1.1.1s.

### Before Oct. 2022

[Here]({{% relref "miscellaneous/histories" %}})