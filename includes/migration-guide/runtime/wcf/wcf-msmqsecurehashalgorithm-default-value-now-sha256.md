---
ms.openlocfilehash: 7c0227980aa5d90f3788783088bcd7cd9509ed66
ms.sourcegitcommit: 261e0c98a111357692b3b63c596edf0cacf72991
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2020
ms.locfileid: "90770846"
---
### <a name="wcf-msmqsecurehashalgorithm-default-value-is-now-sha256"></a>El valor predeterminado de MsmqSecureHashAlgorithm de WCF ahora es SHA256

#### <a name="details"></a>Detalles

A partir de .NET Framework 4.7.1, el algoritmo de firma de mensajes predeterminado de WCF para los mensajes de Msmq es SHA256. En .NET Framework 4.7 y versiones anteriores, el algoritmo de firma de mensajes predeterminado es SHA1.

#### <a name="suggestion"></a>Sugerencia

Si tiene problemas de compatibilidad con este cambio en .NET Framework 4.7.1 o una versión posterior, puede excluirlo mediante la adición de la línea siguiente a la sección `<runtime>` del archivo app.config:

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InMsmqEncryptionAlgorithm=true&quot; />
  </runtime>
</configuration>
```

| NOMBRE    | Valor   |
|:--------|:--------|
| Ámbito   | Secundaria   |
| Versión | 4.7.1   |
| Tipo    | Tiempo de ejecución |

#### <a name="affected-apis"></a>API afectadas

No detectable a través del análisis de la API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
