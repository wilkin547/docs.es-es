---
ms.openlocfilehash: 9dada93c3330331064b7a944d97d61edb4dea299
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620581"
---
### <a name="listsort-algorithm-changed"></a><span data-ttu-id="82078-101">El algoritmo List.Sort ha cambiado</span><span class="sxs-lookup"><span data-stu-id="82078-101">List.Sort algorithm changed</span></span>

#### <a name="details"></a><span data-ttu-id="82078-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="82078-102">Details</span></span>

<span data-ttu-id="82078-103">A partir de .NET Framework 4.5, se ha cambiado el algoritmo de ordenación de <xref:System.Collections.Generic.List%601?displayProperty=fullName> (para que sea una ordenación introspectiva en lugar de una ordenación rápida).</span><span class="sxs-lookup"><span data-stu-id="82078-103">Beginning in .NET Framework 4.5, <xref:System.Collections.Generic.List%601?displayProperty=fullName>'s sort algorithm has changed (to be an introspective sort instead of a quick sort).</span></span> <span data-ttu-id="82078-104">La ordenación de <xref:System.Collections.Generic.List%601?displayProperty=fullName> nunca ha sido estable, pero este cambio puede provocar que otros escenarios se ordenen de maneras inestables.</span><span class="sxs-lookup"><span data-stu-id="82078-104"><xref:System.Collections.Generic.List%601?displayProperty=fullName>'s sort has never been stable, but this change may cause different scenarios to sort in unstable ways.</span></span> <span data-ttu-id="82078-105">Esto simplemente significa que los elementos equivalentes se pueden ordenar de otra forma en las llamadas posteriores de la API.</span><span class="sxs-lookup"><span data-stu-id="82078-105">That simply means that equivalent items may sort in different orders in subsequent calls of the API.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="82078-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="82078-106">Suggestion</span></span>

<span data-ttu-id="82078-107">Como el algoritmo de ordenación anterior también era inestable (aunque de forma ligeramente distinta), no debería haber código que dependa de que los elementos equivalentes se ordenen siempre en un orden concreto.</span><span class="sxs-lookup"><span data-stu-id="82078-107">Because the old sort algorithm was also unstable (though in slightly different ways), there should be no code that depends on equivalent items always sorting in a particular order.</span></span> <span data-ttu-id="82078-108">Si hay instancias de código que dependan de eso y de tener suerte con el comportamiento anterior, ese código se debe actualizar para que use un comparador que ordene de forma determinista los elementos en el orden deseado.</span><span class="sxs-lookup"><span data-stu-id="82078-108">If there are instances of code depending upon that and being lucky with the old behavior, that code should be updated to use a comparer that will deterministically sort the items in the desired order.</span></span>

| <span data-ttu-id="82078-109">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="82078-109">Name</span></span>    | <span data-ttu-id="82078-110">Valor</span><span class="sxs-lookup"><span data-stu-id="82078-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="82078-111">Ámbito</span><span class="sxs-lookup"><span data-stu-id="82078-111">Scope</span></span>   |<span data-ttu-id="82078-112">Transparente</span><span class="sxs-lookup"><span data-stu-id="82078-112">Transparent</span></span>|
|<span data-ttu-id="82078-113">Versión</span><span class="sxs-lookup"><span data-stu-id="82078-113">Version</span></span>|<span data-ttu-id="82078-114">4.5</span><span class="sxs-lookup"><span data-stu-id="82078-114">4.5</span></span>|
|<span data-ttu-id="82078-115">Tipo</span><span class="sxs-lookup"><span data-stu-id="82078-115">Type</span></span>|<span data-ttu-id="82078-116">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="82078-116">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="82078-117">API afectadas</span><span class="sxs-lookup"><span data-stu-id="82078-117">Affected APIs</span></span>

-<xref:System.Collections.Generic.List%601.Sort?displayProperty=nameWithType></li><li><xref:System.Collections.Generic.List%601.Sort(System.Collections.Generic.IComparer{%600})?displayProperty=nameWithType></li><li><xref:System.Collections.Generic.List%601.Sort(System.Comparison{%600})?displayProperty=nameWithType></li><li><xref:System.Collections.Generic.List%601.Sort(System.Int32,System.Int32,System.Collections.Generic.IComparer{%600})?displayProperty=nameWithType></li></ul>|
