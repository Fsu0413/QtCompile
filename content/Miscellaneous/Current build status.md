---
title: "Current build status"
draft: false
weight: 2
---

## QQtPatcher Support Status

This is a list where QQtPatcher is supported and tested on.  
Other version may work, but also may silently fail.

A valid qbp.json is needed for patching Qt 4 Series since `qmake -query` don't output the makespec.

Qt 5.14 is relocatable as announced in [New Features in Qt 5.14](https://wiki.qt.io/New_Features_in_Qt_5.14), so Qt after 5.14 won't need QQtPatcher anymore.  
I delivered QQtPatcher for earlier version of 5.14 (because of the fact that I forgot to modify QQtPatcher related code in build scripts).  
This tool won't be thoroughly tested on 5.13.  
I announced that QQtPatcher will not support Qt 5 after 5.14.

{{% QQtPatcherTable %}}

Build Hosts:

{{% QQtPatcherHosts %}}

## OpenSSL Status

My Qt builds is with linked OpenSSL support for most platforms.  
Here is a list of OpenSSL builds of mine.

Note:   
OpenSSL 1.1.1 series on Windows is only for Qt 5.12 series. For Qt 5 after 5.13 we are using SChannel.  
MinGW builds is `-shared-and-static` so no need to build a seprate static version.

OpenSSL 3 series is used on Qt 6 after 6.2.3.  
Since Qt 6.2 changes tls backend to plugin, one can use more than one tls backend when building.  
On Windows we are using OpenSSL alongwith SChannel, while on macOS we are using OpenSSL alongwith SecureTransport.

{{% OpenSSLSeries %}}

## Qt 5.12 Series (Previous LTS release, EOLed by Qt)

{{% QtTable "5.12.12" %}}

## Qt 5.15 Series (Previous LTS release)

{{% QtTable "5.15.6" %}}

## Qt 6.2 Series (Curent LTS release for commerical version only)

**Note: Since Qt dropped support for 32-bit Windows, our Qt 6 builds will drop support for 32-bit Windows either.**

{{% QtTable "6.2.4" %}}

## Qt 6.4 Series (Curent mainline release)

**Note: Since Qt dropped support for 32-bit Windows, our Qt 6 builds will drop support for 32-bit Windows either.**  
**If there is need of static builds for non-LTS release, please contect me directly for commerical customization.**

{{% QtTable "6.4.0" %}}
