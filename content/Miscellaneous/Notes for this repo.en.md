---
title: "Notes for this repo"
draft: false
weight: 1
---

## Chinese / Multilingual Support

This website was English only since when it was initially built, although the maintainer of this website (me, Fsu0413) is a Chinese native speaker from the PRC.  
Currently I am gradually adding Simplified Chinese support on this website.

~~Recently~~ this website has gained multilingual support thanks to the built-in multilingual support of [Hugo](https://gohugo.io/) and the ~~recently switched~~ [Relearn](https://mcshelby.github.io/hugo-theme-relearn/) theme.  
~~Current Chinese support is in the stage of writing texts. There is a bunch of things which are not finished.~~  
~~But the main contents are rewritten using Chinese, which shouldn't bother us for downloading binaries.~~

If there are any constructive advices, feel free to [create issue on Github](https://github.com/Fsu0413/QtCompile/issues/new).

## Website Mirror

~~Recently~~ I created a mirror of this website in the Greatest China, using service of Gitee Pages.  
This mirror is configured to be displaying Simplified Chinese by default.

Due to the customize domain name function is only available under purchaged service of Gitee, Chinese mirror has to be under the domain of Gitee for now.  
I may purchage the service later when the service seems good enough for me.

[Github Pages (America, with English as default language)](https://build-qt.fsu0413.me/)  
[Gitee Pages (The Greatest China, with Chinese-S as default language)](https://fsu0413.gitee.io/qtcompile/)

## Reproduciable building

I use a set of scripts to do the build and packaging for [reproducible building](https://reproducible-builds.org/) Qt.  
If you are interested in build method, please check the following GitHub repo.

[GitHub](https://github.com/Fsu0413/Fs-scripts)

However unfortunely, this website is manually edited.  
Source of this site is:

[GitHub](https://github.com/Fsu0413/QtCompile)

## Notes on static builds

I don't use static builds in huge projects. I don't think it is wise to use a static build there.

Maybe you just want to distribute a single portable executable binary file, but there is limitations:

* It is not free of charge unless the program itself is a free software under (L)GPLv3.
* A few modules of Qt does not build. (WebEngine, etc...)
* Cannot use dynamically-linked plugin.
* It is not linked at build time, possibly causing linking problem afterwards.

To be wise and stop using static builds in huge projects. You'll feel liberated to make this change. Trust me.

## Static `Lite` Builds and Static `Full` Builds (Updated {{% date 2022 3 8 %}})

Static `lite` builds skipped most of Qt modules, only QtCore, QtDeclarative (QtQml 2), QtXmlPatterns and QtXXXExtras are built.  
It is useful for people who wants to build the QtIFW without building a full static Qt.

(Updated {{% date 2022 3 8 %}}) Qt 5 static `lite` builds is also for my build of QQtPatcher.  
(Updated {{% date 2021 12 4 %}}) Since Qt 6 cross builds of Qt need a host Qt of same version for its tools, we use this static `lite` version of Qt for producing host tools.

Static `full` builds don't skip most of Qt modules, only skip modules which does not build.

## Notes on users of Qt of old version

I only provide the prebuilt libraries of the latest version of each major release/LTS release, older non-LTS versions will get deleted soon after I release most of the packages of the new version.

I don't know why they don't update to the newest version of Qt of the current branch (e.g, Qt 5.6.1-1, at the time of writing, has released for more than half a month but quite a few users are still using 5.6.0).  

For stability? compatibility? feel lazy for updating? or other reasons?

* Stability  
I think updating to the latest version of the same branch increases stability. Qt only does bug-fixes in minor releases. This is not a problem.
* Compatibility  
Binaries of the same major releases are compatible. It is no need to concern.
* Lazy  
Don't compare laziness with me, I feel lazy for comparing.
* Other reasons  
I have no idea if there are any other reasons.

## Notes on the distributed compressed files

Archive files on Windows host are compressed using `7z` in `7z` format using LZMA2 Algorithm.  
The command line of generating the compressed file is like:
```
7z a -t7z -m0=LZMA2:d256m:fb273 -mmt=3 -myx -mqs -ms=on -- xxx.7z xxx
```

Archive files on Linux use GNU `tar`. Archive files on macOS use `bsdtar`.  
In addition, we use `7z` for the `xz` compression.  
The command line of generating the compressed file is like:
```
tar -cf - xxx | 7zr a -txz -m0=LZMA2:d256m:fb273 -mmt=3 -myx -si -- xxx.tar.xz
```

Make sure your uncompresser supports LZMA2 algorithm. For example:  
`7z` users should upgrade your `7z` to 9.20 or later.  
`WinRAR` users should upgrade your `WinRAR` to 4.00 or later.  
Other decompresser users should query for their latest version, since it may support LZMA2 algorithm.

Arch Linux and MSYS2 switched to zst for their package manager recently.  
Only recent GNU `tar` (1.31 or later) and recent `bsdtar` (3.3.3 or later) directly supports `.tar.zst` compress method.  
I will not use zst because the compress ratio is not as good as LZMA2(xz).

## Difference of this Qt and offically distributed Qt (Updated {{% date 2023 1 8 %}})

I provide only binary tarball, which contains only built Qt binary for each OS.  
It should work out of box (for Qt 5.14 or later) or work after patches to Qt (for Qt 5.13 and before).  
(Updated {{% date 2022 4 14 %}}) Since installers are often doubted for attaching unwanted software (I never mean to do it), I will never use installers.

(Updated {{% date 2020 6 7 %}}) There is **NO NEED TO LOGIN Qt ACCOUNT**!!! By doing this gets rid of the nonsense of "This can help optimize Qt".

All Qt builds here have been configured with `-no-icu`, because I thought that the ICU is useless for common usecases, and it is rather a big thing.  

Using linked OpenSSL support for packages which can't use platform native way for creating SSL sockets.
Windows builds before and including Qt 5.12 are using linked OpenSSL to dynamic(shared) libraries, Android builds are using statically linked OpenSSL.  
macOS builds are using SecureTransport instead of OpenSSL.  
Windows builds after and including Qt 5.13 are using SChannel instead of OpenSSL.

(Updated {{% date 2022 4 14 %}}) **No debug libs, which cuts more than a half of the size of the whole Qt package.**  
(Kindly please don't request it without commericial customization since I don't use it. Note that commerical customization has not started yet)

No examples, which cuts more than a half of the size of the whole Qt package.

No docs (and no `QDoc` for Qt 5.12 and later since it depends on Clang), since Qt docs can be read from [http://doc.qt.io](http://doc.qt.io) at any time, it is no need to bondle doc to the package.

(Updated {{% date 2023 1 8 %}}) **No certificate** which may be devastating for especially non-developers.  
Binary program certificate must be bought on expensive price, yet I as a personal developer can't afford it for only a simple trust verification.  
This leads to a problem that the program is reported to be not trusted when running my build of Qt.  
There is no solution for this problem at the moment. I won't buy certificate for verification until commericial customization started and I earned some money by it in the future.  
It is possible to implement GPG verifiiation before certificate can be bought. (Although it has been put away for a long time...)  
(Qt before 5.14 can't be trusted due to patch of Qt after install. Qt 5.14 and later can be relocated which resolves this problem)

## Notes for Qt versions before 5.14

Qt before 5.14 should reject using the binary files which were just uncompressed from the tarball.  
It should report "Qt is not properly installed, please run ```make install```" or something like this in Qt creator.

I redistributed a version of QQtPatcher in the package, you should run it to make Qt running.

The source code of the distributed QQtPatcher is on [GitHub](https://github.com/Fsu0413/QQtPatcher). It is a free software and distributed in public domain.

Do not put the library in a directory which contains non-ascii character or spaces.   
Bug will cause that the path of qmake cannot be properly parsed by Qt Creator.

## Qt offering changes 2020 (updated {{% date 2022 4 14 %}})

Qt just announced [Qt offering changes 2020](https://www.qt.io/blog/qt-offering-changes-2020).  
Following is my opinion of this blog.

First of all, I have a Qt account, but I don’t understand why I need a Qt account to install the Qt development kit.  
All files are compiled and linked from the same set of source code. It will not change even if you log in to your Qt account. It will not add any features to Qt. "This can help optimize Qt" is simply nonsense.

LTS is only available for commercial license. So what is the license for the LTS source package?  
(Removed {{% date 2022 3 8 %}}) ~~If it is also only available for commercial licenses, Qt basically says goodbye to stable open source software.~~  
(Updated {{% date 2022 3 8 %}}) With current release schedule any patch will be delivered after 1 year. It will be too late before a security issue has got patched, espically for original version built by tQtC.  
Besides, their LTS support time is not too long. Windows has 10 years of support time, (Updated {{% date 2022 4 14 %}}) ~~CentOS~~ RockyLinux has 10 years of support time, and Qt has only 3 years...

The offline installation package is only available for commercial licenses, which means that peoples in China can only find the time (usually before 8 am) when the network is available to install the Qt open source version with the online installation package.

What kind of company is a small company?  
Founding a shell company and using this company to buy Qt and distribute software, for only $499 per year? While other employees who work together use the open source version in private?  
This will definitely lose money.

I will continue my amateur job of building Qt. I hope Qt for MCUs will be open source soon.

(Appended {{% date 2023 9 2 %}}) I have been lucky enough to have spotted Qt for MCUs in a small project in my company. It is provided in binary form.  
It uses completely different base structure than desktop and mobile one - it does not use current existing free software like Qt Base, etc..

I did no studying or investigating about that part since my development has no relationship about Qt, so the above words is all I know about it.

## Qt 6 support platforms (updated {{% date 2023 6 14 %}})

See {{% QtBug 113979 "Qt 6.6 TQC Supported Targets" %}} and its predecessors.

Currently I am building Qt 6 for following platforms:

Windows 11 - VS2019, x86_64, host and target  
Windows 11 - MinGW, x86_64, host and target  
macOS 13 - toolchain provided by Apple with AppleClang, x86_64 / arm64_v8a, host and target, universal  
Android - NDK, arm / x86 / arm64 / x86_64, target only. No 32bit builds after 6.3  
WebAssembly - emscripten, target only  
Linux - toolchain provided by RedHat modified by RockyLinux developers with GCC, x86_64, host only

I will add build for following platforms:

Windows 11 - VS2019, arm64, target only (been put away)

Qt 6.2 is LTS release, but with Qt offering changes 2020 Qt 6.2 release to community comes one year later than it is released to commericial users.  
I will add bulid for static version for Qt 6.2, but I don't exactly know how Qt guys operate with their release...

I am using OpenSSL 3 series for Qt 6.2 onwards.

## GPG sign (Updated {{% date 2021 2 6 %}})

I am working on a method to GPG sign every package, but I didn't find a good method.  
I don't want to put the signature file besides the package, I think it will be a waste of upload step......

(Updated {{% date 2021 2 6 %}}) I haven't found a suitable solution, temporarily put it away....

## Windows 10 before version 1809 and 32-bit Windows deprecation (IMPORTANT NOTES!!) (updated {{% date 2023 3 25 %}})

(Updated {{% date 2023 3 25 %}}) Windows 8.1 reaches EOL on {{% date 2023 1 10 %}}.  
Since {{% date 2023 3 25 %}} all builds don't support Windows 8.1. Existing VS2015 and MinGW 7.3 builds are migrated to Windows 10.

Qt 6 builds before 6.2 supports only 64-bit Windows 10 1809 and later, while builds after 6.3 supports only latest Windows 10 (i.e. version after 2004 since they has same system files).

SINCE {{% date 2020 6 3 %}} (Qt 5.15 release and Qt 5.9 EOL) ONLY VS2015 AND MINGW 7.3 BUILDS SUPPORTS WINDOWS 8.1 by me.  
WINDOWS 10 IS MORE AND MORE POPULAR, AND RECEIVING MORE AND MORE NEW FEATURES. ONE SHOULD SWITCH TO WINDOWS 10 ASAP.

SINCE {{% date 2020 1 6 %}} (OpenSSL 1.0.2 EOL) NO LATER BUILD WILL SUPPORT WINDOWS 8 AND EARLIER BY ME, PLEASE UPDATE TO WINDOWS 8.1 AND LATER.

## Decided EOL of current building Qt LTS versions (Updated {{% date 2023 1 7 %}})

(Updated {{% date 2022 3 4 %}}) tQtC released Qt opensource 5.15.3 for a sudden and all the things changed since then.  
All of our EOL schedule becomes meaningless. We should re-consider the EOL date since Qt 5.15.

Note: since OpenSSL is currently built on all versions of my build except for WebAssembly, all of my builds should persist until EOL of that specific OpenSSL version.  
Currently OpenSSL 1.1.1 and 3.0 series are used.  
OpenSSL 1.1.1 series reaches EOL until {{% date 2023 9 11 %}}, while OpenSSL 3.0 series does until {{% date 2026 9 7 %}}.

Since Qt 5.15.8 starts supporting OpenSSL 3.0 series we may switch to OpenSSL 3.0 series on our Qt 5.15 Android builds after EOL of OpenSSL 1.1 series.  
Currently it is certain that Qt 5.15 will be supported for 5 years, but it is unknown that tQtC will provide source code of Qt 5.15 after {{% date 2024 5 26 %}}.  
If subsequent version of Qt 5.15 remains private we won't upgrade OpenSSL to post-3.0 version.

| Qt version | Build Target | EOL date | Notes |
|-|-|-|-|
| 5.12 Series | Windows | {{% date 2023 9 11 %}} | Same as EOL of OpenSSL 1.1.1 series, with VS version update within VS2017/9, no builds for VS2022 |
| | ~~macOS~~ | ~~{{% date 2021 11 25 %}}~~ (EOLed) | ~~Same as EOL of Qt 5.12~~ **A patch has released after 5.12 EOL and an extra package is made for it on macOS**. |
| | Android | {{% date 2023 9 11 %}} | Same as EOL of OpenSSL 1.1.1 series. Will stuck at Android NDK r21 LTS series |
| | ~~WebAssembly~~ | ~~{{% date 2021 11 25 %}}~~ (EOLed) | ~~Same as EOL of Qt 5.12~~ |
| 5.15 Series | Windows 11 with VS2019 (Shared) / VS2022 | {{% date 2024 5 26 %}} | Same as EOL of Qt opensource 5.15, with WebEngine and Script got update ahead of time, with VS version update within VS2019/22 |
| | Windows with VS2015 / VS2017 / VS2019 (static) / MinGW 8.1.0 | {{% date 2024 5 26 %}} | Same as EOL of Qt opensource 5.15, with Script update ahead of time, with VS version update within VS2017/9/22 |
| | macOS | {{% date 2024 5 26 %}} | Same as EOL of Qt opensource 5.15, with WebEngine and Script got update ahead of time, with (at best effort) Xcode and macOS update |
| | Android | {{% date 2026 9 7 %}} | Same as EOL of OpenSSL 3.0 series. |
| | WebAssembly | {{% date 2024 5 26 %}} | Same as EOL of Qt opensource 5.15 |
| 6.2 Series | Windows 11 with VS2019 (Shared) / VS2022 | {{% date 2026 9 7 %}} | Same as EOL of OpenSSL 3.0 series, with WebEngine update ahead of time, with VS version update |
| | Windows 11 with VS2019 (static) | {{% date 2026 9 7 %}} | Same as EOL of OpenSSL 3.0 series, with VS version update |
| | Windows 11 with MinGW 11.2.0 / MinGW-LLVM 15 | {{% date 2026 9 7 %}} | Same as EOL of OpenSSL 3.0 series, with MinGW version update |
| | macOS (Shared) | {{% date 2026 9 7 %}} | Same as EOL of OpenSSL 3.0 series, with WebEngine update ahead of time, with (at best effort) Xcode and macOS update |
| | macOS (static) | {{% date 2026 9 7 %}} | Same as EOL of OpenSSL 3.0 series, with (at best effort) Xcode and macOS update |
| | Android | {{% date 2026 9 7 %}} | Same as EOL of OpenSSL 3.0 series, Will stuck at Android NDK r23 LTS series |
| | WebAssembly | {{% date 2025 9 29 %}} | Same as EOL of Qt opensource 6.2 |

Commericial-only Qt Open Source Release Date (ETA)

| Qt Version | Commericial Release Date | Open Source Release Date |
|-|-|-|
| 5.15.11 | {{% date 2022 10 5 %}} | {{% date 2023 10 5 %}} |
| 5.15.12 | {{% date 2022 12 27 %}} | {{% date 2023 12 27 %}} |
| 5.15.13 | {{% date 2023 3 9 %}} | {{% date 2024 3 9 %}} |
| 5.15.14 | {{% date 2023 5 25 %}} | {{% date 2024 5 25 %}} |
| 5.15.15 | {{% date 2023 8 31 %}} | {{% date 2024 8 31 %}} (Need to check if Qt will really release this version to opensource on that day) |
| 6.2.6 | {{% date 2022 9 27 %}} | {{% date 2023 9 27 %}} |
| 6.2.7 | {{% date 2023 1 2 %}} | {{% date 2024 1 2 %}} |
| 6.2.8 | {{% date 2023 4 18 %}} | {{% date 2024 4 18 %}} |
| 6.2.9 | {{% date 2023 7 4 %}} | {{% date 2024 7 4 %}} |

## Incoming update for future release

~~Use Android NDK r23 series for building Qt 5.15.7 onwards.~~ (Build failed also on 5.15.10. Will test it on 5.15.11)  
~~Use GCC 11 with MinGW-w64 v9 for building Qt 5.15.10 onwards.~~ (Build failed on 5.15.10. Will test it on 5.15.11)  

## Existing Patches

Starting from {{% date 2022 3 12 %}} I am shipping Qt with patches from Qt.  
Most of them are CVE patches which can be downloaded from [Qt Downloads](https://download.qt.io/), others are build fixes which are download from Qt Gerrit or KDE.

Following is a table for patches of each version I am currently building.  
Note that I won't patch an active version of Qt and will simply wait for future release. So only Commericial LTS and EOL version are patched.  
A patch will removed from following table when this patch is shipped or not planned to be applied in all of the maintained versions.  
Version number in brackets are the version when the corresponding patch will be shipped.

| Issue \ Qt Version | 5.12.12 | 5.15.10 | 6.2.5 | 6.5.3 (est.) |
|-|-|-|-|-|
| CVE-2022-25255 | [√](https://codereview.qt-project.org/c/qt/qtbase/+/396020) | shipped | shipped | shipped |
| CVE-2022-27404-27405-27406 | - | [√](https://download.qt.io/official_releases/qt/5.15/CVE-2022-27404-27405-27406-qtbase-5.15.diff) (5.15.11) | [√](https://download.qt.io/official_releases/qt/6.2/CVE-2022-27404-27405-27406-qtbase-6.2.diff) (6.2.6) | shipped |
| CVE-2022-37434 | - | [√](https://download.qt.io/official_releases/qt/5.15/CVE-2022-37434-qtbase-5.15.patch) (5.15.11) | [√](https://download.qt.io/official_releases/qt/6.2/CVE-2022-37434-qtbase-6.2.patch) (6.2.6) | shipped |
| CVE-2023-24607 | - | [√](https://download.qt.io/official_releases/qt/5.15/CVE-2023-24607-qtbase-5.15.diff) (5.15.13) | [√](https://download.qt.io/official_releases/qt/6.2/CVE-2023-24607-qtbase-6.2.diff) (6.2.8) | shipped |
| CVE-2023-32573 | - | [√](https://download.qt.io/official_releases/qt/5.15/CVE-2023-32573-qtsvg-5.15.diff) (5.15.14) | [√](https://download.qt.io/official_releases/qt/6.2/CVE-2023-32573-qtsvg-6.2.diff) (6.2.9) | shipped |
| (5.15 series specific) macOS build fix | - | [macOS only](https://invent.kde.org/qt/qt/qtlocation-mapboxgl/-/commit/5a07e1967dcc925d9def47accadae991436b9686 "Patch provided by KDE") (5.15.14) | - | - |
| CVE-2023-32762 | - | [√](https://download.qt.io/official_releases/qt/5.15/CVE-2023-32762-qtbase-5.15.diff) (5.15.14) | [√](https://download.qt.io/official_releases/qt/6.2/CVE-2023-32762-qtbase-6.2.diff) (6.2.9) | shipped |
| CVE-2023-32763 | - | [√](https://download.qt.io/official_releases/qt/5.15/CVE-2023-32763-qtbase-5.15.diff) (5.15.15) | [√](https://download.qt.io/official_releases/qt/6.2/CVE-2023-32763-qtbase-6.2.diff) (6.2.9) | shipped |
| CVE-2023-33285 | - | [√](https://download.qt.io/official_releases/qt/5.15/CVE-2023-33285-qtbase-5.15.diff) (5.15.14) | [√](https://download.qt.io/official_releases/qt/6.2/CVE-2023-33285-qtbase-6.2.diff) (6.2.9) | shipped |
| CVE-2023-34410 | - | [√](https://download.qt.io/official_releases/qt/5.15/CVE-2023-34410-qtbase-5.15.diff) (5.15.15) | [√](https://download.qt.io/official_releases/qt/6.2/CVE-2023-34410-qtbase-6.2.diff) (6.2.9) | shipped |
| CVE-2023-37369 | - | [√](https://download.qt.io/official_releases/qt/5.15/CVE-2023-37369-qtbase-5.15.diff) (5.15.15) | [**×**](# "Official patch causes CONFLICT. Depends on a commit of Qt 6.2.9. Given up investigating due to no active distro / project is fixing this issue") (6.2.10) | shipped |
| CVE-2023-38197 | - | [√](https://download.qt.io/official_releases/qt/5.15/CVE-2023-38197-qtbase-5.15.diff) (5.15.15) | [**×**](# "Depends on patch of CVE-2023-37369") (6.2.10) | **x** (6.5.3) |
