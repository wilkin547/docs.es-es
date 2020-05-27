---
ms.openlocfilehash: 3c6142fd536bad5676f02570fecd4eb0605db829
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721645"
---
### <a name="begin-trusted-certificate-syntax-no-longer-supported-for-root-certificates-on-linux"></a>Ya no se admite la sintaxis "BEGIN TRUSTED CERTIFICATE" en certificados raíz de Linux

Los certificados raíz de Linux y otros sistemas similares a Unix (a excepción de macOS) se pueden presentar de dos formas: el encabezado PEM `BEGIN CERTIFICATE` estándar y el encabezado PEM `BEGIN TRUSTED CERTIFICATE` específico de OpenSSL. La última sintaxis permite una configuración adicional que ha provocado problemas de compatibilidad con la clase <xref:System.Security.Cryptography.X509Certificates.X509Chain?displayProperty=fullName> de .NET Core. El motor de cadena ya no carga el contenido del certificado raíz `BEGIN TRUSTED CERTIFICATE` a partir de .NET Core 3.0.

#### <a name="change-description"></a>Descripción del cambio

Anteriormente, las sintaxis `BEGIN CERTIFICATE` y `BEGIN TRUSTED CERTIFICATE` se usaban para rellenar la lista de confianza raíz. Si se ha usado la sintaxis `BEGIN TRUSTED CERTIFICATE` y se han especificado opciones adicionales en el archivo, es posible que <xref:System.Security.Cryptography.X509Certificates.X509Chain> haya informado de que la confianza de cadena no se permite explícitamente (<xref:System.Security.Cryptography.X509Certificates.X509ChainStatusFlags.ExplicitDistrust?displayProperty=nameWithType>). Con todo, si el certificado también se había especificado con la sintaxis `BEGIN CERTIFICATE` en un archivo cargado anteriormente, se permitía la confianza de cadena.

A partir de .NET Core 3.0, ya no se lee el contenido de `BEGIN TRUSTED CERTIFICATE`. Si el certificado no se especifica también mediante una sintaxis `BEGIN CERTIFICATE` estándar, <xref:System.Security.Cryptography.X509Certificates.X509Chain> informa de que la raíz no es de confianza (<xref:System.Security.Cryptography.X509Certificates.X509ChainStatusFlags.UntrustedRoot?displayProperty=nameWithType>).

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="recommended-action"></a>Acción recomendada

La mayoría de las aplicaciones no se ven afectadas por este cambio, pero las aplicaciones que no pueden ver ambos orígenes del certificado raíz por problemas de permisos pueden experimentar errores inesperados de `UntrustedRoot` después de actualizarse.

Muchas distribuciones de Linux escriben certificados raíz en dos ubicaciones: un directorio con un certificado por archivo y una concatenación de un archivo. En algunas distribuciones, el directorio con un certificado por archivo usa la sintaxis `BEGIN TRUSTED CERTIFICATE` mientras que la concatenación de archivos usa la sintaxis `BEGIN CERTIFICATE` estándar. Asegúrese de que los certificados raíz personalizados se agregan como `BEGIN CERTIFICATE` en al menos una de estas ubicaciones y que la aplicación puede leer ambas ubicaciones.

El directorio típico es */etc/ssl/certs/* y el archivo concatenado típico es */etc/ssl/cert.pem*. Use el comando `openssl version -d` para determinar la raíz específica de la plataforma, que puede ser diferente de */etc/ssl/* . Por ejemplo, en Ubuntu 18.04, el directorio es */usr/lib/ssl/certs/* y el archivo es */usr/lib/ssl/cert.pem*. A pesar de esto, */usr/lib/ssl/certs/* es un vínculo simbólico a */etc/ssl/certs/* y */usr/lib/ssl/cert.pem* no existe.

```bash
$ openssl version -d
OPENSSLDIR: "/usr/lib/ssl"
$ ls -al /usr/lib/ssl
total 12
drwxr-xr-x  3 root root 4096 Dec 12 17:10 .
drwxr-xr-x 73 root root 4096 Feb 20 15:18 ..
lrwxrwxrwx  1 root root   14 Mar 27  2018 certs -> /etc/ssl/certs
drwxr-xr-x  2 root root 4096 Dec 12 17:10 misc
lrwxrwxrwx  1 root root   20 Nov 12 16:58 openssl.cnf -> /etc/ssl/openssl.cnf
lrwxrwxrwx  1 root root   16 Mar 27  2018 private -> /etc/ssl/private
```

#### <a name="category"></a>Categoría

Criptografía

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Security.Cryptography.X509Certificates.X509Chain?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Security.Cryptography.X509Certificates.X509Chain`

-->
