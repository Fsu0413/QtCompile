---
title: "Fsu0413\'s Original Qt builds"
draft: false
---

# Fsu0413's Original Qt builds

## STOP USING Notepad++

At {{% date 2023 1 25 %}} Notepad++ released a version with a "feature" where users must agree the fake, incorrect and misleading politics words about China.   
If user doesn't agree random character is added when editing using Notepad++.

(Following statements are in Chinese only because I actually don't know how to say it in English)  
作为中国人，我在此声明：  
**中国的各个省、直辖市、自治区和特别行政区，包括港澳台、新疆和西藏，都是中国领土的一部分。**   
**我拒绝接受一切不尊重中国国家主权及领土完整的言论。**

I, Fsu0413, as a Chinese source code peasant in China, won't use Notepad++ anymore and won't support Notepad++ users.  
I also appeals to all users of my websites to STOP USING Notepad++ and find an alternative.

I won't provide any recommendation for alternative.  
There are [tons of Scintilla-based editor in the wild](https://www.texteditors.org/cgi-bin/wiki.pl?ScintillaEditorFamily) and I do believe you'll find the one you like.

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

### {{% date 2023 5 22 %}}
Apply patch for CVE-2023-32762 and CVE-2023-32763 in all supported 5.15.9 and 6.2.4 versions.  
Apply patch in 5.15.9 macOS version for mapbox-gl-native build issue.

### {{% date 2023 5 20 %}}
Update macOS to 13.3.1. Update Xcode to 14.3.  
Update Qt 5.15.9 Universal host builds and arm64 hosted cross builds.  
Update MinGW-w64 with GCC UCRT builds of Qt 6.2.4 and Qt 6.5.0.

Apply patch for CVE-2023-32573 in all supported 5.15.9 and 6.2.4 versions.

### {{% date 2023 5 11 %}}
Use OSDN project instead of Chamber (a.k.a. PersonalForge) for file hosting.

### {{% date 2023 5 9 %}}
Update Qt 5.15.9 / 6.5.0.  
Remove Qt 6.4 series.

On {{% date 2023 4 20 %}} OpenSSL released [a minor fix](https://www.openssl.org/news/secadv/20230420.txt) which applies for ARM built OpenSSL binary.  
I distributes only non-ASM build of OpenSSL so it is not affected to my builds. This update will not integrated to my builds.

### Before Jan. 2023

[Here]({{% relref "miscellaneous/histories" %}})
