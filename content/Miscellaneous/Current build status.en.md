{
  "title": "Current build status",
  "weight": 2,
  "isMaxWidthPreferred": true
}

## OpenSSL Status

My Qt builds is with linked OpenSSL support for most platforms, use (currently only) LTS versions of OpenSSL.  
Here is a list of OpenSSL builds of mine.

OpenSSL 3 series is used on Qt 6 after 6.2.3 and Qt 5.15 after {{% date 2023 9 11 %}}.  
Since Qt 6.2 changes tls backend to plugin, one can use more than one tls backend when building.  
On Windows we are using OpenSSL alongwith SChannel, while on macOS we are using OpenSSL alongwith SecureTransport.

{{% notice style="info" title="Note"  icon="fas fa-info-circle" %}}
Although I simultaneously maintain [openssl-externalCMake](https://github.com/Fsu0413/openssl-externalCMake) I don't use it for building OpenSSL.  
The OpenSSL built by that project still do not pass the test cases.  
So the builds here are still using original Perl-based build instruction.
{{% /notice %}}

{{% OpenSSLSeries %}}

| Qt Version | OpenSSL version used |
|-|-|
| Qt 4.8 Series | OpenSSL 1.0.2u |
| Qt 5.6 Series | OpenSSL 1.0.2u (except macOS) |
| Qt 5.9 Series | OpenSSL 1.0.2u (except macOS) |
| Qt 5.12 Series | OpenSSL 1.1.1w (except macOS) |
| Qt 5.15 Series | OpenSSL 3.0.13 (except Windows and macOS) |
| Qt 6.2 Series | OpenSSL 3.0.13 |
| Qt 6.5 Series | OpenSSL 3.0.13 |
| Qt 6.7 Series | OpenSSL 3.0.13 |

## MariaDB Status

I'll ship MariaDB connector/C dynamic library for Qt 5.15 and later version since {{% date 2023 2 8 %}}.  
This is used to build MySQL database backend.  
I have following reason for not using MySQL libraries.

1. MariaDB is the "original" MySQL per se.
1. Using later MySQL (8.0 series and later) need downloading and building a full MySQL database. But the MySQL database is bulky and hard to be built.
1. MySQL is from Oracle who had history of hitting open source community.

{{% mariaDBSeries %}}

| Qt Version | MariaDB connector/C version used |
|-|-|
| ~~Qt 4.8 Series~~ | N/A (EOL) |
| ~~Qt 5.6 Series~~ | N/A (EOL) |
| ~~Qt 5.9 Series~~ | N/A (EOL) |
| ~~Qt 5.12 Series~~ | N/A (Not developed against. Already EOL on macOS) |
| Qt 5.15 Series | MariaDB connector/C 3.1.23 |
| Qt 6.2 Series | MariaDB connector/C 3.3.8 |
| Qt 6.5 Series | MariaDB connector/C 3.3.8 |
| Qt 6.7 Series | MariaDB connector/C 3.3.8 |

## Qt Build Table

**Note: Since Qt 6 dropped support for 32-bit Windows for Qt 6, our Qt 6 builds will no longer run for 32-bit Windows either.**  
**If there is need of static builds for non-LTS release, please contect me directly for commerical customization.**

{{% QtTable %}}

{{% expand "Legacy builds" %}}
{{% QtTable 1 %}}
{{% /expand %}}
