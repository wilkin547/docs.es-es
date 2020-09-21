---
ms.openlocfilehash: 9cd1d0955b8b77cb77d5c6938b37d9042d8144f6
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606354"
---
### <a name="data-binding-improvement-for-keyedcollection"></a>Mejora de enlace de datos para KeyedCollection

#### <a name="details"></a>Detalles

Se ha corregido el uso incorrecto de <xref:System.Windows.Data.Binding> del indizador IList cuando el objeto de origen declara un indizador personalizado con la misma firma (por ejemplo, KeyedCollection&lt;int, TItem&gt;).

#### <a name="suggestion"></a>Sugerencia

Para que una aplicación destinada a una versión anterior se beneficie de este cambio, se debe ejecutar en .NET Framework 4.8 o versiones posteriores, y debe participar en el cambio agregando el [modificador de AppContext](../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) en la sección <code>&lt;runtime&gt;</code> del archivo de configuración de aplicación y establecerla en <code>false</code>:<pre><code class="lang-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;startup&gt;&#13;&#10;&lt;supportedRuntime version=&quot;v4.0&quot; sku=&quot;.NETFramework,Version=v4.7&quot;/&gt;&#13;&#10;&lt;/startup&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;!-- AppContextSwitchOverrides value attribute is in the form of &#39;key1=true/false;key2=true/false  --&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Data.Binding.IListIndexerHidesCustomIndexer=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Major|
|Versión|4.8|
|Tipo|Tiempo de ejecución|

#### <a name="affected-apis"></a>API afectadas

No detectable a través del análisis de la API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
