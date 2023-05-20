---
title: "Previous Histories"
draft: false
weight: 4
---

## {{% date 2023 3 25 %}}
Update OpenSSL 1.1.1t / 3.0.8 with [the minor fix](https://www.openssl.org/news/secadv/20230322.txt).  
Update Qt 5.12.12 / 5.15.8 / 6.2.4 series, rebuilt with this OpenSSL while 5.15.8 is with QtWebEngine 5.15.13.  
Update Qt 6.4.3 and Qt 6.5.0-rc.

Existing builds on Windows 8.1 are migrated to Windows 10 10.0.19045 since EOL of Windows 8.1.  
Further builds won't support Windows 8.1 and earlier.

Happy birthday to Iroi Imagay (the second time)!

## {{% date 2023 2 25 %}}
Update Qt 6.5.0-beta3 series built with NDK r25c, with builtin MySQL (MariaDB) Database Backend and plugin.

## {{% date 2023 2 12 %}}
Update Qt 6.4.2 series built with NDK r25c.

## {{% date 2023 2 10 %}}
Update Qt 5.12.12 / 5.15.8 / 6.2.4 / 6.4.2 series with OpenSSL 1.1.1t / 3.0.8.  
Update Qt 5.15 / 6.2 / 6.4 series with builtin MySQL (MariaDB) Database Backend and plugin.  
Update Qt 5.15 static `full` series with more Visual Studio version. Discontinue Qt 5.12 static `full` versions.

## {{% date 2023 1 28 %}}
Update Qt 6.5.0-beta2 packages (with QtOpcUa)  
Update Qt 6.2.4 static `full` builds with a workaround of {{% QtBug 102877 %}} .

## {{% date 2023 1 23 %}}
Update Qt 6.5.0-beta1 packages (without QtOpcUa)  
Update Qt 6.2.4 / Qt 6.4.2 with static `libgcc` on Windows. Previous version relies on the `libgcc` DLL. Affected versions are all cross built version and the static `full` builds.

## {{% date 2023 1 8 %}}
Update Qt 6.4.2 / Qt 5.15.8 packages.  
Update Qt 6.2.4 packages built with OpenSSL 3.0.7 with [the minor fix](https://www.openssl.org/news/secadv/20221213.txt).

Qt 6 Linux hosted cross built packages has a problem where the host tool was not properly deployed.  
This time the package is rebuilt with fix.

## {{% date 2022 11 20 %}}
Update all cross built package with CMake toolchain refactored. Currently it can automatically use the bundled host tool using bundled `qt-cmake` script.  
Qt 6.2.4 / 6.4.1, Android / WebAssembly packages are all updated.

## {{% date 2022 11 19 %}}
Update Qt 6.4.1 WebAssembly macOS host with Thread feature ON. (I did only modified x86_64 build and... I am using arm64 build for base of universal builds and it's gone)

## {{% date 2022 11 18 %}}
Update Qt 6.4.1.  
Update Qt 6 WebAssembly with Thread feature ON. (Previous versions are missing this feature)   
Update Qt 6 macOS Universal builds. Future Qt 6 builds of macOS will only provide Universal builds.  
Update Qt 6.2.4 Windows VS builds with updated VS version.

## {{% date 2022 11 8 %}}
Update Qt 6.2.4 with OpenSSL 3.0.7 (Without QtWebEngine since all builds of QtWebEngine failed). Existing patches are all in.  
Update Qt 5.15.7 with OpenSSL 1.1.1s on macOS (Without QtWebEngine).

Qt 6.2.4 cross builds (Linux / macOS host) are packaged with `libexec` folder of host builds where tools like `lrelease` are lying in.

## {{% date 2022 11 6 %}}
Update Qt 5.15.7 with OpenSSL 1.1.1s (excluding macOS, compile failed in QtWebEngine). Existing patches are all in.   
Update Qt 5.12.12 with OpenSSL 1.1.1s.

Reconstruct website with [Relearn](https://mcshelby.github.io/hugo-theme-relearn/) theme, which have better support for multilingual contents.  
Add Simplified Chinese to website.

## {{% date 2022 10 4 %}}
Update Qt 6.4.0.  
Update Qt 6.2.4 static builds with static runtime. Previous versions are without it.  
Update Qt 6.2.4 LLVM-MinGW builds built with llvm 15.

Qt 6.3 builds are removed.

## {{% date 2022 9 16 %}}
Update Qt 6.2.4 / 5.15.6 with updated patch of CVE-2022-37434. Qt 6.2 are rebuilt with QtWebEngine 6.3.2.  
Update to Xcode 14 and rebuild all of macOS hosted Qt 6.2 onwards.

## {{% date 2022 9 12 %}}
Update Qt 6.2.4 / 6.3.2 WebAssembly packages. They are currently built using PCH.  
Update Qt 6.2.4 / 6.3.2 LLVM-MinGW packages. They are currently built with WMF support.  
Update Qt 6.4.0-beta4. All configuration from previous 6.3 are available. RockyLinux 9 is used for Qt 6.4.0 Linux hosted build. WebAssembly and LLVM-MinGW packages are built using updated configuration today.

## {{% date 2022 9 11 %}}
Update Qt 6.3.2 with OpenSSL 3.0.5.  
Update Qt 6.2.4 with patch of CVE-2022-37434.  
Update Qt 5.15.6 with OpenSSL 1.1.1q. Existing patches are all in. Patch of CVE-2022-27404-27405-27406 and CVE-2022-37434 are added.  
Update Qt 5.12.12 macOS hosted Android builds which erroneously used CommandLineTools instead of Xcode as host build toolchain.

## {{% date 2022 8 23 %}}
Update Qt 5.12.12 with OpenSSL 1.1.1q.  
Update Qt 6.2.4 with patch of CVE-2022-27404-27405-27406 provided by Qt, and OpenSSL 3.0.5.   
Update Qt 6.3.1 WebAssembly builds, which are built using emsdk 3.1.6.

Qt 5.15.5 is not updated since patch of CVE-2022-27404-27405-27406 provided by Qt conflicts with 5.15.5 code base.  
I'll wait for 5.15.6 and will release without the patch if this patch doesn't work on 5.15.6 either.

Qt 6.3.1 is not updated. Let's wait for 6.3.2.

## {{% date 2022 6 29 %}}
Update Qt 5.15.5 with OpenSSL 1.1.1p and QtWebEngine 5.15.10.  
~~macOS 11 host is currently failing and builds are not updated. May be a problem of VirtualBox. Currently under investigation.~~ Resolved by a VirtualBox upgrade.

## {{% date 2022 6 26 %}}
Remove GitHub links since it is unstable in The Greatest China.  
Update Qt 5.12.12 with OpenSSL 1.1.1p.  
Update Qt 6.2.4 / 6.3.1 with OpenSSL 3.0.4.

Qt 5.15 are not updated for now since security issues of built versions are not patched.

## {{% date 2022 4 13 %}}
Upload Qt 6.3.0 versions.  
Update Qt 5.15 / 6.2 with CVE patches.

Happy birthday to me!

## {{% date 2022 3 25 %}}
Upload Qt 6.2.4 versions.  
Update Qt 5.12 / 5.15 versions with OpenSSL 1.1.1n / 3.0.2.

Happy birthday to Iroi Imagay!

## {{% date 2022 3 11 %}}
Upload Qt 5.12.12 / 5.15.3-5 VS 2017+ versions.

## {{% date 2022 3 9 %}}
Upload 5.12.12 macOS (Extra version) / Android versions with CVE-2022-25255 patched.  
Upload Qt 5.15.3 with QtWebEngine 5.15.8 / QtScript 5.15.8, with CVE-2022-25255 and CVE-2022-25643 patched.  
(VS version is currently undone for now since VS has got an update and Qt is currently rebuilding)

({{% date 2023 1 14 %}} appended modification) Update disclaimer. Consequent builds will have CVE patched.  
Code of Qt 5.12.12 in local environment is got CVE patched so newer build will always have CVE patched.  
Code of Qt 5.15.3 in local environment is got CVE patched and will be patched every time Qt opensource release. Newer build will always have CVE patched.  
Qt 6.2.4 will have CVE patched in original code and will make opensource release soon. Let's wait for it and do not patch the code.

## {{% date 2022 2 9 %}}
Upload 6.2.3 all versions.  
Update VS2017 / VS2019 / VS2022 to their latest version.  
Upload Qt 6.2.3 series built with VS2022.

## {{% date 2022 1 7 %}}
Upload Qt 5.15.2 with QtWebEngine 5.15.8 / QtScript 5.15.8.  
Upload Qt 5.15.2 series built with VS2022.

## {{% date 2021 12 29 %}}
Upload 5.12.12 Android / 5.12.12 Windows / 5.15.2 Android / 6.2.2 Android versions with OpenSSL 1.1.1m.  
Windows hosted versions has their QQtPatcher update to 0.8.1, which support more 5.12 specific hard-code path patching.

## {{% date 2021 12 7 %}}
Upload 6.2.2 macOS / Windows versions with QtPdf.  
QtPdf is not automatically built anymore with QtWebEngine since Qt 6, and should be enabled manually for now.

Upload 6.2.2 macOS ARM64 version.

## {{% date 2021 12 5 %}}
Upload Qt 5.15.2 with QtWebEngine 5.15.7 / QtScript 5.15.7.  
Remove 5.15.2 Windows arm64 version since it is not officially supported.  
macOS Qt 5.15 / 5.12 cross builds will stuck at macOS 11 with Xcode 12.5.1 since compile error occurs on Xcode 13.

Upload Qt 6.2.2 series, including MinGW version.  
Update to MinGW-w64 v9 w/ GCC 11.2.0, which is same as what Qt is using.  
Update Android SDK for building Qt 6.2.2.

Remove 6.1.3 builds since builds of Qt 6.2 of same configuration is available.

## {{% date 2021 12 4 %}}
Upload Qt 5.12.12.  
Remove 5.12.10 Windows arm64 version since it does not build anymore since one year ago.

Since 5.12 series reaches its EOL and macOS and WebAssembly versions don't use OpenSSL, this build are their final build.  
Other builds where OpenSSL are used will be built until OpenSSL 1.1.1 series reaches EOL, i.e., {{% date 2023 9 11 %}}.

## {{% date 2021 10 19 %}}
Upload Qt 6.2.0 using [mstorsjo's LLVM-based MinGW-w64 toolchain](https://github.com/mstorsjo/llvm-mingw).  
Currently only x86_64 build is available, with both UCRT and msvcrt versions.

These build use newer MinGW-w64 version which is v9, while the GCC 8.1.0 one is using v6.  
I'd recommend using this version if you want to try something new.

## {{% date 2021 10 3 %}}
Upload Qt 6.2.0.

## {{% date 2021 9 29 %}}
Upload Qt 6.2.0-rc2.

## {{% date 2021 9 11 %}}
Upload Qt 5.15.2 with WebEngine 5.15.6 / QtScript 5.15.6.  
Upload Qt 5.15.2 for VS2017+ without WebEngine for newer VS versions.

## {{% date 2021 9 4 %}}
Upload Qt 6.1.3.  
Update OpenSSL to 1.1.1l.  
Rebuild 5.15.2 / 5.12.11 Android version using OpenSSL 1.1.1l.  
Rebuild 5.12.11 Windows version using OpenSSL 1.1.1l. (except for MinGW 64-bit which build failed)

## {{% date 2021 7 2 %}}
Upload Qt 6.1.2.

## {{% date 2021 6 25 %}}
Upload archives to OSDN again for better network in the Greatest China.

## {{% date 2021 6 19 %}}
Upload Qt 5.15.2 with QtWebEngine 5.15.5 / QtScript 5.15.5.  
Update Qt 5.12.11 with QtWebEngine. Downgrade macOS to 5.15.7 for building QtWebEngine. Will use macOS 10.15 for Qt 5.12 builds.

## {{% date 2021 6 9 %}}
Upload Qt 6.1.1 with previously failed Android versions.

## {{% date 2021 5 28 %}}
Upload Qt 5.12.11 (Windows ARM64 version doesn't upload because of compile failure)  
In-place reinstall RockyLinux 8 to replace the current CentOS 8 for Linux build host, preserving all configuration and environment.

## {{% date 2021 5 13 %}}
Upload Qt 5.15.2 with WebEngine 5.15.4 / QtScript 5.15.4.  
Rebuild 5.15.2 Android version using OpenSSL 1.1.1k.

## {{% date 2021 5 11 %}}
Upload 6.1.0 (Desktop version)  **Android version build fails**  
Qt 6.1 series is shipping with full addon. I don't need to download addon manually.

## {{% date 2021 4 9 %}}
Upload 6.0.3 w/ addon.  
Site is re-generated using [Hugo](https://gohugo.io), using [techdoc](https://thingsym.github.io/hugo-theme-techdoc/) theme. ([amWiki](https://github.com/TevinLi/amWiki) was based on GitHub Atom, and hasn't been updated for a while)

## {{% date 2021 3 15 %}}
Upload 6.0.2 w/ addon. (Previous versions are without addon)  
Rebuild 5.15.2 Android version using Android NDK r21e.  
Rebuild 5.12.10 VS2019 builds with newer VS2019 and newer OpenSSL.

I will ship Qt 6 with full addon from now on. There was and will be no `Lite` version of dynamic/shared builds.

## {{% date 2021 3 9 %}}
Upload 5.15.2 w/ QtWebEngine 5.15.3 builds for VS2019 / macOS 11.  
Windows SDK is updated to the latest version, which is 10.0.19041.  
Upload 5.12.10 Android builds w/ Android NDK r21e.

## {{% date 2021 3 4 %}}
Upload 6.0.2 builds.  
VS2019 is updated to the latest version, which is 16.9.0.  
Update macOS to 11.2.2.  
**ANDROID BUILDS ARE WITHOUT LINKED OpenSSL SUPPORT due to compile error!!!!!!!!**

## {{% date 2021 2 21 %}}
Upload Windows hosted Android builds of Qt 6.0.1.  
**ANDROID BUILDS ARE WITHOUT LINKED OpenSSL SUPPORT due to compile error!!!!!!!!**

## {{% date 2021 2 6 %}}
Upload 6.0.1 builds except Windows crossed Android builds.  
VS2019 is updated to the latest version, which is 16.8.4.  
Update macOS to 11.1.  
**ANDROID BUILDS ARE WITHOUT LINKED OpenSSL SUPPORT due to compile error!!!!!!!!**

## {{% date 2021 1 3 %}}
Upload 6.0.0 Android builds (Linux host).  
**ANDROID BUILDS ARE WITHOUT LINKED OpenSSL SUPPORT due to compile error!!!!!!!!**

## {{% date 2021 1 2 %}}
Upload 6.0.0 Android builds (macOS host).  
Rebuild 6.0.0 Windows and macOS builds with stripped binary.  
Note that Android API Level has changed to android-24 since Qt 6.0.0.  
**ANDROID BUILDS ARE WITHOUT LINKED OpenSSL SUPPORT due to compile error!!!!!!!!**

## {{% date 2020 12 20 %}}
Upload 6.0.0 Windows and macOS builds.

## {{% date 2020 12 17 %}}
Upload 5.15.2 builds. (All builds are without QtWebEngine because of compile failure)  
Update macOS to 11.0.1.  
VS2017/2019 are updated to the latest version, which is 15.9.30/16.8.3.

## {{% date 2020 11 11 %}}
Upload 5.12.10 builds.  
macOS is updated to 10.15.7 and Xcode is updated to 12.0.  
VS2019 is updated to the latest version, which is 16.7.7.

**N.B.** Update this time contains modification regarding Qt 6, where the compressed file contains the folder without build date in its name.  
If the repository is operated using script, it needs to be modified according to above modification.

## {{% date 2020 9 12 %}}
Upload 5.15.1 builds.  
macOS is updated to 10.15.6 (19G2021)  
VS2017/2019 are updated to the latest version, which is 15.9.27/16.7.3.

## {{% date 2020 7 7 %}}
~~Upload all artifacts, also to GitHub release in addition to SourceForge.~~ (Deprecated)

## {{% date 2020 6 19 %}}
Upload Android NDK to r21d.  
Rebuilt all android packages using new NDK.

## {{% date 2020 6 18 %}}
Upload 5.12.9 builds.

## {{% date 2020 6 4 %}}
Upload 5.15.0 macOS host builds. (macOS host builds of 5.12.8 have compile failure, we should wait for 5.12.9)   
Upload 5.15.0 Android builds. (macOS 10.15.5 hosted)

## {{% date 2020 6 3 %}}
Add proprietary codecs support for Qt WebEngine for Qt 5.12.9 and 5.15.0 or later.  
Upload 5.15.0 series. (**Except macOS host builds, which encountered some issue while building**)  
Use MinGW-w64 w/ GCC 8.1.0 for Qt 5.15.0 series, switch the build environment of MinGW-w64 w/ GCC 8.1.0 to Win10.  
Upload 5.9.9 VS2017 builds for newer VS2017 version.  
Upload 5.12.8 WebAssembly builds for newer emsdk definition.  
Upload 5.12.8 Android builds for NDK r21b (including macOS hosted builds).  
Remove 5.14 series except macOS ones. (macOS ones will be deleted once 5.15 finishes building and uploading)

Since Qt 5.9 series has reached EOL, there will be no further Qt 5.9 builds.  
i.e., this build is the last build of these packages.  
The build script and environment of Qt 5.9 series has been destructed.

## {{% date 2020 5 18 %}}
Upload 5.15.0-rc2 series. (**All macOS version, including cross builds, are not uploaded because of broken environment**)  
Update Win10 to 10.0.19041(2004)

## {{% date 2020 4 25 %}}
Upload 5.15.0-beta4 series. (**All macOS version, including cross builds, are not uploaded because of broken environment**)

## {{% date 2020 4 12 %}}
Upload 5.15.0-beta3 series. (**All macOS version, including cross builds, are not uploaded because of broken environment**)

## {{% date 2020 4 11 %}}
Upload 5.12.8 series. (**All macOS version, including cross builds, are not uploaded because of broken environment**)

## {{% date 2020 4 3 %}}
Upload 5.14.2 series. (macOS versions are not provided due to QtWebEngine compile failure)

## {{% date 2020 3 26 %}}
Upload 5.15.0-beta2 series. (Static `Full` version don't compile)  
~~Mirror this site on Coding.net for faster browsing in China.~~ (Broken)

## {{% date 2020 3 6 %}}
Upload 5.12.7 Android series with NDK r21.  
Upload 5.15.0-beta1 series. (VS2017 and VS2019 shared builds are not provided due to QtWebEngine compile failure)

## {{% date 2020 2 6 %}}
Upload Windows on ARM64 cross build. (for now it only supports Qt 5.12 and later using VS2017)

## {{% date 2020 2 5 %}}
Upload Qt 5.12.7 Series. (Qt 5.12.7 actually released on {{% date 2020 1 31 %}}, but I didn't mention it....)

Note: QQtPatcher has got an update (to 0.7.0) after the build completed.  
Since most of the modifications affects Windows builds, I only manually recompressed Windows packages.  
Other packages are not recompressed.

## {{% date 2020 2 3 %}}
Add new configurations of static `Full` packages of MinGW builds of Qt 5.12 Series.  
Upload Qt 5.12.6 MinGW static `Full` builds.

## {{% date 2020 2 2 %}}
Rebuild Qt 5.12.6 VS2017 & VS2019 versions using newer VS.  
Resolve the problem where OpenSSL libraries are not in static `Full` builds.

## {{% date 2020 2 1 %}}
I have switched to CentOS 8 for Linux host, affects both Android and WebAssembly builds.  
For now only 5.14 series is built successfully and uploaded.  
CentOS 7 and Ubuntu 16.04 environment has been destructed.

Upload Qt 5.14.1 Series.  
Rebuild all Linux hosted Android builds and WebAssembly builds, using CentOS 8.  
Since there is no host tools in OpenSSL packages, most of the OpenSSL packages are not rebuilt.

## {{% date 2020 1 16 %}}
Recompress the Qt 5.6 static `Full` packages due to a script bug which causes the missing of OpenSSL libraries.  
Note that the packages are not rebuilt.  
(Qt 5.12 packages will be fixed later when OpenSSL 1.1 series or Qt 5.12 series updates)

## {{% date 2020 1 5 %}}
Packages using OpenSSL 1.0.2 Series rebuilt using OpenSSL 1.0.2u.  
Including all Qt 4 packages and non-macOS Qt 5.6/5.9 packages.

Since OpenSSL 1.0.2 Series has reached EOL, there will be no further Qt 4 and Qt 5.6 builds.  
i.e., this build is the last build of these packages.  
The build script and environment of Qt 4 and 5.6 series has been destructed.

## {{% date 2019 12 26 %}}
Windows 8.1 Update build environment has been finished, and Windows Server 2008 R2 build environment has been destructed.  
Upload all packages which build on Windows 8.1.  
Re-add QtSpeech and QtConnectivity module, which were previously failed to build due to Windows SDK version.

## {{% date 2019 12 22 %}}
Upload 5.9.9 and 5.14.0 packages.  
(Qt 5.14.0 for Android is missing due to an error during configure)

## {{% date 2019 12 5 %}}
Add support for macOS build. For now Qt 4.8.7 / 5.6.3 / 5.9.8 / 5.12.6 / 5.13.2 are supported.

Qt 4.8.7 / 5.6.3 are built using OS X 10.10  
Qt 5.9.8 / 5.12.6 are built using macOS 10.14  
Qt 5.13.2 is built using macOS 10.15

## {{% date 2019 12 2 %}}
Uploaded all rebuilt packages after my business trip.  
Shared library of OpenSSL 1.1 series are also included correctly, which wasn't included due to an oversight.

## {{% date 2019 11 22 %}}
Update pending after I return to China.....  
Qt 5.12 Series => 5.12.6  
Qt 5.13 Series => 5.13.2 -> prepare to migrate to Qt 5.14 Series  
OpenSSL 1.0.2 Series => OpenSSL 1.0.2t (affects Qt 4.8/5.6/5.9 Series)  
OpenSSL 1.1.1 Series => OpenSSL 1.1.1d (affects Qt 5.12/5.13 Series)  
VS2017 => 15.9.17  
VS2019 => 16.3.10  
Android NDK => r20b

OS update pending.....  
Win10 => 10.0.18363  
CentOS 7 => 7.7.1908 (Should there be a CentOS 8 environment? Currently Ubuntu 16.04 LTS is used to build the WebAssembly packages. If we change to CentOS 8 then it will become based on newer software)  
macOS 10.14 => 10.15

There will be no further build of original Qt 4.8/5.6 after OpenSSL 1.0.2 Series gets EOL (will be at {{% date 2019 12 31 %}})  
There will be no further build of original Qt 5.9 after Qt 5.9 Series gets EOL (will be at {{% date 2020 5 31 %}})  
There will be no build on Windows 7 (Server 2008 R2) after Windows 7 gets EOL (will be at {{% date 2020 1 11 %}}), existing Windows 7 builds will migrate to Windows 8.1 (Server 2012 R2)

## {{% date 2019 8 26 %}}
A bug about packaging has been revealed. It affects all versions of Qt 5.12 or later.  
The package of 5.12.5 will fix this issue.

## {{% date 2019 8 3 %}}
Re-create this site using [amWiki](https://github.com/TevinLi/amWiki).  
Since there is a builtin content list when using [amWiki](https://github.com/TevinLi/amWiki), it no longer needs to write the downloadable content list manually by now.

## {{% date 2019 7 13 %}}
Rebuild __ALL__ packages using updated QQtPatcher due to a bug in QQtPatcher.  
VS2017 is updated to 15.9.14.  
VS2019 is updated to 16.1.6.

## {{% date 2019 7 9 %}}
WebAssembly packages are updated to Qt 5.12.4 and Qt 5.13.0.

## {{% date 2019 7 8 %}}
Android packages are updated to Qt 5.12.4 and Qt 5.13.0. __Used NDK r19c, although the file name is r20. Build didn't pass using r20__  
Rebuild Android packages with OpenSSL 1.1.1c and 1.0.2s.  
Page links to Android/Wasm packages are put into main page instead of the "XXX-series" pages.

## {{% date 2019 7 6 %}}
Windows packages are updated to Qt 5.13.0. __Using SChannel for SSL backend for now instead of OpenSSL!!!__

## {{% date 2019 7 5 %}}
Rebuild Windows packages with OpenSSL 1.1.1c and 1.0.2s.  
Windows packages are updated to Qt 5.12.4.

## {{% date 2019 5 26 %}}
Rebuild VS2017/VS2019 packages with update VS version.

## {{% date 2019 5 19 %}}
Linux hosted Android packages rebuilt with updated configurations.  
Upload Linux hosted WebAssembly package(No 's'...)  
Since SF.net reworked, the files are reuploaded to SF.net.

(Why can't I use SFTP to manage the files on OSDN?????)

## {{% date 2019 5 15 %}}
Windows packages rebuilt with updated configurations.  
Since SF.net can't be accessed using China Telecom in Dalian, China, the files are reuploaded to OSDN.

## {{% date 2019 4 22 %}}
Upload 5.9.8 and 5.12.3 VS2015 packages.

## {{% date 2019 4 20 %}}
Finish 5.9.8 and 5.12.3 series.

## {{% date 2019 4 19 %}}
Removed All old packages.  
Upload new packages built since Mar, 2019.

## Before year 2017 (Black history)

So I did want to write something here, but I don't know how to say.....

### {{% date 2016 7 23 %}}
Upload 5.6.1-1/5.7.0 VS2015 static builds again due to link issue.

From now on, I will not link MySQL/PostgreSQL/ODBC(unix-like only)/OpenSSL in the static packages.  
The configure scripts may be like this:
```
configure xxxxx -static -openssl -qt-sql-sqlite -no-sql-mysql -no-sql-psql -no-sql-odbc(for unix-like)/-qt-sql-odbc(for windows)
```

I'm anti of static builds, see the notes for details.

### {{% date 2016 7 17 %}}
Upload all files to Mega.nz for users who are not in China.

### {{% date 2016 7 16 %}}
Upload 4.8.7 macOS shared packages.  
Upload 4.8.7 Linux shared packages.

### {{% date 2016 7 15 %}}
From now on, I will distribute the config.status(for Unix-like system) or configure.cache(for Windows) in the compressed packages.  
config.status contains all my commands when calling configure, while configure.cache only contains the parameters passed to configure.exe.  
Upload 4.8.7 VS2015 Shared packages. (And are the first and second packages which have configure.cache)  
Update note to suit Qt4.  
Update note about QtBinPatcher.  
Upload 4.8.7 VS2010 Shared packages.  
Update note about old-version Qt.

### {{% date 2016 7 4 %}}
Upload 5.6.1-1 VS2015 Static packages.  
Upload 5.6.1-1 Android(Windows x86_64 host) Shared packages.  
Upload 5.6.1-1 VS2010 Shared packages __just for the unreconstructed people using Windows XP__.  
Update note.

### {{% date 2016 7 3 %}}
Upload 5.6.1-1 VS2015 Shared packages.  
Upload 5.6.1-1 MinGW Shared packages.  
Upload 5.6.1-1 Linux packages.  
Upload 5.6.1-1 macOS packages.  
Removed 5.6.1 packages.  
Upload 5.6.1-1 Android(Linux x86_64 host) Shared packages.  
Upload 5.6.1-1 Android(macOS x86_64 host) Shared packages.

### {{% date 2016 6 29 %}}
Upload 5.7.0 Android(Windows x86_64 host) Shared packages.

### {{% date 2016 6 28 %}}
Upload 5.7.0 Android(Linux x86_64 host) Shared packages.  
Upload 5.7.0 Android(macOS x86_64 host) Shared packages.

### {{% date 2016 6 27 %}}
Update Disclaimer.

### {{% date 2016 6 22 %}}
Upload 5.7.0 VS2015 Static packages.  
Upload 5.7.0 MinGW Shared packages.  
VS2015-clang packages failed to build, thus cannot upload.

### {{% date 2016 6 19 %}}
Upload 5.7.0 VS2015 Shared packages.  
Upload 5.7.0 macOS packages.

### {{% date 2016 6 18 %}}
Upload 5.7.0 Linux packages.  
Removed 5.6.0 packages.  
Upload 5.6.1 VS2015 Static packages.

### {{% date 2016 6 13 %}}
Initial commit, includes builds of Qt 5.6.0, part of 5.6.1 and 5.7.0-RC.
