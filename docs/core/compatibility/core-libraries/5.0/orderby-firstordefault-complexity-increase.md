---
title: 'Cambio importante: Aumento de la complejidad de LINQ OrderBy.First{OrDefault}'
description: Obtenga información sobre el cambio importante de .NET 5 en las bibliotecas básicas de .NET donde ha cambiado la implementación de OrderBy.First.
ms.date: 11/01/2020
ms.openlocfilehash: 4cd2dda5f60976f935505d6a6cb1e4c23d150d09
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257276"
---
# <a name="complexity-of-linq-orderbyfirstordefault-increased"></a><span data-ttu-id="a5d3d-103">Aumento de la complejidad de LINQ OrderBy.First{OrDefault}</span><span class="sxs-lookup"><span data-stu-id="a5d3d-103">Complexity of LINQ OrderBy.First{OrDefault} increased</span></span>

<span data-ttu-id="a5d3d-104">La implementación de <xref:System.Linq.Enumerable.OrderBy%2A>`.`<xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> y <xref:System.Linq.Enumerable.OrderBy%2A>`.`<xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> ha cambiado, lo que aumenta la complejidad de la operación.</span><span class="sxs-lookup"><span data-stu-id="a5d3d-104">The implementation of <xref:System.Linq.Enumerable.OrderBy%2A>`.`<xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> and <xref:System.Linq.Enumerable.OrderBy%2A>`.`<xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> has changed, resulting in increased complexity for the operation.</span></span>

## <a name="change-description"></a><span data-ttu-id="a5d3d-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="a5d3d-105">Change description</span></span>

<span data-ttu-id="a5d3d-106">Entre las versiones 1.x y 3.x de .NET Core, llamar a <xref:System.Linq.Enumerable.OrderBy%2A> o <xref:System.Linq.Enumerable.OrderByDescending%2A> seguido de <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> o <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> funciona con complejidad `O(N)`.</span><span class="sxs-lookup"><span data-stu-id="a5d3d-106">In .NET Core 1.x - 3.x, calling <xref:System.Linq.Enumerable.OrderBy%2A> or <xref:System.Linq.Enumerable.OrderByDescending%2A> followed by <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> or <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> operates with `O(N)` complexity.</span></span> <span data-ttu-id="a5d3d-107">Puesto que solo se requiere el primer elemento (o el predeterminado), solo se necesitaría una enumeración para encontrarlo.</span><span class="sxs-lookup"><span data-stu-id="a5d3d-107">Since only the first (or default) element is required, only one enumeration is required to find it.</span></span> <span data-ttu-id="a5d3d-108">Sin embargo, el predicado que se proporciona a <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> o <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> se invoca exactamente `N` veces, donde `N` es la longitud de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="a5d3d-108">However, the predicate that's supplied to <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> or <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> is invoked exactly `N` times, where `N` is the length of the sequence.</span></span>

<span data-ttu-id="a5d3d-109">En .NET 5 y versiones posteriores, se [implementó un cambio](https://github.com/dotnet/runtime/pull/36643) con el que llamar a <xref:System.Linq.Enumerable.OrderBy%2A> o <xref:System.Linq.Enumerable.OrderByDescending%2A> seguido de <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> o <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> funcionar con complejidad `O(N log N)` en lugar de con complejidad `O(N)`.</span><span class="sxs-lookup"><span data-stu-id="a5d3d-109">In .NET 5 and later versions, a [change was made](https://github.com/dotnet/runtime/pull/36643) such that calling <xref:System.Linq.Enumerable.OrderBy%2A> or <xref:System.Linq.Enumerable.OrderByDescending%2A> followed by <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> or <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> operates with `O(N log N)` complexity instead of `O(N)` complexity.</span></span> <span data-ttu-id="a5d3d-110">Sin embargo, el predicado que se proporciona a <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> o <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> se puede invocar *menos* de `N` veces, lo cual es más importante para el rendimiento general.</span><span class="sxs-lookup"><span data-stu-id="a5d3d-110">However, the predicate that's supplied to <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> or <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> may be invoked *less* than `N` times, which is more important for overall performance.</span></span>

> [!NOTE]
> <span data-ttu-id="a5d3d-111">Este cambio coincide con la implementación y la complejidad de la operación en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a5d3d-111">This change matches the implementation and complexity of the operation in .NET Framework.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="a5d3d-112">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="a5d3d-112">Reason for change</span></span>

<span data-ttu-id="a5d3d-113">La ventaja de invocar menos veces el predicado es superior a una complejidad general menor, por lo que se revirtió la implementación que se presentó en .NET Core 1.0.</span><span class="sxs-lookup"><span data-stu-id="a5d3d-113">The benefit of invoking the predicate fewer times outweighs a lower overall complexity, so the implementation that was introduced in .NET Core 1.0 was reverted.</span></span> <span data-ttu-id="a5d3d-114">Para obtener más información, vea [este problema de dotnet/runtime](https://github.com/dotnet/runtime/issues/31554).</span><span class="sxs-lookup"><span data-stu-id="a5d3d-114">For more information, see [this dotnet/runtime issue](https://github.com/dotnet/runtime/issues/31554).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="a5d3d-115">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="a5d3d-115">Version introduced</span></span>

<span data-ttu-id="a5d3d-116">5.0</span><span class="sxs-lookup"><span data-stu-id="a5d3d-116">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="a5d3d-117">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="a5d3d-117">Recommended action</span></span>

<span data-ttu-id="a5d3d-118">No se requiere ninguna acción por parte del desarrollador.</span><span class="sxs-lookup"><span data-stu-id="a5d3d-118">No action is required on the developer's part.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="a5d3d-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="a5d3d-119">Affected APIs</span></span>

- <xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=fullName>
- <xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=fullName>
- <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})?displayProperty=fullName>
- <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `Overload:System.Linq.Enumerable.OrderBy`
- `Overload:System.Linq.Enumerable.OrderByDescending`
- `M:System.Linq.Enumerable.First``1(System.Collections.Generic.IEnumerable{``0},System.Func{``0,System.Boolean})`
- `M:System.Linq.Enumerable.FirstOrDefault``1(System.Collections.Generic.IEnumerable{``0},System.Func{``0,System.Boolean})`

-->
