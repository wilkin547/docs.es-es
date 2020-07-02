---
ms.openlocfilehash: e7f690030a5cb5605645f1ca42a6f08dcdd214f5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615765"
---
### <a name="tls-1x-by-default-passes-the-sch_send_aux_record-flag-to-the-underlying-schannel-api"></a>De forma predeterminada, TLS 1.x pasa la marca SCH_SEND_AUX_RECORD a la API SCHANNEL subyacente.

#### <a name="details"></a>Detalles

Cuando se usa TLS 1.x, .NET Framework se basa en la API SCHANNEL de Windows subyacente. A partir de .NET Framework 4.6, de forma predeterminada se pasa la marca [SCH_SEND_AUX_RECORD](https://docs.microsoft.com/windows/win32/api/schannel/ns-schannel-schannel_cred) a SCHANNEL. Esto hace que SCHANNEL divida los datos que se van a cifrar en dos registros independientes, el primero de un solo byte y el segundo con <em>n</em>-1 bytes. En raras ocasiones, esto interrumpe la comunicación entre los clientes y los servidores existentes que dan por hecho que los datos residen en un único registro.

#### <a name="suggestion"></a>Sugerencia

Si este cambio interrumpe la comunicación con un servidor existente, puede deshabilitar el envío de la marca [SCH_SEND_AUX_RECORD](https://docs.microsoft.com/windows/win32/api/schannel/ns-schannel-schannel_cred) y restaurar el comportamiento anterior de no dividir los datos en registros independientes si agrega el modificador siguiente al elemento [<](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) en la sección [<](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Net.DontEnableSchSendAuxRecord=true" />
</runtime>
```

> [!IMPORTANT]
> Este valor solamente se proporciona por motivos de compatibilidad con versiones anteriores. Pero no se recomienda su uso.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Borde        |
| Versión | 4.6         |
| Tipo    | Redestinación |

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Net.Security.SslStream?displayProperty=nameWithType>
- <xref:System.Net.ServicePointManager?displayProperty=nameWithType>
- <xref:System.Net.Http.HttpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>
- <xref:System.Net.FtpWebRequest?displayProperty=nameWithType>
