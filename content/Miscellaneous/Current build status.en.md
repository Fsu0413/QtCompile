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

## MariaDB Status

I'll ship MariaDB connector/C dynamic library for Qt 5.15 and later version since {{% date 2023 2 8 %}}.  
This is used to build MySQL database backend.  
I have following reason for not using MySQL libraries.

1. MariaDB is the "original" MySQL per se.
1. Using later MySQL (8.0 series and later) need downloading and building a full MySQL database. But the MySQL database is bulky and hard to be built.
1. MySQL is from Oracle who had history of hitting open source community.

MariaDB connector/C 3.1 series are used on Qt 5.15.  
MariaDB connector/C 3.3 series are used on Qt 6.2 and later.

{{% mariaDBSeries %}}

## Qt Build Table

**Note: Since Qt dropped support for 32-bit Windows for Qt 6, our Qt 6 builds will no longer run for 32-bit Windows either.**  
**If there is need of static builds for non-LTS release, please contect me directly for commerical customization.**

{{% QtTable %}}