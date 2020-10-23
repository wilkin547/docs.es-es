---
ms.openlocfilehash: d312ba2a22797ff6afff6b893f998c965e68e86e
ms.sourcegitcommit: e078b7540a8293ca1b604c9c0da1ff1506f0170b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "91997767"
---
### <a name="default-tls-cipher-suites-for-net-on-linux"></a>Conjuntos de cifrado TLS predeterminados para .NET en Linux

Ahora .NET en Linux respeta la configuración de OpenSSL para los conjuntos de cifrado predeterminados al realizar TLS/SSL a través de la clase <xref:System.Net.Security.SslStream> o de las operaciones de nivel superior, como HTTPS a través de la clase <xref:System.Net.Http.HttpClient>. Cuando los conjuntos de cifrado predeterminados no se configuran de forma explícita, .NET en Linux usa una lista rigurosamente restringida de conjuntos de cifrado permitidos.

#### <a name="change-description"></a>Descripción del cambio

En versiones anteriores, .NET no respeta la configuración del sistema para los conjuntos de cifrado predeterminados. La lista de conjuntos de cifrado predeterminados para .NET en Linux es muy permisiva.

A partir de .NET 5.0, .NET en Linux respeta la configuración de OpenSSL para los conjuntos de cifrado predeterminados cuando se especifica en *openssl.cnf*. Cuando los conjuntos de cifrado no se configuran de forma explícita, los únicos que se permiten son los siguientes:

- Conjuntos de cifrado TLS 1.3
- TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384
- TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256
- TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384
- TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256
- TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA384
- TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA256
- TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384
- TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256

Como este valor predeterminado de reserva no incluye ningún conjunto de cifrado que sea compatible con TLS 1.0 o TLS 1.1, estas versiones de protocolo anteriores están deshabilitadas de forma predeterminada.

Si se proporciona un valor CipherSuitePolicy a SslStream para una sesión específica, se reemplazará el contenido del archivo de configuración o el valor predeterminado de reserva de .NET.

#### <a name="reason-for-change"></a>Motivo del cambio

Los usuarios que ejecutan .NET en Linux han solicitado que la configuración predeterminada de <xref:System.Net.Security.SslStream> se cambie por otra que proporcione una clasificación de alta seguridad de herramientas de evaluación de terceros.

#### <a name="version-introduced"></a>Versión introducida

5.0 RC1

#### <a name="recommended-action"></a>Acción recomendada

Es probable que los nuevos valores predeterminados funcionen al comunicarse con servidores o clientes modernos. Si tiene que expandir la lista de conjuntos de cifrado predeterminados para aceptar clientes heredados (o para ponerse en contacto con servidores heredados), especifique un valor de `CipherSuitePolicy` o cambie el archivo de configuración de OpenSSL. En muchas distribuciones de Linux, el archivo de configuración de OpenSSL está en */etc/ssl/openssl.cnf*.

Este archivo *openssl.cnf* de ejemplo es un archivo mínimo que equivale a la directiva de conjuntos de cifrado predeterminados para .NET 5.0 y versiones posteriores en Linux. En lugar de reemplazar el archivo del sistema, combine estos conceptos con el archivo que se encuentre en el sistema.

```ini
openssl_conf = default_conf

[default_conf]
ssl_conf = ssl_sect

[ssl_sect]
system_default = system_default_sect

[system_default_sect]
CipherString = ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-ECDSA-AES128-GCM-SHA256:ECDHE-RSA-AES256-GCM-SHA384:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES256-SHA384:ECDHE-ECDSA-AES128-SHA256:ECDHE-RSA-AES256-SHA384:ECDHE-RSA-AES128-SHA256
```

En las distribuciones Red Hat Enterprise Linux, CentOS y Fedora, las aplicaciones .NET tienen como valor predeterminado los conjuntos de cifrado permitidos por las directivas de cifrado de todo el sistema. En estas distribuciones, use la configuración de directivas de cifrado en lugar de *openssl.cnf*.

#### <a name="category"></a>Categoría

- Criptografía
- Seguridad

#### <a name="affected-apis"></a>API afectadas

No detectable a través del análisis de API.

<!--

#### Affected APIs

- Not detectible via API analysis.

-->
