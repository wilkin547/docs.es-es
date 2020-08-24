---
ms.openlocfilehash: 950c69199219cca615e403c6515239de8864d35d
ms.sourcegitcommit: d3c09791297f0edc468a4849a5f11ef62e0e90fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2020
ms.locfileid: "88137482"
---
### <a name="complexity-of-linq-orderbyfirstordefault-increased"></a>Aumento de la complejidad de LINQ OrderBy.First{OrDefault}

La implementación de <xref:System.Linq.Enumerable.OrderBy%2A>`.`<xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> y <xref:System.Linq.Enumerable.OrderBy%2A>`.`<xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> ha cambiado, lo que aumenta la complejidad de la operación.

#### <a name="change-description"></a>Descripción del cambio

Entre las versiones 1.x y 3.x de .NET Core, llamar a <xref:System.Linq.Enumerable.OrderBy%2A> o <xref:System.Linq.Enumerable.OrderByDescending%2A> seguido de <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> o <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> funciona con complejidad `O(N)`. Puesto que solo se requiere el primer elemento (o el predeterminado), solo se necesitaría una enumeración para encontrarlo. Sin embargo, el predicado que se proporciona a <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> o <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> se invoca exactamente `N` veces, donde `N` es la longitud de la secuencia.

En .NET 5.0 y versiones posteriores, se [implementó un cambio](https://github.com/dotnet/runtime/pull/36643) con el que llamar a <xref:System.Linq.Enumerable.OrderBy%2A> o <xref:System.Linq.Enumerable.OrderByDescending%2A> seguido de <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> o <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> funcionar con complejidad `O(N log N)` en lugar de con complejidad `O(N)`. Sin embargo, el predicado que se proporciona a <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> o <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> se puede invocar *menos* de `N` veces, lo cual es más importante para el rendimiento general.

> [!NOTE]
> Este cambio coincide con la implementación y la complejidad de la operación en .NET Framework.

#### <a name="reason-for-change"></a>Motivo del cambio

La ventaja de invocar menos veces el predicado es superior a una complejidad general menor, por lo que se revirtió la implementación que se presentó en .NET Core 1.0. Para obtener más información, vea [este problema de dotnet/runtime](https://github.com/dotnet/runtime/issues/31554).

#### <a name="version-introduced"></a>Versión introducida

5.0

#### <a name="recommended-action"></a>Acción recomendada

No se requiere ninguna acción por parte del desarrollador.

#### <a name="category"></a>Categoría

Bibliotecas de Core .NET

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=fullName>
- <xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=fullName>
- <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})?displayProperty=fullName>
- <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Linq.Enumerable.OrderBy`
- `Overload:System.Linq.Enumerable.OrderByDescending`
- `M:System.Linq.Enumerable.First``1(System.Collections.Generic.IEnumerable{``0},System.Func{``0,System.Boolean})`
- `M:System.Linq.Enumerable.FirstOrDefault``1(System.Collections.Generic.IEnumerable{``0},System.Func{``0,System.Boolean})`

-->
