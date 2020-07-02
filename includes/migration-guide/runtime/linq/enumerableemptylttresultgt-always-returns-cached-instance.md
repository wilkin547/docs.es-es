---
ms.openlocfilehash: 9131c91b34f4c24653dea37ea39af6be6e072287
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620632"
---
### <a name="enumerableemptylttresultgt-always-returns-cached-instance"></a>Enumerable.Empty&lt;TResult&gt; siempre devuelve una instancia almacenada en caché

#### <a name="details"></a>Detalles

A partir de .NET Framework 4.5, <xref:System.Linq.Enumerable.Empty%60%601> siempre devuelve una instancia interna de <xref:System.Collections.Generic.IEnumerable%601> en caché. Anteriormente, <xref:System.Linq.Enumerable.Empty%60%601> almacenaba en caché un <xref:System.Collections.Generic.IEnumerable%601> vacío en el momento de llamar a la API, lo que significa que, en algunas condiciones en las que se llamaba a <xref:System.Linq.Enumerable.Empty%60%601> de forma rápida y simultánea, se podían devolver otras instancias del tipo para otras llamadas a la API.

#### <a name="suggestion"></a>Sugerencia

Puesto que el comportamiento anterior no era determinista, es poco probable que el código dependa de él. No obstante, en el improbable caso de que se comparen enumerables vacíos y que se espere que a veces sean distintos, deberían crearse matrices vacías explícitas (<code>new T[0]</code>) en lugar de usar <xref:System.Linq.Enumerable.Empty%60%601>.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución

#### <a name="affected-apis"></a>API afectadas

-<xref:System.Linq.Enumerable.Empty%60%601?displayProperty=nameWithType></li></ul>|
