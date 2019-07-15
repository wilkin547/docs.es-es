---
ms.openlocfilehash: eab476a1d3f275e851e5af4198c30b60ad0c17b8
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2019
ms.locfileid: "67858389"
---
### <a name="etw-eventlisteners-do-not-capture-events-from-providers-with-explicit-keywords-like-the-tpl-provider"></a>Los elementos EventListener de ETW no capturan eventos de proveedores con palabras clave explícitas (como el proveedor de la TPL)

|   |   |
|---|---|
|Detalles|Los elementos EventListener de ETW con una máscara de palabra clave en blanco no capturarán correctamente los eventos de proveedores con palabras clave explícitas. En .NET Framework 4.5, el proveedor de la TPL comenzó a suministrar palabras clave explícitas y dio pie a este problema. En .NET Framework 4.6, se actualizaron los elementos EventListener para evitar este problema.|
|Sugerencia|Para solucionar este problema, reemplace las llamadas a <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)> con llamadas a la sobrecarga de EnableEvents que especifique explícitamente la máscara &quot;cualquier palabra clave&quot; que se va a usar: <code>EnableEvents(eventSource, level, unchecked((EventKeywords)0xFFFFffffFFFFffff))</code>. Como alternativa, este problema se ha solucionado en .NET Framework 4.6 y se puede solucionar mediante la actualización a esa versión.|
|Ámbito|Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)?displayProperty=nameWithType></li></ul>|

