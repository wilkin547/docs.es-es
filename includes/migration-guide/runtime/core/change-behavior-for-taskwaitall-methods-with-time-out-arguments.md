---
ms.openlocfilehash: 94fad6fe910da6c528c5e13f529a6db274e07d5c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59235920"
---
### <a name="change-in-behavior-for-taskwaitall-methods-with-time-out-arguments"></a>Cambio de comportamiento para los métodos Task.WaitAll con argumentos de tiempo de espera

|   |   |
|---|---|
|Detalles|El comportamiento de <xref:System.Threading.Tasks.Task.WaitAll%2A?displayProperty=nameWithType> se ha hecho más coherente en .NET Framework 4.5. En .NET Framework 4, estos métodos se comportaban de forma incoherente. Cuando se agotaba el tiempo de espera, si una o varias tareas se completaban o cancelaban antes de la llamada al método, el método producía una excepción <xref:System.AggregateException?displayProperty=name>. Cuando se agotaba el tiempo de espera, si no se completaba ni cancelaba ninguna tarea antes de la llamada al método, pero una o varias tareas entraban en estos estados después de la llamada al método, el método pasaba a ser false.<br/><br/>En .NET Framework 4.5, estas sobrecargas de método ahora devuelven false si las tareas siguen en ejecución cuando se agota el intervalo de tiempo de espera e inician una excepción <xref:System.AggregateException?displayProperty=name> solo si se ha cancelado una tarea de entrada (con independencia de si se canceló antes o después de la llamada al método) y no hay otras tareas en ejecución.|
|Sugerencia|Si se detectó una excepción <xref:System.AggregateException?displayProperty=name> como medio de detección de una tarea que se canceló antes de invocar la llamada a <xref:System.Threading.Tasks.Task.WaitAll%2A>, es necesario que ese código realice la misma detección mediante la propiedad <xref:System.Threading.Tasks.Task.IsCanceled%2A> (por ejemplo, .Any(t =&gt; t.IsCanceled)), ya que .NET Framework 4.6 solo iniciará una excepción en ese caso si todas las tareas esperadas se completan antes de que se agote el tiempo de espera.|
|Ámbito|Secundaria|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.Int32)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.Int32,System.Threading.CancellationToken)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.TimeSpan)?displayProperty=nameWithType></li></ul>|
