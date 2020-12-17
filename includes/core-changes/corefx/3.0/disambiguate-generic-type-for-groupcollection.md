---
ms.openlocfilehash: 97fab784acac4331894547eea27fc21b485597fb
ms.sourcegitcommit: fcbe432482464b1639decad78cc4dc8387c6269e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2020
ms.locfileid: "97366868"
---
### <a name="passing-groupcollection-to-extension-methods-taking-ienumerablet-requires-disambiguation"></a><span data-ttu-id="e8b86-101">El paso de GroupCollection a métodos de extensión que toman IEnumerable\<T> requiere desambiguación</span><span class="sxs-lookup"><span data-stu-id="e8b86-101">Passing GroupCollection to extension methods taking IEnumerable\<T> requires disambiguation</span></span>

<span data-ttu-id="e8b86-102">Al llamar a un método de extensión que toma `IEnumerable<T>` en un elemento <xref:System.Text.RegularExpressions.GroupCollection>, se debe eliminar la ambigüedad del tipo mediante una conversión.</span><span class="sxs-lookup"><span data-stu-id="e8b86-102">When calling an extension method that takes an `IEnumerable<T>` on a <xref:System.Text.RegularExpressions.GroupCollection>, you must disambiguate the type using a cast.</span></span>

#### <a name="change-description"></a><span data-ttu-id="e8b86-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="e8b86-103">Change description</span></span>

<span data-ttu-id="e8b86-104">A partir de .NET Core 3.0, <xref:System.Text.RegularExpressions.GroupCollection?displayProperty=nameWithType> implementa `IEnumerable<KeyValuePair<String,Group>>`, además de los otros tipos que implementa, incluido `IEnumerable<Group>`.</span><span class="sxs-lookup"><span data-stu-id="e8b86-104">Starting in .NET Core 3.0, <xref:System.Text.RegularExpressions.GroupCollection?displayProperty=nameWithType> implements `IEnumerable<KeyValuePair<String,Group>>` in addition to the other types it implements, including `IEnumerable<Group>`.</span></span> <span data-ttu-id="e8b86-105">Esto produce ambigüedad al llamar a un método de extensión que toma un elemento <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="e8b86-105">This results in ambiguity when calling an extension method that takes an <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="e8b86-106">Si llama a un método de extensión como este en una instancia de <xref:System.Text.RegularExpressions.GroupCollection>, por ejemplo, <xref:System.Linq.Enumerable.Count%2A?displayProperty=nameWithType>, verá el error del compilador siguiente:</span><span class="sxs-lookup"><span data-stu-id="e8b86-106">If you call such an extension method on a <xref:System.Text.RegularExpressions.GroupCollection> instance, for example, <xref:System.Linq.Enumerable.Count%2A?displayProperty=nameWithType>, you'll see the following compiler error:</span></span>

<span data-ttu-id="e8b86-107">**CS1061: "GroupCollection" no contiene una definición para "Count" ni se encuentra ningún método de extensión accesible "Count" que acepte un primer argumento del tipo "GroupCollection" (¿falta una directiva de uso o una referencia de ensamblado?)** .</span><span class="sxs-lookup"><span data-stu-id="e8b86-107">**CS1061: 'GroupCollection' does not contain a definition for 'Count' and no accessible extension method 'Count' accepting a first argument of type 'GroupCollection' could be found (are you missing a using directive or an assembly reference?)**</span></span>

<span data-ttu-id="e8b86-108">En versiones anteriores de .NET, no había ambigüedad ni ningún error del compilador.</span><span class="sxs-lookup"><span data-stu-id="e8b86-108">In previous versions of .NET, there was no ambiguity and no compiler error.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e8b86-109">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="e8b86-109">Version introduced</span></span>

<span data-ttu-id="e8b86-110">3.0</span><span class="sxs-lookup"><span data-stu-id="e8b86-110">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="e8b86-111">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="e8b86-111">Reason for change</span></span>

