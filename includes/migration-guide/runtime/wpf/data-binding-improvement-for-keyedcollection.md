---
ms.openlocfilehash: 8aae403e3f23d3bfc755140b2ac29d757f10f753
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "74451691"
---
### <a name="data-binding-improvement-for-keyedcollection"></a>Mejora de enlace de datos para KeyedCollection

|   |   |
|---|---|
|Detalles|Se ha corregido el uso incorrecto de <xref:System.Windows.Data.Binding> del indizador IList cuando el objeto de origen declara un indizador personalizado con la misma firma (por ejemplo, KeyedCollection&lt;int, TItem&gt;).|
|Sugerencia|Para que una aplicación destinada a una versión anterior se beneficie de este cambio, se debe ejecutar en .NET Framework 4.8 o versiones posteriores, y debe participar en el cambio agregando el [modificador de AppContext](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) en la sección <code>&lt;runtime&gt;</code> del archivo de configuración de aplicación y establecerla en <code>false</code>:<pre><code class="lang-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;startup&gt;&#13;&#10;&lt;supportedRuntime version=&quot;v4.0&quot; sku=&quot;.NETFramework,Version=v4.7&quot;/&gt;&#13;&#10;&lt;/startup&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;!-- AppContextSwitchOverrides value attribute is in the form of &#39;key1=true/false;key2=true/false  --&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Data.Binding.IListIndexerHidesCustomIndexer=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Ámbito|Major|
|Versión|4.8|
|Tipo|Tiempo de ejecución|
