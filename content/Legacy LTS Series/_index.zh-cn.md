---
title: "遗留的长期支持版本系列"
draft: false
weight: 9999
---

## 不再维护

这些版本不再维护，也不会再收到更新。  
这些仅作为参考而提供。  
我不推荐大家用这些版本的 Qt。

## 对于 Qt 5.14 以前的备注

Qt 5.14 以前的版本拒绝使用刚刚从包中解压出来的二进制文件。  
它会在 Qt Creator 里报告类似“Qt 未正确安装，请运行 ```make install``` ”这样的内容。

我在压缩包里附带了一个 QQtPatcher。解压后需要运行 QQtPatcher 一次来让 Qt 工作。

这个 QQtPatcher 的源码在 [GitHub](https://github.com/Fsu0413/QQtPatcher) 上。这是一个在共有领域发布的自由软件。

不要把这个库放在有空格或者非 ASCII 字符的路径下。  
由于 Bug 导致 qmake 的路径不能被 Qt Creator 成功解析。

{{% children sort="weight" depth=999 %}}
