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

### {{% date 2024 3 16 %}}
Update Visual Studio 2022 to 17.9.3, rebuild all VS2022 packages (except for static one)    
Build Qt 5.15 with [llvm-mingw](https://github.com/mstorsjo/llvm-mingw), now with Clang version 16, 17 and 18 series.  
Upload builds of Qt 6.2 / 6.5 / 6.6 with llvm-mingw 18 series.    
Build Qt 6.2 with Android NDK r25c.    
Build Qt 6.2 and 6.5 with MinGW w/ GCC 13 series.

Got a cold, ke ke ke....

### {{% date 2024 3 12 %}}
Update Qt 5.15.13.  
Update Visual Studio 2022 to 17.9.2.

Patch Qt 5.15 series to be built with newer MinGW-w64 and Android NDK versions.

### Before Jan. 2024

[Here](/Miscellaneous/Histories)
