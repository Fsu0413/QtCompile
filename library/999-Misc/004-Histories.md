# Previous Histories

## 2021.1.3
Upload 6.0.0 Android builds (Linux host).  
<font color=red><b>ANDROID BUILDS ARE WITHOUT LINKED OpenSSL SUPPORT due to compile error!!!!!!!!</b></font>

## 2021.1.2
Upload 6.0.0 Android builds (macOS host).  
Rebuild 6.0.0 Windows and macOS builds with stripped binary.  
Note that Android API Level has changed to android-24 since Qt 6.0.0.  
<font color=red><b>ANDROID BUILDS ARE WITHOUT LINKED OpenSSL SUPPORT due to compile error!!!!!!!!</b></font>

## 2020.12.20
Upload 6.0.0 Windows and macOS builds.

## 2020.12.17
Upload 5.15.2 builds. (All builds are without Webengine because of compile failure<del>, see [Current Failures](?file=999-Misc/003-Current%20failures)</del>(resolved and removed from this page))  
Update macOS to 11.0.1.  
VS2019 is updated to the latest version, which is 16.8.3.  
VS2017 is updated to the latest version, which is 15.9.30.

## 2020.11.11
Upload 5.12.10 builds.  
macOS is updated to 10.15.7 and XCode is updated to 12.0.  
VS2019 is updated to the latest version, which is 16.7.7.

## 2020.9.12
Upload 5.15.1 builds.  
macOS is updated to 10.15.6 (19G2021)  
VS2017/2019 are updated to the latest version, which is 15.9.27/16.7.3.

## 2020.7.7
Upload all artifacts, also to Github release in addition to SourceForge.

## 2020.6.19
Upload Android NDK to r21d.  
Rebuilt all android packages using new NDK.

## 2020.6.18
Upload 5.12.9 builds.

## 2020.6.4
Upload 5.15.0 macOS host builds. (macOS host builds of 5.12.8 have compile failure, we should wait for 5.12.9)   
Upload 5.15.0 Android builds. (macOS 10.15.5 hosted)

## 2020.6.3
Add proprietary codecs support for Qt WebEngine for Qt 5.12.9 and 5.15.0 or later.  
Upload 5.15.0 series. (**Except macOS host builds, which encountered some issue while compiling**)  
Use MinGW-w64 to 8.1.0 for Qt 5.15.0 series, switch the build environment of MinGW 8.1.0 to Win10.  
Upload 5.9.9 VS2017 builds for newer VS2017 compiler.  
Upload 5.12.8 WebAssembly builds for newer emsdk definition.  
Upload 5.12.8 Android builds for NDK r21b.  
Remove 5.14 series except macOS ones. (macOS ones will be deleted once 5.15 finishes compiling)

Since Qt 5.9 series has reached EOL, there will be no further Qt 5.9 builds.  
i.e., this build is the last build of these packages.  
The build script and environment of Qt 5.9 series has been destructed.

## 2020.5.18
Upload 5.15.0-rc2 series. (**All macOS version, including cross builds, are not uploaded because of broken environment**)  
Update Win10 to 10.0.19041(2004)

## 2020.4.25
Upload 5.15.0-beta4 series. (**All macOS version, including cross builds, are not uploaded because of broken environment**)

## 2020.4.12
Upload 5.15.0-beta3 series. (**All macOS version, including cross builds, are not uploaded because of broken environment**)

## 2020.4.11
Upload 5.12.8 series. (**All macOS version, including cross builds, are not uploaded because of broken environment**)

## 2020.4.3
Upload 5.14.2 series. (macOS versions are not provided due to QtWebEngine compile failure, __HOST ONLY__)

