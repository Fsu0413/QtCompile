---
title: "Fsu0413\'s Original Qt builds"
draft: false
archetype: "home"
---

{{% notice style="info" title="Note"  icon="fas fa-info-circle" %}}
Currently there is technical problem on OSDN. Download / Upload are having problems.  
All links to OSDN are removed for now. Please download from SourceForge.

Error during upload is as following (Output by WinSCP).

{{% expand %}}
General failure (server should provide error description).  
Error code: 4  
Error message from server: Failure

Common reasons for the Error code 4 are:
- Renaming a file to a name of already existing file.
- Creating a directory that already exists.
- Moving a remote file to a different filesystem (HDD).
- Uploading a file to a full filesystem (HDD).
- Exceeding a user disk quota.
{{% /expand %}}
{{% /notice %}}

## Disclaimer

These binaries built by Fsu0413 are __TOTALLY UNTESTED__. Use at your own risk.  
The code used is downloaded from [here](http://download.qt.io), and patches applied on top of code are [listed here](/Miscellaneous/NotesForThisRepo#existing-patches) only for dealing with some simple and minor compile / build fixes.  
__THESE PACKAGE ARE PROVIDED "As is", I have no responsibility that you mess up your things with this binaries.__  
Thanks for The Qt Company Ltd. and the programmers of Qt for their fantastic work!!

## Update History

### {{% date 2024 3 28 %}}
Update Qt 6.6.3 and Qt 6.7.0-rc2 versions.   
Rebuild VS2022 and llvm-mingw 18 builds for Qt 5.15 / 6.2 / 6.5.

Qt 6 is migrating MinGW builds from GCC based toolchain to LLVM based one, using [llvm-mingw](https://github.com/mstorsjo/llvm-mingw).   
I also suggest migrating since LLVM has faster build speed and produces smaller binaries, as well as supporting Windows on ARM (although I have not investigated about using llvm-mingw on WoA yet).  
See {{% QtBug 107516 %}} for details.

### {{% date 2024 3 25 %}} no update
Add note about build failure about MySQL backend for Qt 5.15.  
Simply investigate llvm build on Windows.

Happy birthday to Iroi Imagay (the third time)!

### {{% date 2024 3 23 %}}
Add Qt 5.15 series for Windows on ARM64.  

### Before {{% date 2024 3 18 %}}

[Here](/Miscellaneous/Histories)