<span data-ttu-id="e8b86-112">Se trató de un [cambio importante involuntario](https://github.com/dotnet/corefx/pull/30077).</span><span class="sxs-lookup"><span data-stu-id="e8b86-112">This was an [unintentional breaking change](https://github.com/dotnet/corefx/pull/30077).</span></span> <span data-ttu-id="e8b86-113">Dado que no es algo nuevo de ahora, no tenemos previsto revertirlo.</span><span class="sxs-lookup"><span data-stu-id="e8b86-113">Because it has been like this for some time, we don't plan to revert it.</span></span> <span data-ttu-id="e8b86-114">Además, un cambio de este tipo sería importante en sí mismo.</span><span class="sxs-lookup"><span data-stu-id="e8b86-114">In addition, such a change would itself be breaking.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e8b86-115">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="e8b86-115">Recommended action</span></span>

<span data-ttu-id="e8b86-116">En el caso de instancias de <xref:System.Text.RegularExpressions.GroupCollection>, elimine la ambigüedad de las llamadas a métodos de extensión que aceptan un elemento `IEnumerable<T>` con una conversión.</span><span class="sxs-lookup"><span data-stu-id="e8b86-116">For <xref:System.Text.RegularExpressions.GroupCollection> instances, disambiguate calls to extension methods that accept an `IEnumerable<T>` with a cast.</span></span>

```csharp
// Without a cast - causes CS1061.
match.Groups.Count(_ => true)

// With a disambiguating cast.
((IEnumerable<Group>)m.Groups).Count(_ => true);
```

#### <a name="category"></a><span data-ttu-id="e8b86-117">Categoría</span><span class="sxs-lookup"><span data-stu-id="e8b86-117">Category</span></span>

<span data-ttu-id="e8b86-118">Bibliotecas de Core .NET</span><span class="sxs-lookup"><span data-stu-id="e8b86-118">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e8b86-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="e8b86-119">Affected APIs</span></span>

<span data-ttu-id="e8b86-120">Los métodos de extensión que aceptan un elemento <xref:System.Collections.Generic.IEnumerable%601> se ven afectados.</span><span class="sxs-lookup"><span data-stu-id="e8b86-120">Any extension method that accepts an <xref:System.Collections.Generic.IEnumerable%601> is affected.</span></span> <span data-ttu-id="e8b86-121">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e8b86-121">For example:</span></span>

- <xref:System.Collections.Immutable.ImmutableArray.ToImmutableArray%60%601(System.Collections.Generic.IEnumerable{%60%600})?displayProperty=fullName>
- <xref:System.Collections.Immutable.ImmutableDictionary.ToImmutableDictionary%2A?displayProperty=fullName>
- <xref:System.Collections.Immutable.ImmutableHashSet.ToImmutableHashSet%2A?displayProperty=fullName>
- <xref:System.Collections.Immutable.ImmutableList.ToImmutableList%60%601(System.Collections.Generic.IEnumerable{%60%600})?displayProperty=fullName>
- <xref:System.Collections.Immutable.ImmutableSortedDictionary.ToImmutableSortedDictionary%2A?displayProperty=fullName>
- <xref:System.Collections.Immutable.ImmutableSortedSet.ToImmutableSortedSet%2A?displayProperty=fullName>
- <xref:System.Data.DataTableExtensions.CopyToDataTable%2A?displayProperty=fullName>
- <span data-ttu-id="e8b86-122">Gran parte de los métodos `System.Linq.Enumerable`, por ejemplo, <xref:System.Linq.Enumerable.Count%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="e8b86-122">Most of the `System.Linq.Enumerable` methods, for example, <xref:System.Linq.Enumerable.Count%2A?displayProperty=fullName></span></span>
- <xref:System.Linq.ParallelEnumerable.AsParallel%2A?displayProperty=fullName>
- <xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=fullName>

<!--

#### Affected APIs

- ``M:System.Collections.Immutable.ImmutableArray.ToImmutableArray``1(System.Collections.Generic.IEnumerable{``0})``
- `Overload:System.Collections.Immutable.ImmutableDictionary.ToImmutableDictionary`
- `Overload:System.Collections.Immutable.ImmutableHashSet.ToImmutableHashSet`
- ``M:System.Collections.Immutable.ImmutableList.ToImmutableList``1(System.Collections.Generic.IEnumerable{``0})``
- `Overload:System.Collections.Immutable.ImmutableSortedDictionary.ToImmutableSortedDictionary`
- `Overload:System.Collections.Immutable.ImmutableSortedSet.ToImmutableSortedSet`
- `Overload:System.Data.DataTableExtensions.CopyToDataTable`
- `Overload:System.Linq.Enumerable.Count`
- `Overload:System.Linq.ParallelEnumerable.AsParallel`
- `Overload:System.Linq.Queryable.AsQueryable`

-->
