---
title: Interoperabilidad con otros tipos y patrones asincrónicos
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- .NET Framework, and TAP
- asynchronous design patterns, .NET Framework
- TAP, .NET Framework support for
- Task-based Asynchronous Pattern, .NET Framework support for
- .NET Framework, asynchronous design patterns
ms.assetid: f120a5d9-933b-4d1d-acb6-f034a57c3749
ms.openlocfilehash: fe5d8321a62b67a54dc09507e8fd86ee8d5cf74d
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84276561"
---
# <a name="interop-with-other-asynchronous-patterns-and-types"></a><span data-ttu-id="943ba-102">Interoperabilidad con otros tipos y patrones asincrónicos</span><span class="sxs-lookup"><span data-stu-id="943ba-102">Interop with Other Asynchronous Patterns and Types</span></span>
<span data-ttu-id="943ba-103">.NET Framework 1.0 introdujo el patrón <xref:System.IAsyncResult> , conocido también como [Asynchronous Programming Model (APM)](asynchronous-programming-model-apm.md)o el patrón `Begin/End` .</span><span class="sxs-lookup"><span data-stu-id="943ba-103">The .NET Framework 1.0 introduced the <xref:System.IAsyncResult> pattern, otherwise known as the [Asynchronous Programming Model (APM)](asynchronous-programming-model-apm.md), or the `Begin/End` pattern.</span></span>  <span data-ttu-id="943ba-104">.NET Framework 2.0 agregó [Modelo asincrónico basado en eventos (EAP)](event-based-asynchronous-pattern-eap.md).</span><span class="sxs-lookup"><span data-stu-id="943ba-104">The .NET Framework 2.0 added the [Event-based Asynchronous Pattern (EAP)](event-based-asynchronous-pattern-eap.md).</span></span>  <span data-ttu-id="943ba-105">A partir de .NET Framework 4, [Task-based Asynchronous Pattern (TAP)](task-based-asynchronous-pattern-tap.md) reemplaza a APM y EAP, pero proporciona la capacidad de crear fácilmente rutinas de migración a partir de los patrones anteriores:</span><span class="sxs-lookup"><span data-stu-id="943ba-105">Starting with the .NET Framework 4, the [Task-based Asynchronous Pattern (TAP)](task-based-asynchronous-pattern-tap.md) supersedes both APM and EAP, but provides the ability to easily build migration routines from the earlier patterns.</span></span>  
  
 <span data-ttu-id="943ba-106">En este tema:</span><span class="sxs-lookup"><span data-stu-id="943ba-106">In this topic:</span></span>  
  
