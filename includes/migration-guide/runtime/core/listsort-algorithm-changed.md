---
ms.openlocfilehash: 09bd2c6312493f8b6369d05d8f1c4e88e4c05ece
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496196"
---
### <a name="listsort-algorithm-changed"></a><span data-ttu-id="e05f6-101">El algoritmo List.Sort ha cambiado</span><span class="sxs-lookup"><span data-stu-id="e05f6-101">List.Sort algorithm changed</span></span>

#### <a name="details"></a><span data-ttu-id="e05f6-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="e05f6-102">Details</span></span>

<span data-ttu-id="e05f6-103">A partir de .NET Framework 4.5, se ha cambiado el algoritmo de ordenación de <xref:System.Collections.Generic.List%601?displayProperty=fullName> (para que sea una ordenación introspectiva en lugar de una ordenación rápida).</span><span class="sxs-lookup"><span data-stu-id="e05f6-103">Beginning in .NET Framework 4.5, <xref:System.Collections.Generic.List%601?displayProperty=fullName>'s sort algorithm has changed (to be an introspective sort instead of a quick sort).</span></span> <span data-ttu-id="e05f6-104">La ordenación de <xref:System.Collections.Generic.List%601?displayProperty=fullName> nunca ha sido estable, pero este cambio puede provocar que otros escenarios se ordenen de maneras inestables.</span><span class="sxs-lookup"><span data-stu-id="e05f6-104"><xref:System.Collections.Generic.List%601?displayProperty=fullName>'s sort has never been stable, but this change may cause different scenarios to sort in unstable ways.</span></span> <span data-ttu-id="e05f6-105">Esto simplemente significa que los elementos equivalentes se pueden ordenar de otra forma en las llamadas posteriores de la API.</span><span class="sxs-lookup"><span data-stu-id="e05f6-105">That simply means that equivalent items may sort in different orders in subsequent calls of the API.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="e05f6-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="e05f6-106">Suggestion</span></span>

<span data-ttu-id="e05f6-107">Como el algoritmo de ordenación anterior también era inestable (aunque de forma ligeramente distinta), no debería haber código que dependa de que los elementos equivalentes se ordenen siempre en un orden concreto.</span><span class="sxs-lookup"><span data-stu-id="e05f6-107">Because the old sort algorithm was also unstable (though in slightly different ways), there should be no code that depends on equivalent items always sorting in a particular order.</span></span> <span data-ttu-id="e05f6-108">Si hay instancias de código que dependan de eso y de tener suerte con el comportamiento anterior, ese código se debe actualizar para que use un comparador que ordene de forma determinista los elementos en el orden deseado.</span><span class="sxs-lookup"><span data-stu-id="e05f6-108">If there are instances of code depending upon that and being lucky with the old behavior, that code should be updated to use a comparer that will deterministically sort the items in the desired order.</span></span>

| <span data-ttu-id="e05f6-109">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="e05f6-109">Name</span></span>    | <span data-ttu-id="e05f6-110">Valor</span><span class="sxs-lookup"><span data-stu-id="e05f6-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e05f6-111">Ámbito</span><span class="sxs-lookup"><span data-stu-id="e05f6-111">Scope</span></span>   |<span data-ttu-id="e05f6-112">Transparente</span><span class="sxs-lookup"><span data-stu-id="e05f6-112">Transparent</span></span>|
|<span data-ttu-id="e05f6-113">Versión</span><span class="sxs-lookup"><span data-stu-id="e05f6-113">Version</span></span>|<span data-ttu-id="e05f6-114">4.5</span><span class="sxs-lookup"><span data-stu-id="e05f6-114">4.5</span></span>|
|<span data-ttu-id="e05f6-115">Tipo</span><span class="sxs-lookup"><span data-stu-id="e05f6-115">Type</span></span>|<span data-ttu-id="e05f6-116">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="e05f6-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="e05f6-117">API afectadas</span><span class="sxs-lookup"><span data-stu-id="e05f6-117">Affected APIs</span></span>

- <xref:System.Collections.Generic.List%601.Sort?displayProperty=nameWithType>
- <xref:System.Collections.Generic.List%601.Sort(System.Collections.Generic.IComparer{%600})?displayProperty=nameWithType>
- <xref:System.Collections.Generic.List%601.Sort(System.Comparison{%600})?displayProperty=nameWithType>
- <xref:System.Collections.Generic.List%601.Sort(System.Int32,System.Int32,System.Collections.Generic.IComparer{%600})?displayProperty=nameWithType>

<!--

#### Affected APIs

- ``M:System.Collections.Generic.List`1.Sort``
- ``M:System.Collections.Generic.List`1.Sort(System.Collections.Generic.IComparer{`0})``
- ``M:System.Collections.Generic.List`1.Sort(System.Comparison{`0})``
- ``M:System.Collections.Generic.List`1.Sort(System.Int32,System.Int32,System.Collections.Generic.IComparer{`0})``

-->
