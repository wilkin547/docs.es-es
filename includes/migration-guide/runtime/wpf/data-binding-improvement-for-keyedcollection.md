---
ms.openlocfilehash: 9cd1d0955b8b77cb77d5c6938b37d9042d8144f6
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606354"
---
### <a name="data-binding-improvement-for-keyedcollection"></a><span data-ttu-id="0e21d-101">Mejora de enlace de datos para KeyedCollection</span><span class="sxs-lookup"><span data-stu-id="0e21d-101">Data Binding improvement for KeyedCollection</span></span>

#### <a name="details"></a><span data-ttu-id="0e21d-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="0e21d-102">Details</span></span>

<span data-ttu-id="0e21d-103">Se ha corregido el uso incorrecto de <xref:System.Windows.Data.Binding> del indizador IList cuando el objeto de origen declara un indizador personalizado con la misma firma (por ejemplo, KeyedCollection&lt;int, TItem&gt;).</span><span class="sxs-lookup"><span data-stu-id="0e21d-103">Fixed <xref:System.Windows.Data.Binding> incorrect use of IList indexer when the source object declares a custom indexer with the same signature (for example, KeyedCollection&lt;int,TItem&gt;).</span></span>

#### <a name="suggestion"></a><span data-ttu-id="0e21d-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="0e21d-104">Suggestion</span></span>

<span data-ttu-id="0e21d-105">Para que una aplicación destinada a una versión anterior se beneficie de este cambio, se debe ejecutar en .NET Framework 4.8 o versiones posteriores, y debe participar en el cambio agregando el [modificador de AppContext](../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) en la sección <code>&lt;runtime&gt;</code> del archivo de configuración de aplicación y establecerla en <code>false</code>:</span><span class="sxs-lookup"><span data-stu-id="0e21d-105">In order for an application that targets an older version to benefit from this change, it must run on the .NET Framework 4.8 or later, and it must opt in to the change by adding the following [AppContext switch](../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) to the <code>&lt;runtime&gt;</code> section of the app config file and setting it to <code>false</code>:</span></span><pre><code class="lang-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;startup&gt;&#13;&#10;&lt;supportedRuntime version=&quot;v4.0&quot; sku=&quot;.NETFramework,Version=v4.7&quot;/&gt;&#13;&#10;&lt;/startup&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;!-- AppContextSwitchOverrides value attribute is in the form of &#39;key1=true/false;key2=true/false  --&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Data.Binding.IListIndexerHidesCustomIndexer=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="0e21d-106">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="0e21d-106">Name</span></span>    | <span data-ttu-id="0e21d-107">Valor</span><span class="sxs-lookup"><span data-stu-id="0e21d-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="0e21d-108">Ámbito</span><span class="sxs-lookup"><span data-stu-id="0e21d-108">Scope</span></span>   |<span data-ttu-id="0e21d-109">Major</span><span class="sxs-lookup"><span data-stu-id="0e21d-109">Major</span></span>|
|<span data-ttu-id="0e21d-110">Versión</span><span class="sxs-lookup"><span data-stu-id="0e21d-110">Version</span></span>|<span data-ttu-id="0e21d-111">4.8</span><span class="sxs-lookup"><span data-stu-id="0e21d-111">4.8</span></span>|
|<span data-ttu-id="0e21d-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="0e21d-112">Type</span></span>|<span data-ttu-id="0e21d-113">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="0e21d-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="0e21d-114">API afectadas</span><span class="sxs-lookup"><span data-stu-id="0e21d-114">Affected APIs</span></span>

<span data-ttu-id="0e21d-115">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="0e21d-115">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