- <span data-ttu-id="943ba-107">[Tareas y APM](#APM) ([de APM a TAP](#ApmToTap) o [de TAP a APM](#TapToApm))</span><span class="sxs-lookup"><span data-stu-id="943ba-107">[Tasks and APM](#APM) ([from APM to TAP](#ApmToTap) or [from TAP to APM](#TapToApm))</span></span>  
  
- [<span data-ttu-id="943ba-108">Tareas y EAP</span><span class="sxs-lookup"><span data-stu-id="943ba-108">Tasks and EAP</span></span>](#EAP)  
  
- <span data-ttu-id="943ba-109">[Tareas y controladores de espera](#WaitHandles) ([de controladores de espera a TAP](#WHToTap) o [de TAP a controladores de espera](#TapToWH))</span><span class="sxs-lookup"><span data-stu-id="943ba-109">[Tasks and wait handles](#WaitHandles) ([from wait handles to TAP](#WHToTap) or [from TAP to wait handles](#TapToWH))</span></span>  
  
<a name="APM"></a>
## <a name="tasks-and-the-asynchronous-programming-model-apm"></a><span data-ttu-id="943ba-110">Tareas y el modelo de programación asincrónica (APM)</span><span class="sxs-lookup"><span data-stu-id="943ba-110">Tasks and the Asynchronous Programming Model (APM)</span></span>  
  
<a name="ApmToTap"></a>
### <a name="from-apm-to-tap"></a><span data-ttu-id="943ba-111">de APM a TAP</span><span class="sxs-lookup"><span data-stu-id="943ba-111">From APM to TAP</span></span>  
 <span data-ttu-id="943ba-112">Como el patrón [Asynchronous Programming Model (APM)](asynchronous-programming-model-apm.md) está muy estructurado, es muy fácil crear un contenedor para exponer una implementación de APM como una implementación de TAP.</span><span class="sxs-lookup"><span data-stu-id="943ba-112">Because the [Asynchronous Programming Model (APM)](asynchronous-programming-model-apm.md) pattern is very structured, it is quite easy to build a wrapper to expose an APM implementation as a TAP implementation.</span></span> <span data-ttu-id="943ba-113">De hecho, .NET Framework, a partir de .NET Framework 4, incluye rutinas del asistente en forma de sobrecargas del método <xref:System.Threading.Tasks.TaskFactory.FromAsync%2A> para ofrecer esta traducción.</span><span class="sxs-lookup"><span data-stu-id="943ba-113">In fact, the .NET Framework, starting with .NET Framework 4, includes helper routines in the form of <xref:System.Threading.Tasks.TaskFactory.FromAsync%2A> method overloads to provide this translation.</span></span>  
  
 <span data-ttu-id="943ba-114">Considere la clase <xref:System.IO.Stream> y sus métodos <xref:System.IO.Stream.BeginRead%2A> y <xref:System.IO.Stream.EndRead%2A> , que representan el equivalente de APM al método sincrónico <xref:System.IO.Stream.Read%2A> :</span><span class="sxs-lookup"><span data-stu-id="943ba-114">Consider the <xref:System.IO.Stream> class and its <xref:System.IO.Stream.BeginRead%2A> and <xref:System.IO.Stream.EndRead%2A> methods, which represent the APM counterpart to the synchronous <xref:System.IO.Stream.Read%2A> method:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Stream1.cs#1)]
 [!code-vb[Conceptual.AsyncInterop#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/stream1.vb#1)]  
[!code-csharp[Conceptual.AsyncInterop#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Stream1.cs#2)]
[!code-vb[Conceptual.AsyncInterop#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/stream1.vb#2)]  
[!code-csharp[Conceptual.AsyncInterop#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Stream1.cs#3)]
[!code-vb[Conceptual.AsyncInterop#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/stream1.vb#3)]  
  
 <span data-ttu-id="943ba-115">Puede usar el método <xref:System.Threading.Tasks.TaskFactory%601.FromAsync%2A?displayProperty=nameWithType> para implementar un contenedor de TAP para esta operación como sigue:</span><span class="sxs-lookup"><span data-stu-id="943ba-115">You can use the <xref:System.Threading.Tasks.TaskFactory%601.FromAsync%2A?displayProperty=nameWithType> method to implement a TAP wrapper for this operation as follows:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Wrap1.cs#4)]
 [!code-vb[Conceptual.AsyncInterop#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/Wrap1.vb#4)]  
  
 <span data-ttu-id="943ba-116">Esta implementación es similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="943ba-116">This implementation is similar to the following:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Wrap2.cs#5)]
 [!code-vb[Conceptual.AsyncInterop#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/Wrap2.vb#5)]  
  
<a name="TapToApm"></a>
### <a name="from-tap-to-apm"></a><span data-ttu-id="943ba-117">de TAP a APM</span><span class="sxs-lookup"><span data-stu-id="943ba-117">From TAP to APM</span></span>  
 <span data-ttu-id="943ba-118">Si la infraestructura existente espera el patrón APM, también deseará realizar una implementación de TAP y usarla donde se espere una implementación de APM.</span><span class="sxs-lookup"><span data-stu-id="943ba-118">If your existing infrastructure expects the APM pattern, you'll also want to take a TAP implementation and use it where an APM implementation is expected.</span></span>  <span data-ttu-id="943ba-119">Como las tareas se pueden crear y la clase <xref:System.Threading.Tasks.Task> implementa <xref:System.IAsyncResult>, puede usar una función del asistente sencilla para ello.</span><span class="sxs-lookup"><span data-stu-id="943ba-119">Because tasks can be composed and  the <xref:System.Threading.Tasks.Task> class implements <xref:System.IAsyncResult>, you can use a straightforward helper function to do this.</span></span> <span data-ttu-id="943ba-120">En el código siguiente se usa una extensión de la clase <xref:System.Threading.Tasks.Task%601> , pero puede usar una función casi idéntica para las tareas no genéricas.</span><span class="sxs-lookup"><span data-stu-id="943ba-120">The following code uses an extension of the <xref:System.Threading.Tasks.Task%601> class, but you can use an almost identical function for non-generic tasks.</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/APM1.cs#6)]
 [!code-vb[Conceptual.AsyncInterop#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/APM1.vb#6)]  
  
 <span data-ttu-id="943ba-121">Ahora, considere un caso donde tiene la implementación siguiente de TAP:</span><span class="sxs-lookup"><span data-stu-id="943ba-121">Now, consider a case where you have the following TAP implementation:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/APM2.cs#7)]
 [!code-vb[Conceptual.AsyncInterop#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/APM2.vb#7)]  
  
 <span data-ttu-id="943ba-122">y desea proporcionar esta implementación de APM:</span><span class="sxs-lookup"><span data-stu-id="943ba-122">and you want to provide this APM implementation:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#8](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/APM2.cs#8)]
 [!code-vb[Conceptual.AsyncInterop#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/APM2.vb#8)]  
[!code-csharp[Conceptual.AsyncInterop#9](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/APM2.cs#9)]
[!code-vb[Conceptual.AsyncInterop#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/APM2.vb#9)]  
  
 <span data-ttu-id="943ba-123">En el ejemplo siguiente se muestra una migración a APM:</span><span class="sxs-lookup"><span data-stu-id="943ba-123">The following example demonstrates one migration to APM:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#10](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/APM2.cs#10)]
 [!code-vb[Conceptual.AsyncInterop#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/APM2.vb#10)]  
  
<a name="EAP"></a>
## <a name="tasks-and-the-event-based-asynchronous-pattern-eap"></a><span data-ttu-id="943ba-124">Tareas y el patrón asincrónico basado en eventos (EAP)</span><span class="sxs-lookup"><span data-stu-id="943ba-124">Tasks and the Event-based Asynchronous Pattern (EAP)</span></span>  
 <span data-ttu-id="943ba-125">El encapsulamiento de una implementación de [Modelo asincrónico basado en eventos (EAP)](event-based-asynchronous-pattern-eap.md) es más complejo que encapsular un patrón de APM, ya que el patrón de EAP tiene más variaciones y menos estructura que el de APM.</span><span class="sxs-lookup"><span data-stu-id="943ba-125">Wrapping an [Event-based Asynchronous Pattern (EAP)](event-based-asynchronous-pattern-eap.md) implementation is more involved than wrapping an APM pattern, because the EAP pattern has more variation and less structure than the APM pattern.</span></span>  <span data-ttu-id="943ba-126">Para mostrarlo, el código siguiente encapsula el método `DownloadStringAsync` .</span><span class="sxs-lookup"><span data-stu-id="943ba-126">To demonstrate, the following code wraps the `DownloadStringAsync` method.</span></span>  <span data-ttu-id="943ba-127">`DownloadStringAsync` acepta un URI, genera el evento `DownloadProgressChanged` durante la descarga para informar de varias estadísticas sobre el progreso y genera el evento `DownloadStringCompleted` cuando termina.</span><span class="sxs-lookup"><span data-stu-id="943ba-127">`DownloadStringAsync` accepts a URI, raises the `DownloadProgressChanged` event while downloading in order to report multiple statistics on progress, and raises the `DownloadStringCompleted` event when it's done.</span></span>  <span data-ttu-id="943ba-128">El resultado final es una cadena que incluye el contenido de la página en el URI especificado.</span><span class="sxs-lookup"><span data-stu-id="943ba-128">The final result is a string that contains the contents of the page at the specified URI.</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#11](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/EAP1.cs#11)]
 [!code-vb[Conceptual.AsyncInterop#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/EAP1.vb#11)]  
  
<a name="WaitHandles"></a>
## <a name="tasks-and-wait-handles"></a><span data-ttu-id="943ba-129">Tareas y controladores de espera</span><span class="sxs-lookup"><span data-stu-id="943ba-129">Tasks and Wait Handles</span></span>  
  
<a name="WHToTap"></a>
### <a name="from-wait-handles-to-tap"></a><span data-ttu-id="943ba-130">de controladores de espera a TAP</span><span class="sxs-lookup"><span data-stu-id="943ba-130">From Wait Handles to TAP</span></span>  
 <span data-ttu-id="943ba-131">Aunque los controladores de espera no implementan un patrón asincrónico, los desarrolladores avanzados pueden usar la clase <xref:System.Threading.WaitHandle> y el método <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A?displayProperty=nameWithType> para las notificaciones asincrónicas cuando se establece un controlador de este tipo.</span><span class="sxs-lookup"><span data-stu-id="943ba-131">Although wait handles don't implement an asynchronous pattern, advanced developers may use the <xref:System.Threading.WaitHandle> class and the <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A?displayProperty=nameWithType> method for asynchronous notifications when a wait handle is set.</span></span>  <span data-ttu-id="943ba-132">Puede encapsular el método <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A> para habilitar una alternativa basada en tareas para cualquier espera sincrónica en un controlador de espera:</span><span class="sxs-lookup"><span data-stu-id="943ba-132">You can wrap the <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A> method to enable a task-based alternative to any synchronous wait on a wait handle:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#12](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Wait1.cs#12)]
 [!code-vb[Conceptual.AsyncInterop#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/Wait1.vb#12)]  
  
 <span data-ttu-id="943ba-133">Con este método se pueden usar las implementaciones existentes <xref:System.Threading.WaitHandle> en métodos asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="943ba-133">With this method, you can use existing <xref:System.Threading.WaitHandle> implementations in asynchronous methods.</span></span>  <span data-ttu-id="943ba-134">Por ejemplo, si quiere restringir el número de operaciones asincrónicas que se ejecutan en un momento dado, puede usar un semáforo (un objeto <xref:System.Threading.SemaphoreSlim?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="943ba-134">For example, if you want to throttle the number of asynchronous operations that are executing at any particular time, you can utilize a semaphore (a <xref:System.Threading.SemaphoreSlim?displayProperty=nameWithType> object).</span></span>  <span data-ttu-id="943ba-135">Se puede restringir a *N* el número de operaciones que se ejecutan simultáneamente mediante una inicialización del contador del semáforo a *N*, esperando al semáforo cuando se quiera realizar una operación y liberando el semáforo cuando se haya terminado:</span><span class="sxs-lookup"><span data-stu-id="943ba-135">You can throttle to *N* the number of operations that run concurrently by initializing the semaphore’s count to *N*, waiting on the semaphore any time you want to perform an operation, and releasing the semaphore when you’re done with an operation:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#13](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Semaphore1.cs#13)]
 [!code-vb[Conceptual.AsyncInterop#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/Semaphore1.vb#13)]  
  
 <span data-ttu-id="943ba-136">También se puede compilar un semáforo asincrónico que no se base en controladores de espera, sino que funcione completamente con tareas.</span><span class="sxs-lookup"><span data-stu-id="943ba-136">You can also build an asynchronous semaphore that does not rely on wait handles and instead works completely with tasks.</span></span> <span data-ttu-id="943ba-137">Para ello, puede usar técnicas como las descritas en [Consuming the Task-based Asynchronous Pattern](consuming-the-task-based-asynchronous-pattern.md) para crear estructuras de datos encima de <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="943ba-137">To do this, you can use techniques such as those discussed in [Consuming the Task-based Asynchronous Pattern](consuming-the-task-based-asynchronous-pattern.md) for building data structures on top of <xref:System.Threading.Tasks.Task>.</span></span>  
  
<a name="TapToWH"></a>
### <a name="from-tap-to-wait-handles"></a><span data-ttu-id="943ba-138">de TAP a controladores de espera</span><span class="sxs-lookup"><span data-stu-id="943ba-138">From TAP to Wait Handles</span></span>  
 <span data-ttu-id="943ba-139">Como se mencionó anteriormente, la clase <xref:System.Threading.Tasks.Task> implementa <xref:System.IAsyncResult>y esa implementación expone una propiedad <xref:System.Threading.Tasks.Task.System%23IAsyncResult%23AsyncWaitHandle%2A> que devuelve un controlador de espera que se establecerá cuando la <xref:System.Threading.Tasks.Task> se haya completado.</span><span class="sxs-lookup"><span data-stu-id="943ba-139">As previously mentioned, the <xref:System.Threading.Tasks.Task> class implements <xref:System.IAsyncResult>, and that implementation exposes an <xref:System.Threading.Tasks.Task.System%23IAsyncResult%23AsyncWaitHandle%2A> property that returns a wait handle that will be set when the <xref:System.Threading.Tasks.Task> completes.</span></span>  <span data-ttu-id="943ba-140">Puede obtener la instancia de <xref:System.Threading.WaitHandle> para una <xref:System.Threading.Tasks.Task> de esta manera:</span><span class="sxs-lookup"><span data-stu-id="943ba-140">You can get a <xref:System.Threading.WaitHandle> for a <xref:System.Threading.Tasks.Task> as follows:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#14](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Wait1.cs#14)]
 [!code-vb[Conceptual.AsyncInterop#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/Wait1.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="943ba-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="943ba-141">See also</span></span>

- <span data-ttu-id="943ba-142">[Modelo asincrónico basado en tareas [TAP]](task-based-asynchronous-pattern-tap.md)</span><span class="sxs-lookup"><span data-stu-id="943ba-142">[Task-based Asynchronous Pattern (TAP)](task-based-asynchronous-pattern-tap.md)</span></span>
- [<span data-ttu-id="943ba-143">Implementar el modelo asincrónico basado en tareas</span><span class="sxs-lookup"><span data-stu-id="943ba-143">Implementing the Task-based Asynchronous Pattern</span></span>](implementing-the-task-based-asynchronous-pattern.md)
- [<span data-ttu-id="943ba-144">Utilizar el modelo asincrónico basado en tareas</span><span class="sxs-lookup"><span data-stu-id="943ba-144">Consuming the Task-based Asynchronous Pattern</span></span>](consuming-the-task-based-asynchronous-pattern.md)
