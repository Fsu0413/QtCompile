{
  "title": "Fsu0413's Original Qt builds",
  "archetype": "home",
  "description": "Personal build of Qt4 onwards, with SSL builtin. Multiple configuration available."
}

## Disclaimer

These binaries built by Fsu0413 are __TOTALLY UNTESTED__. Use at your own risk.  
The code used is downloaded from [here](http://download.qt.io), and patches applied on top of code are [listed here](/Miscellaneous/NotesForThisRepo#existing-patches) only for dealing with some simple and minor compile / build fixes.  
__THESE PACKAGE ARE PROVIDED "As is", I have no responsibility that you mess up your things with this binaries.__  
Thanks for The Qt Company Ltd. and the programmers of Qt for their fantastic work!!

## Update History

### {{% date 2024 6 9 %}}
Update OpenSSL to 3.0.13.  
Rebuild versions built by llvm-mingw 18 series toolchain, using llvm-mingw 18.1.7.  
Update Visual Studio 2022 to 17.10.1.

### {{% date 2024 5 28 %}}
Update Qt 5.15.14 / 6.7.1.  
Apply patches for CVE-2024-36048 for all supported versions, all packages are rebuilt.  
Rebuild versions built by llvm-mingw 18 series toolchain, using llvm-mingw 18.1.6.

Update macOS (arm64) to 14.5 and update Xcode to version with AppleClang 15.0.0.

I'm starting gradually ending support for QtWebEngine on Qt 6.5 series, as been done in 6.2 series before.  
Currently build doesn't pass on macOS platform and it is disabled and won't be enabled on macOS for 6.5 series again.  
If Qt 6.5 QtWebEngine build failed on MSVC series I'll just disable it.

### {{% date 2024 5 12 %}}
Rebuild all Qt 6 static builds. Remove OpenSSL builtin from these versions.  
Reason is that it is [Repo](https://github.com/Fsu0413/QtCompile/issues/25)[rted](https://github.com/Fsu0413/QtCompile/issues/22) that Qt won't be working without OpenSSL header file.

Rebuild versions (except for Qt 6.7) built by llvm-mingw 18 series toolchain, using llvm-mingw 18.1.5.

Rebuild Qt 5.15 MinGW (GCC 11.2.0 and later, LLVM all) versions, fixed a problem which causes that the MySQL (MariaDB) plugin wasn't built.

### Before {{% date 2024 4 19 %}}

[Here](/Miscellaneous/Histories)
