---
ms.openlocfilehash: 7a7ecf052276fe8e62463498b83230d466630c79
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616298"
---
### <a name="workflow-xoml-definition-and-sqltrackingservice-cache-keys-changed-from-md5-to-sha256"></a><span data-ttu-id="32e22-101">La definición XOML de flujo de trabajo y las claves de caché de SqlTrackingService han cambiado de MD5 a SHA256</span><span class="sxs-lookup"><span data-stu-id="32e22-101">Workflow XOML definition and SqlTrackingService cache keys changed from MD5 to SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="32e22-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="32e22-102">Details</span></span>

<span data-ttu-id="32e22-103">El tiempo de ejecución de flujo de trabajo mantiene una caché de definiciones de flujo de trabajo definido en XOML.</span><span class="sxs-lookup"><span data-stu-id="32e22-103">The Workflow Runtime in keeps a cache of workflow definitions defined in XOML.</span></span> <span data-ttu-id="32e22-104">SqlTrackingService también mantiene una caché organizada por cadenas.</span><span class="sxs-lookup"><span data-stu-id="32e22-104">The SqlTrackingService also keeps a cache that is keyed by strings.</span></span> <span data-ttu-id="32e22-105">Estas cachés están organizadas según los valores que incluyen el valor de código hash de suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="32e22-105">These caches are keyed by values that include checksum hash value.</span></span> <span data-ttu-id="32e22-106">En .NET Framework 4.7.2 y versiones anteriores, este hash de suma de comprobación usaba el algoritmo MD5, que causaba problemas en sistemas compatibles con FIPS.</span><span class="sxs-lookup"><span data-stu-id="32e22-106">In the .NET Framework 4.7.2 and earlier versions, this checksum hashing used the MD5 algorithm, which caused issues on FIPS-enabled systems.</span></span> <span data-ttu-id="32e22-107">A partir de .NET Framework 4.8, el algoritmo utilizado es SHA256. No debería haber ninguna incidencia de compatibilidad con este cambio ya que los valores se vuelven a calcular cada vez que se inician el tiempo de ejecución de flujo de trabajo y SqlTrackingService.</span><span class="sxs-lookup"><span data-stu-id="32e22-107">Starting with the .NET Framework 4.8, the algorithm used is SHA256.There shouldn't be a compatibility issue with this change because the values are recalculated each time the Workflow Runtime and SqlTrackingService is started.</span></span> <span data-ttu-id="32e22-108">Sin embargo, hemos proporcionado una interpretación para permitir que los clientes puedan volver a usar el algoritmo hash heredado, en caso necesario.</span><span class="sxs-lookup"><span data-stu-id="32e22-108">However, we have provided quirks to allow customers to revert back to usage of the legacy hashing algorithm, if necessary.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="32e22-109">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="32e22-109">Suggestion</span></span>

<span data-ttu-id="32e22-110">Si este cambio supone un problema al ejecutar los flujos de trabajo, pruebe a establecer uno o ambos modificadores `AppContext`:</span><span class="sxs-lookup"><span data-stu-id="32e22-110">If this change presents a problem when executing workflows, try setting one or both of the `AppContext` switches:</span></span>

- <span data-ttu-id="32e22-111">&quot;Switch.System.Workflow.Runtime.UseLegacyHashForWorkflowDefinitionDispenserCacheKey&quot; en true.</span><span class="sxs-lookup"><span data-stu-id="32e22-111">&quot;Switch.System.Workflow.Runtime.UseLegacyHashForWorkflowDefinitionDispenserCacheKey&quot; to true.</span></span>
- <span data-ttu-id="32e22-112">&quot;Switch.System.Workflow.Runtime.UseLegacyHashForSqlTrackingCacheKey&quot; en true.</span><span class="sxs-lookup"><span data-stu-id="32e22-112">&quot;Switch.System.Workflow.Runtime.UseLegacyHashForSqlTrackingCacheKey&quot; to true.</span></span>
<span data-ttu-id="32e22-113">Mediante código:</span><span class="sxs-lookup"><span data-stu-id="32e22-113">In code:</span></span>

<pre><code class="lang-csharp">System.AppContext.SetSwitch(&quot;Switch.System.Workflow.Runtime.UseLegacyHashForWorkflowDefinitionDispenserCacheKey&quot;, true);&#13;&#10;System.AppContext.SetSwitch(&quot;Switch.System.Workflow.Runtime.UseLegacyHashForSqlTrackingCacheKey&quot;, true);&#13;&#10;</code></pre>

<span data-ttu-id="32e22-114">O en el archivo de configuración (que debe estar en el archivo de configuración de la aplicación que está creando el objeto <xref:System.Workflow.Runtime.WorkflowRuntime>):</span><span class="sxs-lookup"><span data-stu-id="32e22-114">Or in the configuration file (this needs to be in the config file for the application that is creating the <xref:System.Workflow.Runtime.WorkflowRuntime> object):</span></span>

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Workflow.Runtime.UseLegacyHashForWorkflowDefinitionDispenserCacheKey=true&quot; /&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Workflow.Runtime.UseLegacyHashForSqlTrackingCacheKeytrue&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="32e22-115">Nombre</span><span class="sxs-lookup"><span data-stu-id="32e22-115">Name</span></span>    | <span data-ttu-id="32e22-116">Valor</span><span class="sxs-lookup"><span data-stu-id="32e22-116">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="32e22-117">Ámbito</span><span class="sxs-lookup"><span data-stu-id="32e22-117">Scope</span></span>   | <span data-ttu-id="32e22-118">Secundaria</span><span class="sxs-lookup"><span data-stu-id="32e22-118">Minor</span></span>       |
| <span data-ttu-id="32e22-119">Versión</span><span class="sxs-lookup"><span data-stu-id="32e22-119">Version</span></span> | <span data-ttu-id="32e22-120">4.8</span><span class="sxs-lookup"><span data-stu-id="32e22-120">4.8</span></span>         |
| <span data-ttu-id="32e22-121">Tipo</span><span class="sxs-lookup"><span data-stu-id="32e22-121">Type</span></span>    | <span data-ttu-id="32e22-122">Redestinación</span><span class="sxs-lookup"><span data-stu-id="32e22-122">Retargeting</span></span> |
