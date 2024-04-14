{
  "title": "当前构建状态",
  "weight": 2,
  "isMaxWidthPreferred": true
}

## OpenSSL 状态

我的 Qt 构建在大部分平台上附带链接的 OpenSSL。（目前只）使用 LTS 版本的 OpenSSL。  
下面是我构建 OpenSSL 的列表。

OpenSSL 3 系列在 6.2.3 以及更新的 Qt 6 版本和于 {{% date 2023 9 11 %}}后构建的 Qt 5.15 版本上使用。  
自从 Qt 6.2 将 tls 后端换成了插件，我们可以用多于一个的后端来构建。  
在 Windows 上我们使用 OpenSSL 和 SChannel，而在 macOS 上我们使用 OpenSSL 和 SecureTransport。

{{% notice style="info" title="备注"  icon="fas fa-info-circle" %}}
虽然我同时还在维护 [openssl-externalCMake](https://github.com/Fsu0413/openssl-externalCMake) 我并未使用该项目构建 OpenSSL。  
那个项目构建出来的 OpenSSL 还没有通过测试用例。  
所以现在的所有构建还是使用原来的基于 Perl 的构建方法。
{{% /notice %}}

{{% OpenSSLSeries %}}

| Qt 版本 | 使用的 OpenSSL 版本 |
|-|-|
| Qt 4.8 系列 | OpenSSL 1.0.2u |
| Qt 5.6 系列 | OpenSSL 1.0.2u （macOS 除外） |
| Qt 5.9 系列 | OpenSSL 1.0.2u （macOS 除外） |
| Qt 5.12 系列 | OpenSSL 1.1.1w （macOS 除外） |
| Qt 5.15 系列 | OpenSSL 3.0.13 （Windows 和 macOS 除外） |
| Qt 6.2 系列 | OpenSSL 3.0.13 |
| Qt 6.5 系列 | OpenSSL 3.0.13 |
| Qt 6.7 系列 | OpenSSL 3.0.13 |

## MariaDB 状态

从 {{% date 2023 2 8 %}}开始，Qt 5.15 及以上的桌面版构建中附带 MariaDB connector/C 的动态库。
这个动态库用来构建 MySQL 数据库插件。  
不使用 MySQL 提供的库的原因有以下几个。

1. MariaDB 是真正的“原来的” MySQL
1. 使用新版 MySQL（8.0 及以后的版本）需要下载并构建整个 MySQL 数据库。而 MySQL 数据库太大，构建较费事。
1. MySQL 出自 Oracle。而 Oracle 有打击开源社区的历史。

{{% mariaDBSeries %}}

| Qt 版本 | 使用的 MariaDB connector/C 版本 |
|-|-|
| ~~Qt 4.8 系列~~ | 不适用（结束生命周期） |
| ~~Qt 5.6 系列~~ | 不适用（结束生命周期） |
| ~~Qt 5.9 系列~~ | 不适用（结束生命周期） |
| ~~Qt 5.12 系列~~ | 不适用（未开发。且于 macOS 上结束生命周期） |
| Qt 5.15 系列 | MariaDB connector/C 3.1.23 |
| Qt 6.2 系列 | MariaDB connector/C 3.3.8 |
| Qt 6.5 系列 | MariaDB connector/C 3.3.8 |
| Qt 6.7 系列 | MariaDB connector/C 3.3.8 |

## Qt 构建表

**注：因为 Qt 6 移除了对 32 位 Windows 的支持，我们也不会为 32 位 Windows 提供 Qt 6 的构建。**   
**如果需要非 LTS 版本的静态构建，请直接联系我寻求商业定制。**

{{% QtTable %}}

{{% expand "遗留的构建" %}}
{{% QtTable 1 %}}
{{% /expand %}}
