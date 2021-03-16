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
# <a name="complexity-of-linq-orderbyfirstordefault-increased"></a>Aumento de la complejidad de LINQ OrderBy.First{OrDefault}

La implementación de <xref:System.Linq.Enumerable.OrderBy%2A>`.`<xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> y <xref:System.Linq.Enumerable.OrderBy%2A>`.`<xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> ha cambiado, lo que aumenta la complejidad de la operación.

## <a name="change-description"></a>Descripción del cambio

Entre las versiones 1.x y 3.x de .NET Core, llamar a <xref:System.Linq.Enumerable.OrderBy%2A> o <xref:System.Linq.Enumerable.OrderByDescending%2A> seguido de <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> o <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> funciona con complejidad `O(N)`. Puesto que solo se requiere el primer elemento (o el predeterminado), solo se necesitaría una enumeración para encontrarlo. Sin embargo, el predicado que se proporciona a <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> o <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> se invoca exactamente `N` veces, donde `N` es la longitud de la secuencia.

En .NET 5 y versiones posteriores, se [implementó un cambio](https://github.com/dotnet/runtime/pull/36643) con el que llamar a <xref:System.Linq.Enumerable.OrderBy%2A> o <xref:System.Linq.Enumerable.OrderByDescending%2A> seguido de <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> o <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> funcionar con complejidad `O(N log N)` en lugar de con complejidad `O(N)`. Sin embargo, el predicado que se proporciona a <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> o <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> se puede invocar *menos* de `N` veces, lo cual es más importante para el rendimiento general.

> [!NOTE]
> Este cambio coincide con la implementación y la complejidad de la operación en .NET Framework.

## <a name="reason-for-change"></a>Motivo del cambio

La ventaja de invocar menos veces el predicado es superior a una complejidad general menor, por lo que se revirtió la implementación que se presentó en .NET Core 1.0. Para obtener más información, vea [este problema de dotnet/runtime](https://github.com/dotnet/runtime/issues/31554).

## <a name="version-introduced"></a>Versión introducida

5.0

## <a name="recommended-action"></a>Acción recomendada

No se requiere ninguna acción por parte del desarrollador.

## <a name="affected-apis"></a>API afectadas

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
