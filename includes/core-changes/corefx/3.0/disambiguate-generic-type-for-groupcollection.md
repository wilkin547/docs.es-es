---
ms.openlocfilehash: 97fab784acac4331894547eea27fc21b485597fb
ms.sourcegitcommit: fcbe432482464b1639decad78cc4dc8387c6269e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2020
ms.locfileid: "97366868"
---
### <a name="passing-groupcollection-to-extension-methods-taking-ienumerablet-requires-disambiguation"></a>El paso de GroupCollection a métodos de extensión que toman IEnumerable\<T> requiere desambiguación

Al llamar a un método de extensión que toma `IEnumerable<T>` en un elemento <xref:System.Text.RegularExpressions.GroupCollection>, se debe eliminar la ambigüedad del tipo mediante una conversión.

#### <a name="change-description"></a>Descripción del cambio

A partir de .NET Core 3.0, <xref:System.Text.RegularExpressions.GroupCollection?displayProperty=nameWithType> implementa `IEnumerable<KeyValuePair<String,Group>>`, además de los otros tipos que implementa, incluido `IEnumerable<Group>`. Esto produce ambigüedad al llamar a un método de extensión que toma un elemento <xref:System.Collections.Generic.IEnumerable%601>. Si llama a un método de extensión como este en una instancia de <xref:System.Text.RegularExpressions.GroupCollection>, por ejemplo, <xref:System.Linq.Enumerable.Count%2A?displayProperty=nameWithType>, verá el error del compilador siguiente:

**CS1061: "GroupCollection" no contiene una definición para "Count" ni se encuentra ningún método de extensión accesible "Count" que acepte un primer argumento del tipo "GroupCollection" (¿falta una directiva de uso o una referencia de ensamblado?)** .

En versiones anteriores de .NET, no había ambigüedad ni ningún error del compilador.

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="reason-for-change"></a>Motivo del cambio

Se trató de un [cambio importante involuntario](https://github.com/dotnet/corefx/pull/30077). Dado que no es algo nuevo de ahora, no tenemos previsto revertirlo. Además, un cambio de este tipo sería importante en sí mismo.

#### <a name="recommended-action"></a>Acción recomendada

En el caso de instancias de <xref:System.Text.RegularExpressions.GroupCollection>, elimine la ambigüedad de las llamadas a métodos de extensión que aceptan un elemento `IEnumerable<T>` con una conversión.

```csharp
// Without a cast - causes CS1061.
match.Groups.Count(_ => true)

// With a disambiguating cast.
((IEnumerable<Group>)m.Groups).Count(_ => true);
```

#### <a name="category"></a>Categoría

Bibliotecas de Core .NET

#### <a name="affected-apis"></a>API afectadas

Los métodos de extensión que aceptan un elemento <xref:System.Collections.Generic.IEnumerable%601> se ven afectados. Por ejemplo:

- <xref:System.Collections.Immutable.ImmutableArray.ToImmutableArray%60%601(System.Collections.Generic.IEnumerable{%60%600})?displayProperty=fullName>
- <xref:System.Collections.Immutable.ImmutableDictionary.ToImmutableDictionary%2A?displayProperty=fullName>
- <xref:System.Collections.Immutable.ImmutableHashSet.ToImmutableHashSet%2A?displayProperty=fullName>
- <xref:System.Collections.Immutable.ImmutableList.ToImmutableList%60%601(System.Collections.Generic.IEnumerable{%60%600})?displayProperty=fullName>
- <xref:System.Collections.Immutable.ImmutableSortedDictionary.ToImmutableSortedDictionary%2A?displayProperty=fullName>
- <xref:System.Collections.Immutable.ImmutableSortedSet.ToImmutableSortedSet%2A?displayProperty=fullName>
- <xref:System.Data.DataTableExtensions.CopyToDataTable%2A?displayProperty=fullName>
- Gran parte de los métodos `System.Linq.Enumerable`, por ejemplo, <xref:System.Linq.Enumerable.Count%2A?displayProperty=fullName>
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
