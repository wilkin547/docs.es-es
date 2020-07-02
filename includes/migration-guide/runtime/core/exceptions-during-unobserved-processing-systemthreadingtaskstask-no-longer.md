---
ms.openlocfilehash: 5ba2ddb76ab946339449246840667ba4a48e9c66
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620578"
---
### <a name="exceptions-during-unobserved-processing-in-systemthreadingtaskstask-no-longer-propagate-on-finalizer-thread"></a>Las excepciones durante el procesamiento inadvertido en System.Threading.Tasks.Task ya no se propagan por el subproceso de finalizador

#### <a name="details"></a>Detalles

Dado que la clase <xref:System.Threading.Tasks.Task?displayProperty=fullName> representa una operación asincrónica, detecta todas las excepciones no graves que se producen durante el procesamiento asincrónico. En .NET Framework 4.5, si no se detecta una excepción y el código nunca espera a que se complete la tarea, la excepción ya no se propagará por el subproceso de finalizador y bloqueará el proceso durante la recolección de elementos no utilizados. Este cambio mejora la confiabilidad de las aplicaciones que usan la clase Task para realizar un procesamiento asincrónico inadvertido.

#### <a name="suggestion"></a>Sugerencia

Si una aplicación depende de la propagación de excepciones asincrónicas inadvertidas al subproceso de finalizador, se puede restaurar el comportamiento anterior si se proporciona un controlador adecuado para el evento <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException>, o bien se establece un [elemento de configuración del entorno de ejecución](~/docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md).

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución

#### <a name="affected-apis"></a>API afectadas

-<xref:System.Threading.Tasks.Task.Run(System.Action)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run(System.Action,System.Threading.CancellationToken)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run(System.Func{System.Threading.Tasks.Task})?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run(System.Func{System.Threading.Tasks.Task},System.Threading.CancellationToken)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run%60%601(System.Func{%60%600})?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run%60%601(System.Func{%60%600},System.Threading.CancellationToken)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run%60%601(System.Func{System.Threading.Tasks.Task{%60%600}})?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Run%60%601(System.Func{System.Threading.Tasks.Task{%60%600}},System.Threading.CancellationToken)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Start?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.Start(System.Threading.Tasks.TaskScheduler)?displayProperty=nameWithType></li></ul>|
