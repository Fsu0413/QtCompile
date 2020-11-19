# Notes for this repo

## Packaging (Updated 2020.6.4)

I use a set of scripts to do the compilation and packaging.  
If you are interested in compilation method, please check the following GitHub repo.

[GitHub](https://github.com/Fsu0413/Fs-scripts)

However unfortunely, this website is manually edited.  
Source of this site is:

[GitHub](https://github.com/Fsu0413/QtCompile)

## Notes on static builds

I don't use static builds in huge projects. I think it is not wise to use a static build there.

Maybe you just want to distribute a single portable executable binary file, but there is limitations:

* It is not free of charge unless the program itself is a free software under (L)GPLv3.
* A few modules of Qt does not compile. (WebEngine, etc...)
* Cannot use dynamically-linked plugin.
* It is not linked at build time, possibly causing linking problem afterwards.

To be wise and stop using static builds in huge projects. You'll feel liberated to make this change. Trust me.

## Static `Lite` Builds and Static `Full` Builds

Static `lite` builds skipped most of Qt modules, only QtCore, QtDeclarative(QtQml 2), QtXmlPatterns and QtXXXExtras are built.  
It is useful for people who wants to build the QtIFW without building a full static Qt.

Static `full` builds don't skip most of Qt modules, only skip modules which will cause compile failure.

## Notes on users of Qt of old version

I only provide the prebuilt libraries of the latest version of each major release/LTS release, older non-LTS versions will get deleted soon after I release most of the packages of the new version.

I don't know why they don't update to the newest version of Qt of the current branch (e.g, Qt 5.6.1-1, at the time of writing, has released for more than half a month but quite a few users are still using 5.6.0).  

For stability? compatibility? feel lazy for updating? or other reasons?

* Stability  
I think updating to the latest version of the same branch increases stability. Qt only does bug-fixes in minor releases. This is not a problem.
* Compatibility  
Binaries of the same major releases are compatible. It is no need to concern.
* Lazy  
Don't compare laziness with me. I feel lazy for comparing.
* Other reasons  
I have no idea if there is any other reasons.

## Notes on the distributed compressed files (Updated 2020.6.4)

Archive files on Windows host are compressed using 7z in 7z format using LZMA2 Algorithm.  
The command line of generating the compressed file is like:
```
7z a -t7z -m0=LZMA2:d256m:fb273 -mmt=3 -myx -mqs -ms=on -- xxx.7z xxx
```

Archive files on Linux use GNU tar. Archive files on macOS use bsdtar.  
In addition, we use 7z for the xz compression.  
The command line of generating the compressed file is like:
```
tar -cf - xxx | 7zr a -txz -m0=LZMA2:d256m:fb273 -mmt=3 -myx -si -- xxx.tar.xz
```

Make sure your uncompresser supports LZMA2 algorithm. For example:  
7z users should upgrade your 7z to 9.20 or later.  
WinRAR users should upgrade your WinRAR to 4.00 or later.  
Other decompresser users should query for their latest version, since it may support LZMA2 algorithm.

I just noticed that Arch Linux and MSYS2 switched to zst for their package manager.  
Only recent GNU tar (1.31 or later) and recent libarchive (a.k.a. bsdtar, 3.3.3 or later) directly supports .tar.zst compress method.  
I will not use zst because the compress ratio is not as good as LZMA2(xz).

## Difference of this Qt and offically distributed Qt (Updated 2020.6.7)

I provide only binary tarball, which contains only built Qt binary for each OS.  
It should work out of box (for Qt 5.14 or later) or work after patches to Qt (for Qt 5.13 and before).  
I will never use online installers.

There is **NO NEED TO LOGIN Qt ACCOUNT**!!! By doing this gets rid of the nonsense of "This can help optimize Qt".

All Qt builds here have been configured with -no-icu, because I thought that the ICU is useless for common users, and it is rather a big thing.  

Using linked OpenSSL support for packages which can't use platform native way for creating SSL sockets.
Windows builds before and including Qt 5.12 are using linked OpenSSL to dynamic(shared) libraries, Android builds are using statically linked OpenSSL.  
macOS builds are using SecureTransport instead of OpenSSL.  
Windows builds after and including Qt 5.13 are using SChannel instead of OpenSSL.

No debug libs, which cuts more than a half of the size of the whole Qt package.

No examples, which cuts more than a half of the size of the whole Qt package.

No docs (and no QDoc for Qt 5.12 and later since it depends on Clang), since Qt docs can be read from http://doc.qt.io, it is no need to bondle doc to the package.

## Notes for Qt versions before 5.14

Qt should complain about the binary files which were just uncompressed from the tarball.  
It should say "Qt is not properly installed, please run _make install_" or something like this in Qt creator.

I redistributed a version of QQtPatcher, you should run it to make Qt running.

The source code of the distributed QQtPatcher is on [Github](https://github.com/Fsu0413/QQtPatcher). It is a free software and distributed in public domain.

Do not put the library in a directory which contains non-ascii character or spaces.   
Bug will cause that the path of qmake cannot be properly parsed by Qt Creator.

## Qt offering changes 2020

Qt just announced [Qt offering changes 2020](https://www.qt.io/blog/qt-offering-changes-2020).  
Following is my opinion of this blog.

First of all, I have a Qt account, but I don’t understand why I need a Qt account to install the Qt development kit.  
All files are compiled and linked from the same set of source code. It will not change even if you log in to your Qt account. It will not add any features to Qt. "This can help optimize Qt" is simply nonsense.

LTS is only available for commercial license. So what is the license for the LTS source package?  
If it is also only available for commercial licenses, Qt basically says goodbye to stable open source software.  
Besides, their LTS support time is not too long. Windows has 10 years of support time, CentOS has 10 years of support time, and Qt has only 3 years...

The offline installation package is only available for commercial licenses, which means that peoples in China can only find the time (usually before 8 am) when the network is available to install the Qt open source version with the online installation package.

What kind of company is a small company?  
Founding a shell company and using this company to buy Qt and distribute software, for only $499 per year? While other employees who work together use the open source version in private?  
This will definitely lose money.

I will continue my amateur job of compiling Qt. I hope Qt for MCUs will be open source soon.
