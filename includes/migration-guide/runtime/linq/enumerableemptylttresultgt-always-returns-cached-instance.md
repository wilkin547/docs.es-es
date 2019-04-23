---
ms.openlocfilehash: c9efbefc2bce9e21f328680795e72b62bfcd5cbd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235825"
---
### <a name="enumerableemptytresult-always-returns-cached-instance"></a>Enumerable.Empty\<TResult> siempre devuelve una instancia almacenada en caché

|   |   |
|---|---|
|Detalles|A partir de .NET Framework 4.5, <xref:System.Linq.Enumerable.Empty%60%601> siempre devuelve una instancia interna de <xref:System.Collections.Generic.IEnumerable%601> en caché. Anteriormente, <xref:System.Linq.Enumerable.Empty%60%601> almacenaba en caché un <xref:System.Collections.Generic.IEnumerable%601> vacío en el momento de llamar a la API, lo que significa que, en algunas condiciones en las que se llamaba a <xref:System.Linq.Enumerable.Empty%60%601> de forma rápida y simultánea, se podían devolver otras instancias del tipo para otras llamadas a la API.|
|Sugerencia|Puesto que el comportamiento anterior no era determinista, es poco probable que el código dependa de él. No obstante, en el improbable caso de que se comparen enumerables vacíos y que se espere que a veces sean distintos, deberían crearse matrices vacías explícitas (<code>new T[0]</code>) en lugar de usar <xref:System.Linq.Enumerable.Empty%60%601>.|
|Ámbito|Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Linq.Enumerable.Empty%60%601?displayProperty=nameWithType></li></ul>|
