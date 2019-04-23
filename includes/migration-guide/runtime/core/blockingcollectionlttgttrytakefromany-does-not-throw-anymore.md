---
ms.openlocfilehash: 9e8f9c616d5ae4ed17f35665cff21acbbacda457
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235830"
---
### <a name="blockingcollectionttrytakefromany-does-not-throw-anymore"></a>BlockingCollection\<T>.TryTakeFromAny ya no inicia excepciones

|   |   |
|---|---|
|Detalles|Si alguna de las colecciones de entrada está marcada como completada, <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)> no devuelve -1 y <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)> deja de iniciar una excepción. Este cambio permite trabajar con colecciones cuando una de las colecciones está vacía o completa y la otra colección todavía tiene elementos que se pueden recuperar.|
|Sugerencia|Si se han usado un método TryTakeFromAny que devuelva -1 o un método TakeFromAny de inicio para el control de flujo en casos en los que se complete una recolección de bloqueo, es necesario cambiar dicho código para que use <code>.Any(b =&gt; b.IsCompleted)</code> para detectar dicha condición.|
|Ámbito|Secundaria|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)?displayProperty=nameWithType></li><li><xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.Threading.CancellationToken)?displayProperty=nameWithType></li><li><xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)?displayProperty=nameWithType></li><li><xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.Int32)?displayProperty=nameWithType></li><li><xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.TimeSpan)?displayProperty=nameWithType></li><li><xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.TimeSpan)?displayProperty=nameWithType></li></ul>|
