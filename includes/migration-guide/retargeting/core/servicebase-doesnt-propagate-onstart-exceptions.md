---
ms.openlocfilehash: 519de92ca4201d199941afe6382ddf9fc480fbbd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614776"
---
### <a name="servicebase-doesnt-propagate-onstart-exceptions"></a>ServiceBase no propaga las excepciones OnStart

#### <a name="details"></a>Detalles

En .NET Framework 4.7 y versiones anteriores, las excepciones que se producen al inicio del servicio no se propagan al autor de la llamada de <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType>.<br/>A partir de las aplicaciones que tienen como destino .NET Framework 4.7.1, el tiempo de ejecución propaga las excepciones a <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType> para los servicios que no se pueden iniciar.

#### <a name="suggestion"></a>Sugerencia

Durante el inicio del servicio, si hay una excepción, se propaga. Esto debería ayudar a diagnosticar los casos en los que no se pueden iniciar los servicios. <br/>Si no quiere este comportamiento, puede rechazarlo mediante la adición del elemento &lt;AppContextSwitchOverrides&gt; siguiente a la sección &lt;runtime&gt; del archivo de configuración de la aplicación:

```xml
<AppContextSwitchOverrides value="Switch.System.ServiceProcess.DontThrowExceptionsOnStart=true" />
```

Si la aplicación está destinada a una versión anterior a 4.7.1 pero quiere tener este comportamiento, agregue el elemento &lt;AppContextSwitchOverrides&gt; siguiente a la sección &lt;runtime&gt; del archivo de configuración de la aplicación:

```xml
<AppContextSwitchOverrides value="Switch.System.ServiceProcess.DontThrowExceptionsOnStart=false" />
```

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Secundaria       |
| Versión | 4.7.1       |
| Tipo    | Redestinación |

#### <a name="affected-apis"></a>API afectadas

- <xref:System.ServiceProcess.ServiceBase.Run(System.ServiceProcess.ServiceBase)?displayProperty=nameWithType>
- <xref:System.ServiceProcess.ServiceBase.Run(System.ServiceProcess.ServiceBase[])?displayProperty=nameWithType>
