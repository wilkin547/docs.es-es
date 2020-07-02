---
ms.openlocfilehash: 5c86be598ab6196ecf4da05451c7f22d2be52c12
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614701"
---
### <a name="default-value-of-servicepointmanagersecurityprotocol-is-securityprotocoltypesystemdefault"></a>El valor predeterminado de ServicePointManager.SecurityProtocol es SecurityProtocolType.System.Default

#### <a name="details"></a>Detalles

A partir de las aplicaciones que tienen como destino .NET Framework 4.7, el valor predeterminado de la propiedad <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType> es <xref:System.Net.SecurityProtocolType.SystemDefault?displayProperty=nameWithType>. Este cambio permite que las API para redes de .NET Framework basadas en SslStream (como FTP, HTTPS y SMTP) hereden los protocolos de seguridad predeterminados del sistema operativo en lugar de usar valores codificados de forma rígida definidos por .NET Framework. El valor predeterminado varía según el sistema operativo y la configuración personalizada que realice el administrador del sistema. Para obtener información sobre el protocolo SChannel predeterminado en cada versión del sistema operativo Windows, vea [Protocols in TLS/SSL (Schannel SSP)](https://docs.microsoft.com/windows/desktop/SecAuthN/protocols-in-tls-ssl--schannel-ssp-) (Protocolos en TLS/SSL [Schannel SSP]).</p>Para las aplicaciones que tienen como destino una versión anterior de .NET Framework, el valor predeterminado de la propiedad <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType> depende de la versión de .NET Framework de destino. Vea la [sección Redes del artículo Cambios de redestinación para la migración desde .NET Framework 4.5.2 a 4.6](~/docs/framework/migration-guide/retargeting/4.5.2-4.6.md#networking) para obtener más información.

#### <a name="suggestion"></a>Sugerencia

Este cambio solo afecta a las aplicaciones que tienen como destino .NET Framework 4.7 o versiones posteriores. Si prefiere usar un protocolo definido en lugar de basarse en el valor predeterminado del sistema, puede establecer de forma explícita el valor de la propiedad <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType>. Si no quiere este cambio, puede rechazarlo mediante la adición de un valor de configuración a la sección [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación. En el ejemplo siguiente se muestra la sección `<runtime>` y el conmutador de rechazo `Switch.System.Net.DontEnableSystemDefaultTlsVersions`:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Net.DontEnableSystemDefaultTlsVersions=true" />
</runtime>
```

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Secundaria       |
| Versión | 4.7         |
| Tipo    | Redestinación |

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType>
