{
  "title": "Fsu0413's Original Qt builds",
  "archetype": "home"
}

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

## `xz` backdoor

Just saw surprisingly that `xz` have been backdoored upstream by a trusted maintainer.   
All investigation result shows that a user called JiaT75 is the bad guy, and this backdoor is revealed to be working only on x86_64 systemd-based Linux distributions, and is used for injecting OpenSSH for estabilishing unauthorized connections. It is not for manipulating files during {,de}compression.

XZ packages built by this project are **NOT** compressed using the original `xz` tool. They are using `7z` from Igor Pavlov on Windows / `p7zip` from jinfeihan57 on non-Windows.  
But when building other packages `tar -xJf xxx.tar.xz` is still called for decompressing packages of dependencies like OpenSSL, MariaDB and host Qt static `Lite` packages. This step still invokes the `xz` program.  
It is shown that 

All Linux build machine we are using are Rocky Linux which derives from RHEL. It does not upgrade software on major version just like RHEL, so we may be unaffected.   
But `libarchive` (which macOS and Windows is using. `bsdtar` is from this library) also contains code authored by the bad guy. `libarchive` have already started re-reviewing the code the bad guy authored.

This banner will be put here until the result gets clear. I will continuously pay attention to related news, and will do repacking of all released packages if necessary.

More details can be found in Lasse Collin (Initial maintainer of `xz`)'s [post](https://tukaani.org/xz-backdoor/) on the official website of `xz`.

## Disclaimer

These binaries built by Fsu0413 are __TOTALLY UNTESTED__. Use at your own risk.  
The code used is downloaded from [here](http://download.qt.io), and patches applied on top of code are [listed here](/Miscellaneous/NotesForThisRepo#existing-patches) only for dealing with some simple and minor compile / build fixes.  
__THESE PACKAGE ARE PROVIDED "As is", I have no responsibility that you mess up your things with this binaries.__  
Thanks for The Qt Company Ltd. and the programmers of Qt for their fantastic work!!

## Update History

### {{% date 2024 4 3 %}}
Update Qt 6.7.0 versions.

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

### Before {{% date 2024 3 23 %}}

[Here](/Miscellaneous/Histories)
