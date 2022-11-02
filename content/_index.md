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
<font color=red>__THESE PACKAGE ARE PROVIDED "As is", I have no responsibility that you mess up your things with this binaries.__</font>  
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

### 2022.10.4
Update Qt 6.4.0.  
Update Qt 6.2.4 static builds with static runtime. Previous versions are without it.  
Update Qt 6.2.4 llvm-mingw builds built with llvm 15.

Qt 6.3 builds are removed.

### 2022.9.16
Update Qt 6.2.4 / 5.15.6 with updated patch of CVE-2022-37434. Qt 6.2 are rebuilt with QtWebEngine 6.3.2.  
Update to Xcode 14 and rebuild all of macOS hosted Qt 6.2 onwards.

### 2022.9.12
Update Qt 6.2.4 / 6.3.2 WebAssembly packages. They are currently built using PCH.  
Update Qt 6.2.4 / 6.3.2 llvm-mingw packages. They are currently built with WMF support.  
Update Qt 6.4.0-beta4. All configuration from previous 6.3 are available. RockyLinux 9 is used for Qt 6.4.0 Linux hosted build. WebAssembly and llvm-mingw packages are built using updated configuration today.

### 2022.9.11
Update Qt 6.3.2 with OpenSSL 3.0.5.  
Update Qt 6.2.4 with patch of CVE-2022-37434.  
Update Qt 5.15.6 with OpenSSL 1.1.1q. Existing patch are all in. Patch of CVE-2022-27404-27405-27406 and CVE-2022-37434 are added.  
Update Qt 5.12.12 macOS hosted Android builds which erroneously used CommandLineTools instead of Xcode as host build toolchain.

### Before Aug. 2022

[Here]({{% relref "miscellaneous/histories" %}})
