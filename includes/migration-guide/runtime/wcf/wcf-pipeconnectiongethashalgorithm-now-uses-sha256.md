---
ms.openlocfilehash: 3cf1740565343558a85fdfa68957773468c28231
ms.sourcegitcommit: 261e0c98a111357692b3b63c596edf0cacf72991
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2020
ms.locfileid: "90770831"
---
### <a name="wcf-pipeconnectiongethashalgorithm-now-uses-sha256"></a>En PipeConnection.GetHashAlgorithm de WCF ahora se usa SHA256

#### <a name="details"></a>Detalles

A partir de .NET Framework 4.7.1, Windows Communication Foundation usa un código hash SHA256 para generar nombres aleatorios para las canalizaciones con nombre. En .NET Framework 4.7 y versiones anteriores, usaba un hash SHA1.

#### <a name="suggestion"></a>Sugerencia

Si tiene problemas de compatibilidad con este cambio en .NET Framework 4.7.1 o una versión posterior, puede excluirlo mediante la adición de la línea siguiente a la sección `<runtime>` del archivo app.config:

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.ServiceModel.UseSha1InPipeConnectionGetHashAlgorithm=true" />
  </runtime>
</configuration>

| Name    | Value   |
|:--------|:--------|
| Scope   | Minor   |
| Version | 4.7.1   |
| Type    | Runtime |

#### Affected APIs

Not detectable via API analysis.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
