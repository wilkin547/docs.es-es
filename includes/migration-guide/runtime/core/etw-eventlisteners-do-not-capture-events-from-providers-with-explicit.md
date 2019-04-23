---
ms.openlocfilehash: 1ef31202d7c072ca27c21fc22db102aafa6b8de7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59805052"
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
