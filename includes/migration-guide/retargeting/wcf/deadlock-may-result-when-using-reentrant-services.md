---
ms.openlocfilehash: add7b803c413f8d9ba913d5dcc1a21bbd0c5bd48
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59805041"
---
### <a name="deadlock-may-result-when-using-reentrant-services"></a>El uso de servicios reentrantes puede producir un interbloqueo

|   |   |
|---|---|
|Detalles|Se puede producir un interbloqueo en un servicio reentrante, lo que restringe las instancias del servicio a un subproceso de ejecución a la vez. Los servicios propensos a sufrir este problema tendrán el atributo <xref:System.ServiceModel.ServiceBehaviorAttribute> siguiente en su código:<pre><code class="lang-csharp">[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Reentrant)]&#13;&#10;</code></pre>|
|Sugerencia|Para solucionar este problema, puede seguir estos pasos:<ul><li>Establezca el modo de simultaneidad del servicio en <xref:System.ServiceModel.ConcurrencyMode.Single?displayProperty=nameWithType> o &lt;System.ServiceModel.ConcurrencyMode.Multiple?displayProperty=nameWithType&gt;. Por ejemplo:</li></ul><pre><code class="lang-csharp">[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Single)]&#13;&#10;</code></pre><ul><li>Instale la actualización más reciente de .NET Framework 4.6.2 o actualice a una versión posterior de .NET Framework. Esto deshabilita el flujo de <xref:System.Threading.ExecutionContext> en <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType>. Este comportamiento se puede configurar; equivale a agregar la configuración de aplicación siguiente al archivo de configuración:</li></ul><pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.ServiceModel.DisableOperationContextAsyncFlow&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>El valor de <code>Switch.System.ServiceModel.DisableOperationContextAsyncFlow</code> nunca se debe establecer en <code>false</code> para los servicios reentrantes.|
|Ámbito|Secundaria|
|Versión|4.6.2|
|Tipo|Redestinación|
|API afectadas|<ul><li><xref:System.ServiceModel.ServiceBehaviorAttribute?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ConcurrencyMode.Reentrant?displayProperty=nameWithType></li></ul>|
