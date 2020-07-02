---
ms.openlocfilehash: 0e949cbdeda99dd7b94e919b903a21171a57f527
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614728"
---
### <a name="wcf-binding-with-the-transportwithmessagecredential-security-mode"></a>Enlace de WCF con el modo de seguridad de TransportWithMessageCredential

#### <a name="details"></a>Detalles

A partir de .NET Framework 4.6.1, el enlace de WCF que usa el modo de seguridad de TransportWithMessageCredential se puede configurar para recibir mensajes con encabezados &quot;para&quot; sin firmar para las claves de seguridad asimétricas. De forma predeterminada, en .NET Framework 4.6.1 se seguirán rechazando los encabezados &quot;para&quot; sin firmar. Solo se aceptarán si una aplicación incluye este modo de operación nuevo mediante el modificador de configuración Switch.System.ServiceModel.AllowUnsignedToHeader.

#### <a name="suggestion"></a>Sugerencia

Como es una característica opcional, no debería afectar al comportamiento de las aplicaciones existentes.<br/>Para controlar si se usa el comportamiento nuevo o no, use la opción de configuración siguiente:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.ServiceModel.AllowUnsignedToHeader=true" />
</runtime>
```

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Transparente |
| Versión | 4.6.1       |
| Tipo    | Redestinación |

#### <a name="affected-apis"></a>API afectadas

- <xref:System.ServiceModel.BasicHttpSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType>
- <xref:System.ServiceModel.BasicHttpsSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType>
- <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential?displayProperty=nameWithType>
- <xref:System.ServiceModel.WSFederationHttpSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType>
