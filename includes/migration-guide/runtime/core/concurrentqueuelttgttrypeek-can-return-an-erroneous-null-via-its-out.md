---
ms.openlocfilehash: a93fbbd787aa50f080337a6170cf8f56d0d24e31
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236716"
---
### <a name="concurrentqueuettrypeek-can-return-an-erroneous-null-via-its-out-parameter"></a>ConcurrentQueue\<T>.TryPeek puede devolver un valor NULL erróneo mediante su parámetro out

|   |   |
|---|---|
|Detalles|En algunos escenarios con múltiples subprocesos, <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=name> puede devolver true, pero rellenar el parámetro out con un valor nulo (en lugar del valor correcto observado).|
|Sugerencia|Este problema se corrigió en .NET Framework 4.5.1. Actualizar a esta versión de .NET Framework solucionará el problema.|
|Ámbito|Major|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=nameWithType></li></ul>|
