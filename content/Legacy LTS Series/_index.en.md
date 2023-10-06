---
title: "Legacy LTS Series"
draft: false
weight: 9999
---

## Not maintained

These versions are not maintained and will not update anymore.  
They are provided only for reference.  
I don't recommend you use these versions of Qt.

## Notes for Qt versions before 5.14

Qt before 5.14 should reject using the binary files which were just uncompressed from the tarball.  
It should report "Qt is not properly installed, please run ```make install```" or something like this in Qt creator.

I redistributed a version of QQtPatcher in the package, you should run it to make Qt running.

The source code of the distributed QQtPatcher is on [GitHub](https://github.com/Fsu0413/QQtPatcher). It is a free software and distributed in public domain.

Do not put the library in a directory which contains non-ascii character or spaces.   
Bug will cause that the path of qmake cannot be properly parsed by Qt Creator.

{{% children sort="weight" depth=999 %}}
