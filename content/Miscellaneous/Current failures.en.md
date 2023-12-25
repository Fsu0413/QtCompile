---
title: "Current failures"
draft: false
weight: 3
---

## QDoc after Qt 5.12 cannot use static linked clang when using MSVC

It uses `libclang_static.lib` but clang don't provide this one.  
I have decided not provide LLVM-based QDoc until I find a way to static link it.

Update {{% date 2020 11 3 %}}:  
`libclang_static.lib` is packed seprately using script by Qt guys.  
Thanks "lixinwei" on QTCN.org for telling me related info. [Original post](http://www.qtcn.org/bbs/job.php?action=topost&tid=85983&pid=200952) (Sorry, it's in Chinese)

## Command line too long when building Qt 6.2 series for MinGW

See {{% QtBug 96339 %}} - workaround using CMake 3.20.2

## QtOpcUa issues (Updated {{% date 2023 12 25 %}})

QtOpcUa ~~is currently~~ was previously not compatible with OpenSSL 3.0 series.  
Temporarily disabling QtOpcUa build until the Qt guys update their open62541 version.  
This change takes place since building and packaging of Qt 6.2.3 (when OpenSSL 3.0 started being used).

~~But seems like that open62541 guys don't treat this as issue despite the increasing popularity of OpenSSL 3.0 series.~~  
~~Version 1.3.3 has released without any fix about OpenSSL 3.0.~~  
~~I don't know if we can bring QtOpcUa back in Qt 6.4...~~

Update {{% date 2022 11 6 %}}:  
open62541 hasn't release any version after 1.3.3 so there is no OpenSSL 3.0 support on open62541 of QtOpcUa 6.4.  
There is a merged Pull Request on Github which added OpenSSL 3.0 support. Reference: [Github Pull Request](https://github.com/open62541/open62541/pull/5349).  
I will restart building with QtOpcUa when this change is got integrated in next released version of open62541.

Update {{% date 2023 1 23 %}}:  
open62541 released 1.3.4 at {{% date 2022 11 14 %}}. QtOpcUa 6.5 ships this version of open62541.  
I'll try building with QtOpcUa enabled on build of Qt 6.5. (Packages built before {{% date 2023 1 23 %}} are without QtOpcUa)

Update {{% date 2023 9 2 %}}:  
It is estimated that we can build QtOpcUa on Qt 6.2.7 which was released on {{% date 2023 1 2 %}}.

Update {{% date 2023 12 25 %}}:
Qt 6.2.7 released with open62541 version 1.1.  
We'd wait for next version of Qt 6.2.

## Various failures building higher version of QtWebEngine on Qt 6.2.4

QtWebEngine 6.3.2 on Qt 6.2.4 fails on macOS when using Xcode 14.1. It was OK using Xcode 14.0.1. Probably because QtWebEngine 6.3.2 is incompatible with macOS Ventura SDK.  
QtWebEngine 6.4.0 on Qt 6.2.4 fails on macOS and Windows. All of them succeeds inside `gn` and outside it. Different failure occurs on Windows and macOS.

I'm tired of investigating them and will distribute Qt 6.2 series without QtWebEngine.  
QtWebEngine has not released as LTS since Qt 6.2.4 and the Qt guys are simply taking QtWebEngine from later version (6.3, etc) for their 6.2 LTS series releases.  
But no one else knows what version Qt guys are using for their Qt 6.2 LTS Releases except for the official packagers, as the QtWebEngine version is always different than the binary files.

Update {{% date 2023 3 25 %}}:  
QtWebEngine still develops in its own branch, but only `qtwebengine-chromium` repository is made public.  
The SHA1 of commits of each release version are recorded in tQtC's own yocto repository `meta-qt6` but commit of `qtwebengine` repository can't be found.  
I don't expect QtWebEngine can build with mismatched `qtwebengine` and `qtwebengine-chromium` repositories. Even if we are lucky enough that the code builds I don't expect it works.

Since then I won't provide builds of Qt 6.2 LTS series with QtWebEngine.  
Existing package with QtWebEngine will be removed after {{% date 2023 3 25 %}}.

## Patch of CVE-2023-37369 conflicts on Qt 6.2.4 / 6.2.5

The patch is made for working with Qt 6.2.9, where it included an incompatible modification compared to Qt 6.2.4 / 6.2.5.  
I've made patches on Qt 6.2.4 to fix the conflict but it conflicts with 6.2.5 again.

I won't apply this patch before Qt 6.2.9 unless there are packagers / Linux distros who are aware of this issue and made patches.

Subsequent patch of CVE-2023-38197 depends on patch of CVE-2023-37369 thus can't be applied either.
