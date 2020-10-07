---
ms.openlocfilehash: 8b70df0fb2072fd5243d9e46a4a20c22cc7fd677
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "91607802"
---
### <a name="profiling-aspnet-mvc4-apps-can-lead-to-fatal-execution-engine-error"></a><span data-ttu-id="6de2b-101">Posible error irrecuperable en el motor de ejecución por parte de las aplicaciones de MVC4 de generación de perfiles de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="6de2b-101">Profiling ASP.NET MVC4 apps can lead to Fatal Execution Engine Error</span></span>

#### <a name="details"></a><span data-ttu-id="6de2b-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="6de2b-102">Details</span></span>

<span data-ttu-id="6de2b-103">Los generadores de perfiles que usan ensamblados /Profile de NGEN pueden bloquear las aplicaciones de MVC4 con perfiles de ASP.NET durante el inicio con una "Excepción irrecuperable de motor de ejecución".</span><span class="sxs-lookup"><span data-stu-id="6de2b-103">Profilers using NGEN /Profile assemblies may crash profiled ASP.NET MVC4 applications on startup with a 'Fatal Execution Engine Exception'</span></span>

#### <a name="suggestion"></a><span data-ttu-id="6de2b-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="6de2b-104">Suggestion</span></span>

<span data-ttu-id="6de2b-105">Este problema se ha corregido en .NET Framework 4.5.2.</span><span class="sxs-lookup"><span data-stu-id="6de2b-105">This issue is fixed in the .NET Framework 4.5.2.</span></span> <span data-ttu-id="6de2b-106">Como alternativa, el generador de perfiles puede evitar este problema mediante la especificación de <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> en su máscara de eventos.</span><span class="sxs-lookup"><span data-stu-id="6de2b-106">Alternatively, the profiler may avoid this issue by specifying <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> in its event mask.</span></span>

| <span data-ttu-id="6de2b-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="6de2b-107">Name</span></span>    | <span data-ttu-id="6de2b-108">Valor</span><span class="sxs-lookup"><span data-stu-id="6de2b-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6de2b-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="6de2b-109">Scope</span></span>   |<span data-ttu-id="6de2b-110">Borde</span><span class="sxs-lookup"><span data-stu-id="6de2b-110">Edge</span></span>|
|<span data-ttu-id="6de2b-111">Versión</span><span class="sxs-lookup"><span data-stu-id="6de2b-111">Version</span></span>|<span data-ttu-id="6de2b-112">4.5</span><span class="sxs-lookup"><span data-stu-id="6de2b-112">4.5</span></span>|
|<span data-ttu-id="6de2b-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="6de2b-113">Type</span></span>|<span data-ttu-id="6de2b-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="6de2b-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="6de2b-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="6de2b-115">Affected APIs</span></span>

<span data-ttu-id="6de2b-116">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="6de2b-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
