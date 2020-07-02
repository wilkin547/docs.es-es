---
ms.openlocfilehash: 9131c91b34f4c24653dea37ea39af6be6e072287
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620632"
---
### <a name="enumerableemptylttresultgt-always-returns-cached-instance"></a><span data-ttu-id="6a2cf-101">Enumerable.Empty&lt;TResult&gt; siempre devuelve una instancia almacenada en caché</span><span class="sxs-lookup"><span data-stu-id="6a2cf-101">Enumerable.Empty&lt;TResult&gt; always returns cached instance</span></span>

#### <a name="details"></a><span data-ttu-id="6a2cf-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="6a2cf-102">Details</span></span>

<span data-ttu-id="6a2cf-103">A partir de .NET Framework 4.5, <xref:System.Linq.Enumerable.Empty%60%601> siempre devuelve una instancia interna de <xref:System.Collections.Generic.IEnumerable%601> en caché. Anteriormente, <xref:System.Linq.Enumerable.Empty%60%601> almacenaba en caché un <xref:System.Collections.Generic.IEnumerable%601> vacío en el momento de llamar a la API, lo que significa que, en algunas condiciones en las que se llamaba a <xref:System.Linq.Enumerable.Empty%60%601> de forma rápida y simultánea, se podían devolver otras instancias del tipo para otras llamadas a la API.</span><span class="sxs-lookup"><span data-stu-id="6a2cf-103">Beginning in .NET Framework 4.5, <xref:System.Linq.Enumerable.Empty%60%601> always returns a cached internal instance <xref:System.Collections.Generic.IEnumerable%601>.Previously, <xref:System.Linq.Enumerable.Empty%60%601> would cache an empty <xref:System.Collections.Generic.IEnumerable%601> at the time the API was called, meaning that in some conditions in which <xref:System.Linq.Enumerable.Empty%60%601> was called rapidly and concurrently, different instances of the type could be returned for different calls to the API.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="6a2cf-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="6a2cf-104">Suggestion</span></span>

<span data-ttu-id="6a2cf-105">Puesto que el comportamiento anterior no era determinista, es poco probable que el código dependa de él.</span><span class="sxs-lookup"><span data-stu-id="6a2cf-105">Because the previous behavior was non-deterministic, code is unlikely to depend on it.</span></span> <span data-ttu-id="6a2cf-106">No obstante, en el improbable caso de que se comparen enumerables vacíos y que se espere que a veces sean distintos, deberían crearse matrices vacías explícitas (<code>new T[0]</code>) en lugar de usar <xref:System.Linq.Enumerable.Empty%60%601>.</span><span class="sxs-lookup"><span data-stu-id="6a2cf-106">However, in the unlikely case that empty enumerables are being compared and expected to sometimes be unequal, explicit empty arrays should be created (<code>new T[0]</code>) instead of using <xref:System.Linq.Enumerable.Empty%60%601>.</span></span>

| <span data-ttu-id="6a2cf-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="6a2cf-107">Name</span></span>    | <span data-ttu-id="6a2cf-108">Valor</span><span class="sxs-lookup"><span data-stu-id="6a2cf-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6a2cf-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="6a2cf-109">Scope</span></span>   |<span data-ttu-id="6a2cf-110">Borde</span><span class="sxs-lookup"><span data-stu-id="6a2cf-110">Edge</span></span>|
|<span data-ttu-id="6a2cf-111">Versión</span><span class="sxs-lookup"><span data-stu-id="6a2cf-111">Version</span></span>|<span data-ttu-id="6a2cf-112">4.5</span><span class="sxs-lookup"><span data-stu-id="6a2cf-112">4.5</span></span>|
|<span data-ttu-id="6a2cf-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="6a2cf-113">Type</span></span>|<span data-ttu-id="6a2cf-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="6a2cf-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="6a2cf-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="6a2cf-115">Affected APIs</span></span>

-<xref:System.Linq.Enumerable.Empty%60%601?displayProperty=nameWithType></li></ul>|
