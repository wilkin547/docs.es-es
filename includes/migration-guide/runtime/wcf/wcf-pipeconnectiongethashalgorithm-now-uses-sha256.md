---
ms.openlocfilehash: 318609c15d2e0b9a7ee59b38463735b33ef87974
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "67857257"
---
### <a name="wcf-pipeconnectiongethashalgorithm-now-uses-sha256"></a><span data-ttu-id="a71ca-101">En PipeConnection.GetHashAlgorithm de WCF ahora se usa SHA256</span><span class="sxs-lookup"><span data-stu-id="a71ca-101">WCF PipeConnection.GetHashAlgorithm now uses SHA256</span></span>

|   |   |
|---|---|
|<span data-ttu-id="a71ca-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="a71ca-102">Details</span></span>|<span data-ttu-id="a71ca-103">A partir de .NET Framework 4.7.1, Windows Communication Foundation usa un código hash SHA256 para generar nombres aleatorios para las canalizaciones con nombre.</span><span class="sxs-lookup"><span data-stu-id="a71ca-103">Starting with the .NET Framework 4.7.1, Windows Communication Foundation uses a SHA256 hash to generate random names for named pipes.</span></span> <span data-ttu-id="a71ca-104">En .NET Framework 4.7 y versiones anteriores, usaba un hash SHA1.</span><span class="sxs-lookup"><span data-stu-id="a71ca-104">In the .NET Framework 4.7 and earlier versions, it used a SHA1 hash.</span></span>|
|<span data-ttu-id="a71ca-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="a71ca-105">Suggestion</span></span>|<span data-ttu-id="a71ca-106">Si tiene problemas de compatibilidad con este cambio en .NET Framework 4.7.1 o una versión posterior, puede excluirlo mediante la adición de la línea siguiente a la sección <code>&lt;runtime&gt;</code> del archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="a71ca-106">If you run into compatibility issue with this change on the .NET Framework 4.7.1 or later, you can opt-out it by adding the following line to the <code>&lt;runtime&gt;</code> section of your app.config file:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InPipeConnectionGetHashAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="a71ca-107">Ámbito</span><span class="sxs-lookup"><span data-stu-id="a71ca-107">Scope</span></span>|<span data-ttu-id="a71ca-108">Secundaria</span><span class="sxs-lookup"><span data-stu-id="a71ca-108">Minor</span></span>|
|<span data-ttu-id="a71ca-109">Versión</span><span class="sxs-lookup"><span data-stu-id="a71ca-109">Version</span></span>|<span data-ttu-id="a71ca-110">4.7.1</span><span class="sxs-lookup"><span data-stu-id="a71ca-110">4.7.1</span></span>|
|<span data-ttu-id="a71ca-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="a71ca-111">Type</span></span>|<span data-ttu-id="a71ca-112">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="a71ca-112">Runtime</span></span>|
