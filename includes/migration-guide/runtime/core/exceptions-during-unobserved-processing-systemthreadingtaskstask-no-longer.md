---
ms.openlocfilehash: bae211e5684dc1fbbb1d7e69c928e37c1c532096
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497208"
---
### <a name="exceptions-during-unobserved-processing-in-systemthreadingtaskstask-no-longer-propagate-on-finalizer-thread"></a><span data-ttu-id="dbc8c-101">Las excepciones durante el procesamiento inadvertido en System.Threading.Tasks.Task ya no se propagan por el subproceso de finalizador</span><span class="sxs-lookup"><span data-stu-id="dbc8c-101">Exceptions during unobserved processing in System.Threading.Tasks.Task no longer propagate on finalizer thread</span></span>

#### <a name="details"></a><span data-ttu-id="dbc8c-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="dbc8c-102">Details</span></span>

<span data-ttu-id="dbc8c-103">Dado que la clase <xref:System.Threading.Tasks.Task?displayProperty=fullName> representa una operación asincrónica, detecta todas las excepciones no graves que se producen durante el procesamiento asincrónico.</span><span class="sxs-lookup"><span data-stu-id="dbc8c-103">Because the <xref:System.Threading.Tasks.Task?displayProperty=fullName> class represents an asynchronous operation, it catches all non-severe exceptions that occur during asynchronous processing.</span></span> <span data-ttu-id="dbc8c-104">En .NET Framework 4.5, si no se detecta una excepción y el código nunca espera a que se complete la tarea, la excepción ya no se propagará por el subproceso de finalizador y bloqueará el proceso durante la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="dbc8c-104">In the .NET Framework 4.5, if an exception is not observed and your code never waits on the task, the exception will no longer propagate on the finalizer thread and crash the process during garbage collection.</span></span> <span data-ttu-id="dbc8c-105">Este cambio mejora la confiabilidad de las aplicaciones que usan la clase Task para realizar un procesamiento asincrónico inadvertido.</span><span class="sxs-lookup"><span data-stu-id="dbc8c-105">This change enhances the reliability of applications that use the Task class to perform unobserved asynchronous processing.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="dbc8c-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="dbc8c-106">Suggestion</span></span>

<span data-ttu-id="dbc8c-107">Si una aplicación depende de la propagación de excepciones asincrónicas inadvertidas al subproceso de finalizador, se puede restaurar el comportamiento anterior si se proporciona un controlador adecuado para el evento <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException>, o bien se establece un [elemento de configuración del entorno de ejecución](~/docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md).</span><span class="sxs-lookup"><span data-stu-id="dbc8c-107">If an app depends on unobserved asynchronous exceptions propagating to the finalizer thread, the previous behavior can be restored by providing an appropriate handler for the <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> event, or by setting a [runtime configuration element](~/docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md).</span></span>

| <span data-ttu-id="dbc8c-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="dbc8c-108">Name</span></span>    | <span data-ttu-id="dbc8c-109">Valor</span><span class="sxs-lookup"><span data-stu-id="dbc8c-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="dbc8c-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="dbc8c-110">Scope</span></span>   |<span data-ttu-id="dbc8c-111">Borde</span><span class="sxs-lookup"><span data-stu-id="dbc8c-111">Edge</span></span>|
|<span data-ttu-id="dbc8c-112">Versión</span><span class="sxs-lookup"><span data-stu-id="dbc8c-112">Version</span></span>|<span data-ttu-id="dbc8c-113">4.5</span><span class="sxs-lookup"><span data-stu-id="dbc8c-113">4.5</span></span>|
|<span data-ttu-id="dbc8c-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="dbc8c-114">Type</span></span>|<span data-ttu-id="dbc8c-115">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="dbc8c-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="dbc8c-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="dbc8c-116">Affected APIs</span></span>

- <xref:System.Threading.Tasks.Task.Run(System.Action)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.Run(System.Action,System.Threading.CancellationToken)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.Run(System.Func{System.Threading.Tasks.Task})?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.Run(System.Func{System.Threading.Tasks.Task},System.Threading.CancellationToken)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.Run%60%601(System.Func{%60%600})?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.Run%60%601(System.Func{%60%600},System.Threading.CancellationToken)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.Run%60%601(System.Func{System.Threading.Tasks.Task{%60%600}})?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.Run%60%601(System.Func{System.Threading.Tasks.Task{%60%600}},System.Threading.CancellationToken)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.Start?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task.Start(System.Threading.Tasks.TaskScheduler)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Threading.Tasks.Task.Run(System.Action)`
- `M:System.Threading.Tasks.Task.Run(System.Action,System.Threading.CancellationToken)`
- `M:System.Threading.Tasks.Task.Run(System.Func{System.Threading.Tasks.Task})`
- `M:System.Threading.Tasks.Task.Run(System.Func{System.Threading.Tasks.Task},System.Threading.CancellationToken)`
- ``M:System.Threading.Tasks.Task.Run``1(System.Func{``0})``
- ``M:System.Threading.Tasks.Task.Run``1(System.Func{``0},System.Threading.CancellationToken)``
- ``M:System.Threading.Tasks.Task.Run``1(System.Func{System.Threading.Tasks.Task{``0}})``
- ``M:System.Threading.Tasks.Task.Run``1(System.Func{System.Threading.Tasks.Task{``0}},System.Threading.CancellationToken)``
- `M:System.Threading.Tasks.Task.Start`
- `M:System.Threading.Tasks.Task.Start(System.Threading.Tasks.TaskScheduler)`

-->
