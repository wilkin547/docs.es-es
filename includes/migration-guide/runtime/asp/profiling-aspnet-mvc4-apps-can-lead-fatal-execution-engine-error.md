---
ms.openlocfilehash: 439a4976482639cd2e4e17315ec1a53ca54aa477
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "67803158"
---
### <a name="profiling-aspnet-mvc4-apps-can-lead-to-fatal-execution-engine-error"></a><span data-ttu-id="1d4f1-101">Las aplicaciones de MVC4 de generación de perfiles de ASP.NET pueden provocar el error irrecuperable de motor de ejecución</span><span class="sxs-lookup"><span data-stu-id="1d4f1-101">Profiling ASP.Net MVC4 apps can lead to Fatal Execution Engine Error</span></span>

|   |   |
|---|---|
|<span data-ttu-id="1d4f1-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="1d4f1-102">Details</span></span>|<span data-ttu-id="1d4f1-103">Los generadores de perfiles que usan ensamblados /Profile de NGEN pueden bloquear las aplicaciones de MVC4 con perfiles de ASP.NET durante el inicio con una "Excepción irrecuperable de motor de ejecución".</span><span class="sxs-lookup"><span data-stu-id="1d4f1-103">Profilers using NGEN /Profile assemblies may crash profiled ASP.NET MVC4 applications on startup with a 'Fatal Execution Engine Exception'</span></span>|
|<span data-ttu-id="1d4f1-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="1d4f1-104">Suggestion</span></span>|<span data-ttu-id="1d4f1-105">Este problema se ha corregido en .NET Framework 4.5.2.</span><span class="sxs-lookup"><span data-stu-id="1d4f1-105">This issue is fixed in the .NET Framework 4.5.2.</span></span> <span data-ttu-id="1d4f1-106">Como alternativa, el generador de perfiles puede evitar este problema mediante la especificación de <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> en su máscara de eventos.</span><span class="sxs-lookup"><span data-stu-id="1d4f1-106">Alternatively, the profiler may avoid this issue by specifying <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> in its event mask.</span></span>|
|<span data-ttu-id="1d4f1-107">Ámbito</span><span class="sxs-lookup"><span data-stu-id="1d4f1-107">Scope</span></span>|<span data-ttu-id="1d4f1-108">Borde</span><span class="sxs-lookup"><span data-stu-id="1d4f1-108">Edge</span></span>|
|<span data-ttu-id="1d4f1-109">Versión</span><span class="sxs-lookup"><span data-stu-id="1d4f1-109">Version</span></span>|<span data-ttu-id="1d4f1-110">4.5</span><span class="sxs-lookup"><span data-stu-id="1d4f1-110">4.5</span></span>|
|<span data-ttu-id="1d4f1-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="1d4f1-111">Type</span></span>|<span data-ttu-id="1d4f1-112">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="1d4f1-112">Runtime</span></span>|
