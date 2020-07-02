---
ms.openlocfilehash: 9dada93c3330331064b7a944d97d61edb4dea299
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620581"
---
### <a name="listsort-algorithm-changed"></a>El algoritmo List.Sort ha cambiado

#### <a name="details"></a>Detalles

A partir de .NET Framework 4.5, se ha cambiado el algoritmo de ordenación de <xref:System.Collections.Generic.List%601?displayProperty=fullName> (para que sea una ordenación introspectiva en lugar de una ordenación rápida). La ordenación de <xref:System.Collections.Generic.List%601?displayProperty=fullName> nunca ha sido estable, pero este cambio puede provocar que otros escenarios se ordenen de maneras inestables. Esto simplemente significa que los elementos equivalentes se pueden ordenar de otra forma en las llamadas posteriores de la API.

#### <a name="suggestion"></a>Sugerencia

Como el algoritmo de ordenación anterior también era inestable (aunque de forma ligeramente distinta), no debería haber código que dependa de que los elementos equivalentes se ordenen siempre en un orden concreto. Si hay instancias de código que dependan de eso y de tener suerte con el comportamiento anterior, ese código se debe actualizar para que use un comparador que ordene de forma determinista los elementos en el orden deseado.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Transparente|
|Versión|4.5|
|Tipo|Tiempo de ejecución

#### <a name="affected-apis"></a>API afectadas

-<xref:System.Collections.Generic.List%601.Sort?displayProperty=nameWithType></li><li><xref:System.Collections.Generic.List%601.Sort(System.Collections.Generic.IComparer{%600})?displayProperty=nameWithType></li><li><xref:System.Collections.Generic.List%601.Sort(System.Comparison{%600})?displayProperty=nameWithType></li><li><xref:System.Collections.Generic.List%601.Sort(System.Int32,System.Int32,System.Collections.Generic.IComparer{%600})?displayProperty=nameWithType></li></ul>|
