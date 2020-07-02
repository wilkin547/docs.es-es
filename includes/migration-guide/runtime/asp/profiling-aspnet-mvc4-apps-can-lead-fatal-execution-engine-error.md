---
ms.openlocfilehash: 2e13268d4983af5d2fdd6d12b4d9e67d61d07f3d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622131"
---
### <a name="profiling-aspnet-mvc4-apps-can-lead-to-fatal-execution-engine-error"></a><span data-ttu-id="20df2-101">Las aplicaciones de MVC4 de generación de perfiles de ASP.NET pueden provocar el error irrecuperable de motor de ejecución</span><span class="sxs-lookup"><span data-stu-id="20df2-101">Profiling ASP.Net MVC4 apps can lead to Fatal Execution Engine Error</span></span>

#### <a name="details"></a><span data-ttu-id="20df2-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="20df2-102">Details</span></span>

<span data-ttu-id="20df2-103">Los generadores de perfiles que usan ensamblados /Profile de NGEN pueden bloquear las aplicaciones de MVC4 con perfiles de ASP.NET durante el inicio con una "Excepción irrecuperable de motor de ejecución".</span><span class="sxs-lookup"><span data-stu-id="20df2-103">Profilers using NGEN /Profile assemblies may crash profiled ASP.NET MVC4 applications on startup with a 'Fatal Execution Engine Exception'</span></span>

#### <a name="suggestion"></a><span data-ttu-id="20df2-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="20df2-104">Suggestion</span></span>

<span data-ttu-id="20df2-105">Este problema se ha corregido en .NET Framework 4.5.2.</span><span class="sxs-lookup"><span data-stu-id="20df2-105">This issue is fixed in the .NET Framework 4.5.2.</span></span> <span data-ttu-id="20df2-106">Como alternativa, el generador de perfiles puede evitar este problema mediante la especificación de <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> en su máscara de eventos.</span><span class="sxs-lookup"><span data-stu-id="20df2-106">Alternatively, the profiler may avoid this issue by specifying <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> in its event mask.</span></span>

| <span data-ttu-id="20df2-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="20df2-107">Name</span></span>    | <span data-ttu-id="20df2-108">Valor</span><span class="sxs-lookup"><span data-stu-id="20df2-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="20df2-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="20df2-109">Scope</span></span>   |<span data-ttu-id="20df2-110">Borde</span><span class="sxs-lookup"><span data-stu-id="20df2-110">Edge</span></span>|
|<span data-ttu-id="20df2-111">Versión</span><span class="sxs-lookup"><span data-stu-id="20df2-111">Version</span></span>|<span data-ttu-id="20df2-112">4.5</span><span class="sxs-lookup"><span data-stu-id="20df2-112">4.5</span></span>|
|<span data-ttu-id="20df2-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="20df2-113">Type</span></span>|<span data-ttu-id="20df2-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="20df2-114">Runtime</span></span>|