## 2020.3.26
Upload 5.15.0-beta2 series. (Static `full` version don't compile)  
Mirror this site on Coding.net for faster browsing in China.

## 2020.3.6
Upload 5.12.7 Android series with NDK r21.  
Upload 5.15.0-beta1 series. (VS2017 and VS2019 shared builds are not provided due to QtWebEngine compile failure)

## 2020.2.6
Upload Windows on ARM64 cross build. (for now it only supports Qt 5.12 and later using VS2017.)

## 2020.2.5
Upload Qt 5.12.7 Series. (Qt 5.12.7 actually released on 31st, Jan., but I didn't mention it....)  
Note: QQtPatcher has got an update (to 0.7.0) after the build completed.  
Since most of the modifications affects Windows builds, I only manually recompressed Windows packages.  
Other packages are not recompressed.

## 2020.2.3
Add new configurations of static `full` packages of MinGW builds of Qt 5.12 Series.  
Upload Qt 5.12.6 MinGW static `full` builds.

## 2020.2.2
Rebuild Qt 5.12.6 VS2017 & VS2019 versions using newer VS.

## 2020.2.1
I have switched to CentOS 8 for both Android builds and WebAssembly builds.  
For now only 5.14 series is built successfully and uploaded.  
CentOS 7 and Ubuntu 16.04 environment has been destructed.

Upload Qt 5.14.1 Series.  
Rebuild all Linux hosted Android builds and WebAssembly builds, using CentOS 8.  
Since there is no host tools in OpenSSL packages, most of the OpenSSL packages are not rebuilt.

## 2020.1.16
Recompress the Qt 5.6 static `full` packages due to a script bug which causes the missing of OpenSSL libraries.  
Note that the packages are not rebuilt.  
(Qt 5.12 packages will update later when OpenSSL 1.1 series or Qt 5.12 series updates)

## 2020.1.5
Packages using OpenSSL 1.0.2 Series rebuilt using OpenSSL 1.0.2u.  
Including all Qt 4 packages and non-macOS Qt 5.6/5.9 packages.

Since OpenSSL 1.0.2 Series has reached EOL, there will be no further Qt 4 and Qt 5.6 builds.  
i.e., this build is the last build of these packages.  
The build script and environment of Qt 4 and 5.6 series has been destructed.

## 2019.12.26
Windows 8.1 Update build environment has been finished, and Windows Server 2008 R2 build environment has been destructed.  
Upload all packages which build on Windows 8.1.

## 2019.12.22
Upload 5.9.9 and 5.14.0 packages.  
(Qt 5.14.0 packages for android is missing due to an error during configure)

## 2019.12.5
Upload all macOS packages.

## 2019.12.2
Uploaded all rebuilt packages after my business trip.

## 2019.11.22
Update pending after I return to China.....  
Qt 5.12 Series => 5.12.6  
Qt 5.13 Series => 5.13.2 -> prepare to migrate to Qt 5.14 Series  
OpenSSL 1.0.2 Series => OpenSSL 1.0.2t (affects Qt 4.8/5.6/5.9 Series)  
OpenSSL 1.1.1 Series => OpenSSL 1.1.1d (affects Qt 5.12/5.13 Series)  
VS2017 => 15.9.17  
VS2019 => 16.3.10  
Android NDK => r20b

OS update pending.....  
Win10 => 10.0.18363  
CentOS 7 => 7.7.1908 (Should there be a CentOS 8 environment? Currently Ubuntu 16.04 LTS is used to build the WebAssembly packages. If we change to CentOS 8 then it will become based on newer software)  
macOS 10.14 => 10.15

There will be no further build of original Qt 4.8/5.6 after OpenSSL 1.0.2 Series gets EOL (will be at 2019.12.31)  
There will be no further build of original Qt 5.9 after Qt 5.9 Series gets EOL (will be at 2020.5.31)  
There will be no build on Windows 7 (Server 2008 R2) after Windows 7 gets EOL (will be at 2020.1.11), existing Windows 7 builds will migrate to Windows 8.1 (Server 2012 R2)

## 2019.8.26
A bug about packaging has been revealed. It affects all versions of Qt 5.12 or later.  
The package of 5.12.5 will fix this issue.

## 2019.8.3
Re-create this site using amWiki.  
Since there is a builtin content list when using amWiki, it no longer needs to write the downloadable content list manually by now.

## 2019.7.13
Rebuild __ALL__ packages using updated QQtPatcher due to a bug in QQtPatcher.  
VS2017 is updated to 15.9.14.  
VS2019 is updated to 16.1.6.

## 2019.7.9
WebAssembly packages are updated to Qt 5.12.4 and Qt 5.13.0.

## 2019.7.8
Android packages are updated to Qt 5.12.4 and Qt 5.13.0. <font color=red>__Used NDK r19c, although the file name is r20__</font>  
Rebuild Android packages with OpenSSL 1.1.1c and 1.0.2s.  
Page links to Android/Wasm packages are put into main page instead of the "XXX-series" pages.

## 2019.7.6
Windows packages are updated to Qt 5.13.0.

## 2019.7.5
Rebuild Windows packages with OpenSSL 1.1.1c and 1.0.2s.  
Windows packages are updated to Qt 5.12.4.

## 2019.5.26
Rebuild VS2017/VS2019 packages with update VS version.

## 2019.5.19
Linux hosted Android packages rebuilt with updated configurations.  
Upload Linux hosted WebAssembly package(No 's'...)  
Since SF.net reworked, the files are reuploaded to SF.net.

(Why can't I use SFTP to manage the files on OSDN?????)

## 2019.5.15
Windows packages rebuilt with updated configurations.  
Since SF.net can't be accessed using China Telecom in Dalian, China, the files are reuploaded to OSDN.

## 2019.4.22
Upload 5.9.8 and 5.12.3 VS2015 packages.

## 2019.4.20
Finish 5.9.8 and 5.12.3 series.

## 2019.4.19
Removed All old packages.  
Upload new packages built since Mar., 2019.

## Before 2017 (Black history)

So I did want to write something here, but I don't know how to say.....

### 2016.7.23
Upload 5.6.1-1/5.7.0 VS2015 static builds again due to link issue.

From now on, I will not link MySQL/PostgreSQL/ODBC(unix-like only)/OpenSSL in the static packages.  
The configure scripts may be like this:
```
configure xxxxx -static -openssl -qt-sql-sqlite -no-sql-mysql -no-sql-psql -no-sql-odbc(for unix-like)/-qt-sql-odbc(for windows)
```

I'm anti of static builds, see the notes for details.

### 2016.7.17
Upload all files to Mega.nz for users who are not in China.

### 2016.7.16
Upload 4.8.7 macOS shared packages.  
Upload 4.8.7 Linux shared packages.

### 2016.7.15
From now on, I will distribute the config.status(for Unix-like system) or configure.cache(for Windows) in the compressed packages.  
config.status contains all my commands when calling configure, while configure.cache only contains the parameters passed to configure.exe.  
Upload 4.8.7 VS2015 Shared packages. (And are the first and second packages which have configure.cache)  
Update note to suit Qt4.  
Update note about QtBinPatcher.  
Upload 4.8.7 VS2010 Shared packages.  
Update note about old-version Qt.

### 2016.7.4
Upload 5.6.1-1 VS2015 Static packages.  
Upload 5.6.1-1 Android(Windows x86_64 host) Shared packages.  
Upload 5.6.1-1 VS2010 Shared packages __just for the unreconstructed people using Windows XP__.  
Update note.

### 2016.7.3
Upload 5.6.1-1 VS2015 Shared packages.  
Upload 5.6.1-1 MinGW Shared packages.  
Upload 5.6.1-1 Linux packages.  
Upload 5.6.1-1 macOS packages.  
Removed 5.6.1 packages.  
Upload 5.6.1-1 Android(Linux x86_64 host) Shared packages.  
Upload 5.6.1-1 Android(macOS x86_64 host) Shared packages.

### 2016.6.29
Upload 5.7.0 Android(Windows x86_64 host) Shared packages.

### 2016.6.28
Upload 5.7.0 Android(Linux x86_64 host) Shared packages.  
Upload 5.7.0 Android(macOS x86_64 host) Shared packages.

### 2016.6.27
Update Disclaimer.

### 2016.6.22
Upload 5.7.0 VS2015 Static packages.  
Upload 5.7.0 MinGW Shared packages.  
VS2015-clang packages failed to build, thus cannot upload.

### 2016.6.19
Upload 5.7.0 VS2015 Shared packages.  
Upload 5.7.0 macOS packages.

### 2016.6.18
Upload 5.7.0 Linux packages.  
Removed 5.6.0 packages.  
Upload 5.6.1 VS2015 Static packages.

### 2016.6.13
Initial commit, includes builds of Qt 5.6.0, part of 5.6.1 and 5.7.0-RC.
