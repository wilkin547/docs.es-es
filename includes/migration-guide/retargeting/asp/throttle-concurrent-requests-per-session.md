---
ms.openlocfilehash: b521f4163bf5bf4a369d0eec12dae503703a976e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614644"
---
### <a name="throttle-concurrent-requests-per-session"></a>Límite de solicitudes simultáneas por sesión

#### <a name="details"></a>Detalles

En .NET Framework 4.6.2 y en versiones anteriores, ASP.NET ejecuta las solicitudes con el mismo Sessionid de manera secuencial y siempre emite el Sessionid mediante cookies de forma predeterminada. Si una página tarda mucho tiempo en responder, reducirá considerablemente el rendimiento del servidor simplemente presionando <kbd>F5</kbd> en el explorador. En la corrección, se ha agregado un contador para realizar el seguimiento de las solicitudes en cola y finalizar las solicitudes cuando superen un límite especificado. El valor predeterminado es 50. Si se alcanza el límite, se registrará una advertencia en el registro de eventos y se podrá grabar una respuesta HTTP 500 en el registro de IIS.

#### <a name="suggestion"></a>Sugerencia

Para restaurar el comportamiento anterior, puede agregar la siguiente configuración al archivo web.config para rechazar el nuevo comportamiento.

```xml
<appSettings>
    <add key="aspnet:RequestQueueLimitPerSession" value="2147483647"/>
</appSettings>
```

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Borde        |
| Versión | 4.7         |
| Tipo    | Redestinación |
