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

### {{% date 2024 4 19 %}}
Update Qt 6.2.8.  
Rebuild versions built by llvm-mingw 18 series toolchain, using llvm-mingw 18.1.4.

Remove "Qt 6 support platforms" section from notes since there is nothing we are planning for Qt 6 build right now.  
Initial version of Qt 6.0 has released for more than 3 years, and all targets planned for build has achieved. This section have no future use.

### {{% date 2024 4 17 %}}
Add builds of Qt 6.5 and 6.7, using VS2019.  
Rebuild Qt 5.15 / 6.5 / 6.7 using updated VS2017 15.9.61 / VS2019 16.11.35 / VS2022 17.9.6. (except for static builds)

### Before {{% date 2024 4 13 %}}

[Here](/Miscellaneous/Histories)
