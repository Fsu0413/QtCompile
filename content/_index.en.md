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

## Disclaimer

These binaries built by Fsu0413 are __TOTALLY UNTESTED__. Use at your own risk.  
The code used is downloaded from [here](http://download.qt.io), and patches applied on top of code are [listed here](/Miscellaneous/NotesForThisRepo#existing-patches) only for dealing with some simple and minor compile / build fixes.  
__THESE PACKAGE ARE PROVIDED "As is", I have no responsibility that you mess up your things with this binaries.__  
Thanks for The Qt Company Ltd. and the programmers of Qt for their fantastic work!!

## Update History

### {{% date 2024 4 13 %}}
Rebuild versions built by NDK r26 series toolchain, using NDK r26d.

Happy birthday to me (the 32nd time)!

### {{% date 2024 4 6 %}}
Rebuild versions built by llvm-mingw 18 series toolchain, using llvm-mingw 18.1.3.

### {{% date 2024 4 3 %}}
Update Qt 6.7.0 versions.

### Before Apr. 2024

[Here](/Miscellaneous/Histories)
