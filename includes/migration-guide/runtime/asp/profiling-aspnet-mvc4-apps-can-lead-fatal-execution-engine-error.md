---
ms.openlocfilehash: 439a4976482639cd2e4e17315ec1a53ca54aa477
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235834"
---
### <a name="profiling-aspnet-mvc4-apps-can-lead-to-fatal-execution-engine-error"></a><span data-ttu-id="aabc9-101">Las aplicaciones de MVC4 de generación de perfiles de ASP.NET pueden provocar el error irrecuperable de motor de ejecución</span><span class="sxs-lookup"><span data-stu-id="aabc9-101">Profiling ASP.Net MVC4 apps can lead to Fatal Execution Engine Error</span></span>

|   |   |
|---|---|
|<span data-ttu-id="aabc9-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="aabc9-102">Details</span></span>|<span data-ttu-id="aabc9-103">Los generadores de perfiles que usan ensamblados /Profile de NGEN pueden bloquear las aplicaciones de MVC4 con perfiles de ASP.NET durante el inicio con una "Excepción irrecuperable de motor de ejecución".</span><span class="sxs-lookup"><span data-stu-id="aabc9-103">Profilers using NGEN /Profile assemblies may crash profiled ASP.NET MVC4 applications on startup with a 'Fatal Execution Engine Exception'</span></span>|
|<span data-ttu-id="aabc9-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="aabc9-104">Suggestion</span></span>|<span data-ttu-id="aabc9-105">Este problema se ha corregido en .NET Framework 4.5.2.</span><span class="sxs-lookup"><span data-stu-id="aabc9-105">This issue is fixed in the .NET Framework 4.5.2.</span></span> <span data-ttu-id="aabc9-106">Como alternativa, el generador de perfiles puede evitar este problema mediante la especificación de <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> en su máscara de eventos.</span><span class="sxs-lookup"><span data-stu-id="aabc9-106">Alternatively, the profiler may avoid this issue by specifying <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> in its event mask.</span></span>|
|<span data-ttu-id="aabc9-107">Ámbito</span><span class="sxs-lookup"><span data-stu-id="aabc9-107">Scope</span></span>|<span data-ttu-id="aabc9-108">Borde</span><span class="sxs-lookup"><span data-stu-id="aabc9-108">Edge</span></span>|
|<span data-ttu-id="aabc9-109">Versión</span><span class="sxs-lookup"><span data-stu-id="aabc9-109">Version</span></span>|<span data-ttu-id="aabc9-110">4.5</span><span class="sxs-lookup"><span data-stu-id="aabc9-110">4.5</span></span>|
|<span data-ttu-id="aabc9-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="aabc9-111">Type</span></span>|<span data-ttu-id="aabc9-112">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="aabc9-112">Runtime</span></span>|
