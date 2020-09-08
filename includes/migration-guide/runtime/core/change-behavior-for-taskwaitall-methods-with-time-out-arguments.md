---
ms.openlocfilehash: 9d0791f00db7d830fc5d327af30218a0bbfcb25f
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496295"
---
### <a name="change-in-behavior-for-taskwaitall-methods-with-time-out-arguments"></a>Cambio de comportamiento para los métodos Task.WaitAll con argumentos de tiempo de espera

#### <a name="details"></a>Detalles

El comportamiento de <xref:System.Threading.Tasks.Task.WaitAll%2A?displayProperty=nameWithType> se ha hecho más coherente en .NET Framework 4.5. En .NET Framework 4, estos métodos se comportaban de forma incoherente. Cuando se agotaba el tiempo de espera, si una o varias tareas se completaban o cancelaban antes de la llamada al método, el método producía una excepción <xref:System.AggregateException?displayProperty=fullName>. Cuando se agotaba el tiempo de espera, si no se completaba ni cancelaba ninguna tarea antes de la llamada al método, pero una o varias tareas entraban en estos estados después de la llamada al método, el método pasaba a ser false.<br/><br/>En .NET Framework 4.5, estas sobrecargas de método ahora devuelven false si las tareas siguen en ejecución cuando se agota el intervalo de tiempo de espera e inician una excepción <xref:System.AggregateException?displayProperty=fullName> solo si se ha cancelado una tarea de entrada (con independencia de si se canceló antes o después de la llamada al método) y no hay otras tareas en ejecución.

#### <a name="suggestion"></a>Sugerencia

Si se detectó una excepción <xref:System.AggregateException?displayProperty=fullName> como medio de detección de una tarea que se canceló antes de invocar la llamada a <xref:System.Threading.Tasks.Task.WaitAll%2A>, es necesario que ese código realice la misma detección mediante la propiedad <xref:System.Threading.Tasks.Task.IsCanceled%2A> (por ejemplo, .Any(t =&gt; t.IsCanceled)), ya que .NET Framework 4.6 solo iniciará una excepción en ese caso si todas las tareas esperadas se completan antes de que se agote el tiempo de espera.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Secundaria|
|Versión|4.5|
|Tipo|Tiempo de ejecución

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.Int32)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.Int32,System.Threading.CancellationToken)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.TimeSpan)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.Int32)`
- `M:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.Int32,System.Threading.CancellationToken)`
- `M:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.TimeSpan)`

-->
