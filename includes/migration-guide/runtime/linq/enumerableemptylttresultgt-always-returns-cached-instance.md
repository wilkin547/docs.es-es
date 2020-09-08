---
ms.openlocfilehash: 05f60978f5380c406c43aa98ded0c812b1d50694
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496608"
---
### <a name="enumerableemptylttresultgt-always-returns-cached-instance"></a><span data-ttu-id="ed283-101">Enumerable.Empty&lt;TResult&gt; siempre devuelve una instancia almacenada en caché</span><span class="sxs-lookup"><span data-stu-id="ed283-101">Enumerable.Empty&lt;TResult&gt; always returns cached instance</span></span>

#### <a name="details"></a><span data-ttu-id="ed283-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="ed283-102">Details</span></span>

<span data-ttu-id="ed283-103">A partir de .NET Framework 4.5, <xref:System.Linq.Enumerable.Empty%60%601> siempre devuelve una instancia interna de <xref:System.Collections.Generic.IEnumerable%601> en caché. Anteriormente, <xref:System.Linq.Enumerable.Empty%60%601> almacenaba en caché un <xref:System.Collections.Generic.IEnumerable%601> vacío en el momento de llamar a la API, lo que significa que, en algunas condiciones en las que se llamaba a <xref:System.Linq.Enumerable.Empty%60%601> de forma rápida y simultánea, se podían devolver otras instancias del tipo para otras llamadas a la API.</span><span class="sxs-lookup"><span data-stu-id="ed283-103">Beginning in .NET Framework 4.5, <xref:System.Linq.Enumerable.Empty%60%601> always returns a cached internal instance <xref:System.Collections.Generic.IEnumerable%601>.Previously, <xref:System.Linq.Enumerable.Empty%60%601> would cache an empty <xref:System.Collections.Generic.IEnumerable%601> at the time the API was called, meaning that in some conditions in which <xref:System.Linq.Enumerable.Empty%60%601> was called rapidly and concurrently, different instances of the type could be returned for different calls to the API.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ed283-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="ed283-104">Suggestion</span></span>

<span data-ttu-id="ed283-105">Puesto que el comportamiento anterior no era determinista, es poco probable que el código dependa de él.</span><span class="sxs-lookup"><span data-stu-id="ed283-105">Because the previous behavior was non-deterministic, code is unlikely to depend on it.</span></span> <span data-ttu-id="ed283-106">No obstante, en el improbable caso de que se comparen enumerables vacíos y que se espere que a veces sean distintos, deberían crearse matrices vacías explícitas (<code>new T[0]</code>) en lugar de usar <xref:System.Linq.Enumerable.Empty%60%601>.</span><span class="sxs-lookup"><span data-stu-id="ed283-106">However, in the unlikely case that empty enumerables are being compared and expected to sometimes be unequal, explicit empty arrays should be created (<code>new T[0]</code>) instead of using <xref:System.Linq.Enumerable.Empty%60%601>.</span></span>

| <span data-ttu-id="ed283-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="ed283-107">Name</span></span>    | <span data-ttu-id="ed283-108">Valor</span><span class="sxs-lookup"><span data-stu-id="ed283-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ed283-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="ed283-109">Scope</span></span>   |<span data-ttu-id="ed283-110">Borde</span><span class="sxs-lookup"><span data-stu-id="ed283-110">Edge</span></span>|
|<span data-ttu-id="ed283-111">Versión</span><span class="sxs-lookup"><span data-stu-id="ed283-111">Version</span></span>|<span data-ttu-id="ed283-112">4.5</span><span class="sxs-lookup"><span data-stu-id="ed283-112">4.5</span></span>|
|<span data-ttu-id="ed283-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="ed283-113">Type</span></span>|<span data-ttu-id="ed283-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="ed283-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="ed283-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="ed283-115">Affected APIs</span></span>

- <xref:System.Linq.Enumerable.Empty%60%601?displayProperty=nameWithType>

<!--

#### Affected APIs

- ``M:System.Linq.Enumerable.Empty``1``

-->
