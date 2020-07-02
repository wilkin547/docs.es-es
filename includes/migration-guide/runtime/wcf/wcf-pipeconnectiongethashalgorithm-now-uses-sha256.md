---
ms.openlocfilehash: 0f87f9e9b87860da97ce96e18104b44ec4327c91
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621389"
---
### <a name="wcf-pipeconnectiongethashalgorithm-now-uses-sha256"></a><span data-ttu-id="bb675-101">En PipeConnection.GetHashAlgorithm de WCF ahora se usa SHA256</span><span class="sxs-lookup"><span data-stu-id="bb675-101">WCF PipeConnection.GetHashAlgorithm now uses SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="bb675-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="bb675-102">Details</span></span>

<span data-ttu-id="bb675-103">A partir de .NET Framework 4.7.1, Windows Communication Foundation usa un código hash SHA256 para generar nombres aleatorios para las canalizaciones con nombre.</span><span class="sxs-lookup"><span data-stu-id="bb675-103">Starting with the .NET Framework 4.7.1, Windows Communication Foundation uses a SHA256 hash to generate random names for named pipes.</span></span> <span data-ttu-id="bb675-104">En .NET Framework 4.7 y versiones anteriores, usaba un hash SHA1.</span><span class="sxs-lookup"><span data-stu-id="bb675-104">In the .NET Framework 4.7 and earlier versions, it used a SHA1 hash.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="bb675-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="bb675-105">Suggestion</span></span>

<span data-ttu-id="bb675-106">Si tiene problemas de compatibilidad con este cambio en .NET Framework 4.7.1 o una versión posterior, puede excluirlo mediante la adición de la línea siguiente a la sección <code>&lt;runtime&gt;</code> del archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="bb675-106">If you run into compatibility issue with this change on the .NET Framework 4.7.1 or later, you can opt-out it by adding the following line to the <code>&lt;runtime&gt;</code> section of your app.config file:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InPipeConnectionGetHashAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="bb675-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="bb675-107">Name</span></span>    | <span data-ttu-id="bb675-108">Valor</span><span class="sxs-lookup"><span data-stu-id="bb675-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="bb675-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="bb675-109">Scope</span></span>   |<span data-ttu-id="bb675-110">Secundaria</span><span class="sxs-lookup"><span data-stu-id="bb675-110">Minor</span></span>|
|<span data-ttu-id="bb675-111">Versión</span><span class="sxs-lookup"><span data-stu-id="bb675-111">Version</span></span>|<span data-ttu-id="bb675-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="bb675-112">4.7.1</span></span>|
|<span data-ttu-id="bb675-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="bb675-113">Type</span></span>|<span data-ttu-id="bb675-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="bb675-114">Runtime</span></span>|
