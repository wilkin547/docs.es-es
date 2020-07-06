---
ms.openlocfilehash: 7a7ecf052276fe8e62463498b83230d466630c79
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616298"
---
### <a name="workflow-xoml-definition-and-sqltrackingservice-cache-keys-changed-from-md5-to-sha256"></a>La definición XOML de flujo de trabajo y las claves de caché de SqlTrackingService han cambiado de MD5 a SHA256

#### <a name="details"></a>Detalles

El tiempo de ejecución de flujo de trabajo mantiene una caché de definiciones de flujo de trabajo definido en XOML. SqlTrackingService también mantiene una caché organizada por cadenas. Estas cachés están organizadas según los valores que incluyen el valor de código hash de suma de comprobación. En .NET Framework 4.7.2 y versiones anteriores, este hash de suma de comprobación usaba el algoritmo MD5, que causaba problemas en sistemas compatibles con FIPS. A partir de .NET Framework 4.8, el algoritmo utilizado es SHA256. No debería haber ninguna incidencia de compatibilidad con este cambio ya que los valores se vuelven a calcular cada vez que se inician el tiempo de ejecución de flujo de trabajo y SqlTrackingService. Sin embargo, hemos proporcionado una interpretación para permitir que los clientes puedan volver a usar el algoritmo hash heredado, en caso necesario.

#### <a name="suggestion"></a>Sugerencia

Si este cambio supone un problema al ejecutar los flujos de trabajo, pruebe a establecer uno o ambos modificadores `AppContext`:

- &quot;Switch.System.Workflow.Runtime.UseLegacyHashForWorkflowDefinitionDispenserCacheKey&quot; en true.
- &quot;Switch.System.Workflow.Runtime.UseLegacyHashForSqlTrackingCacheKey&quot; en true.
Mediante código:

<pre><code class="lang-csharp">System.AppContext.SetSwitch(&quot;Switch.System.Workflow.Runtime.UseLegacyHashForWorkflowDefinitionDispenserCacheKey&quot;, true);&#13;&#10;System.AppContext.SetSwitch(&quot;Switch.System.Workflow.Runtime.UseLegacyHashForSqlTrackingCacheKey&quot;, true);&#13;&#10;</code></pre>

O en el archivo de configuración (que debe estar en el archivo de configuración de la aplicación que está creando el objeto <xref:System.Workflow.Runtime.WorkflowRuntime>):

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Workflow.Runtime.UseLegacyHashForWorkflowDefinitionDispenserCacheKey=true&quot; /&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Workflow.Runtime.UseLegacyHashForSqlTrackingCacheKeytrue&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| Nombre    | Valor       |
|:--------|:------------|
| Ámbito   | Secundaria       |
| Versión | 4.8         |
| Tipo    | Redestinación |
