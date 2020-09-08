---
ms.openlocfilehash: d32725b0d3063d3320b73e02039ff567090da932
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496762"
---
### <a name="wcf-pipeconnectiongethashalgorithm-now-uses-sha256"></a><span data-ttu-id="48240-101">En PipeConnection.GetHashAlgorithm de WCF ahora se usa SHA256</span><span class="sxs-lookup"><span data-stu-id="48240-101">WCF PipeConnection.GetHashAlgorithm now uses SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="48240-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="48240-102">Details</span></span>

<span data-ttu-id="48240-103">A partir de .NET Framework 4.7.1, Windows Communication Foundation usa un código hash SHA256 para generar nombres aleatorios para las canalizaciones con nombre.</span><span class="sxs-lookup"><span data-stu-id="48240-103">Starting with the .NET Framework 4.7.1, Windows Communication Foundation uses a SHA256 hash to generate random names for named pipes.</span></span> <span data-ttu-id="48240-104">En .NET Framework 4.7 y versiones anteriores, usaba un hash SHA1.</span><span class="sxs-lookup"><span data-stu-id="48240-104">In the .NET Framework 4.7 and earlier versions, it used a SHA1 hash.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="48240-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="48240-105">Suggestion</span></span>

<span data-ttu-id="48240-106">Si tiene problemas de compatibilidad con este cambio en .NET Framework 4.7.1 o una versión posterior, puede excluirlo mediante la adición de la línea siguiente a la sección <code>&lt;runtime&gt;</code> del archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="48240-106">If you run into compatibility issue with this change on the .NET Framework 4.7.1 or later, you can opt-out it by adding the following line to the <code>&lt;runtime&gt;</code> section of your app.config file:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InPipeConnectionGetHashAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="48240-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="48240-107">Name</span></span>    | <span data-ttu-id="48240-108">Valor</span><span class="sxs-lookup"><span data-stu-id="48240-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="48240-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="48240-109">Scope</span></span>   |<span data-ttu-id="48240-110">Secundaria</span><span class="sxs-lookup"><span data-stu-id="48240-110">Minor</span></span>|
|<span data-ttu-id="48240-111">Versión</span><span class="sxs-lookup"><span data-stu-id="48240-111">Version</span></span>|<span data-ttu-id="48240-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="48240-112">4.7.1</span></span>|
|<span data-ttu-id="48240-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="48240-113">Type</span></span>|<span data-ttu-id="48240-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="48240-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="48240-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="48240-115">Affected APIs</span></span>

<span data-ttu-id="48240-116">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="48240-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
