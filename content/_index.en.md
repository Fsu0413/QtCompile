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

## Notes for this repo

[Here]({{% relref "miscellaneous/notes for this repo" %}})

## Current build status

[Here]({{% relref "miscellaneous/current build status" %}})

## Downloads

Please refer to the content lists in the left area.

## Current failures

[Here]({{% relref "miscellaneous/current failures" %}})

## Update History

### {{% date 2023 10 8 %}}
Update Qt 5.15.11 / 6.2.6 / 6.5.3 with OpenSSL 1.1.1w / 3.0.11.  
Apply patch for CVE-2023-4863 in all supported 5.15.11 versions. (Conflict on Qt 6.2.6)  
Apply patch for CVE-2023-43114 in all supported 5.15.11 and 6.2.6 versions.   
Update MariaDB Connector C to 3.3.7 / 3.1.22.

### {{% date 2023 10 6 %}}
Update Qt 5.12.12 with OpenSSL 1.1.1w.

Since OpenSSL 1.1.1 series has reached EOL, there will be no further Qt 5.12 builds.  
i.e., this build is the last build of these packages.  
The build script and environment of Qt 5.12 series has been destructed.

### {{% date 2023 8 5 %}}
Update Qt 5.12.12.  
Update Qt 5.15.10. Apply patch of CVE-2023-37369 and CVE-2023-38197.  
Update Qt 6.2.5.  
Update Qt 6.5.2.

Update OpenSSL to 3.0.10 / 1.1.1v.

OSDN service is temporarily stopping from being used due to technical problem. Currently prebuilt packages are only uploaded to SourceForge.

### Before Jul. 2023

[Here]({{% relref "miscellaneous/histories" %}})
