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
The code used is downloaded from [here](http://download.qt.io), I made no changes to the source/generated files, except for officially announced patches.  
__THESE PACKAGE ARE PROVIDED "As is", I have no responsibility that you mess up your things with this binaries.__  
Thanks for The Qt Company Ltd. and the programmers of Qt for their fantastic work!!

## Update History

### {{% date 2024 2 7 %}}
Update Qt 5.15 & 6.2.7 & 6.5.3 Android version with updated API level.  
Update OpenSSL to 3.0.13.

### {{% date 2023 12 25 %}}
Update Qt 5.15.12 & 6.2.7 with existing patches.   
Apply patches of CVE-2023-51714 which is not yet announced by tQtC for all LTS Qt versions.

Merry Christmas!

### {{% date 2023 12 4 %}}
Update Qt 6.6.1.   
Rebuild Qt 6.5.3 with patch CVE-2023-43114.   
Update OpenSSL 3.0.12. Rebuild all packages which use OpenSSL, including Qt 5.15 Android and Qt 6.2 non-WebAssembly.   
Update MariaDB Connector C to 3.3.8 / 3.1.23.

### Before Nov. 2023

[Here]({{% relref "miscellaneous/histories" %}})
