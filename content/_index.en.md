---
title: "Fsu0413\'s Original Qt builds"
draft: false
---

# Fsu0413's Original Qt builds

## Website Mirror

Recently I created a mirror of this website in the Greatest China, using service of Gitee Pages.  
This mirror is configured to be displaying Simplified Chinese by default.

Due to the customize domain name function is only available under purchaged service of Gitee, Chinese mirror has to be under the domain of Gitee for now.  
I may purchage the service later when the service seems good enough for me.

[Github Pages (America, with English as default language)](https://build-qt.fsu0413.me/)  
[Gitee Pages (The Greatest China, with Chinese-S as default language)](https://fsu0413.gitee.io/qtcompile/)

## Disclaimer

These binaries built by Fsu0413 are __TOTALLY UNTESTED__. Use at your own risk.  
The code used is downloaded from [here](http://download.qt.io), I made no changes to the source/generated files, except for officially announced patches.  
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

### 2023.1.23
Update Qt 6.5.0-beta1 packages (without QtOpcUa)  
Update Qt 6.2.4 / Qt 6.4.2 with static `libgcc` on Windows. Previous version relies on the `libgcc` DLL. Affected versions are all cross built version and the static `full` builds.

### 2023.1.8
Update Qt 6.4.2 / Qt 5.15.8 packages.  
Update Qt 6.2.4 packages built with OpenSSL 3.0.7 with [the minor fix](https://www.openssl.org/news/secadv/20221213.txt).

Qt 6 Linux hosted cross built packages has a problem where the host tool was not properly deployed.  
This time the package is rebuilt with fix.

### Before Nov. 2022

[Here]({{% relref "miscellaneous/histories" %}})
