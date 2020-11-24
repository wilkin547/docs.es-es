---
title: Notificaciones de recolección de elementos no utilizados
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- garbage collection, notifications
ms.assetid: e12d8e74-31e3-4035-a87d-f3e66f0a9b89
ms.openlocfilehash: c91712b9d25221f1ffd9e9e980c420be32e2379a
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94831187"
---
# <a name="garbage-collection-notifications"></a><span data-ttu-id="a20d3-102">Notificaciones de recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="a20d3-102">Garbage Collection Notifications</span></span>
<span data-ttu-id="a20d3-103">Hay situaciones en que una colección de elementos no utilizados completa (es decir, una colección de generación 2) de Common Language Runtime puede afectar negativamente al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="a20d3-103">There are situations in which a full garbage collection (that is, a generation 2 collection) by the common language runtime may adversely affect performance.</span></span> <span data-ttu-id="a20d3-104">Esto puede ser un problema especialmente con servidores que procesan grandes volúmenes de solicitudes; en este caso, una recolección grande de elementos no utilizados puede causar un tiempo de espera en la solicitud. Para evitar una recolección grande durante un período crítico, puede recibir una notificación de la proximidad de una recolección grande de elementos no utilizados y adoptar las medidas pertinentes para redirigir la carga de trabajo a otra instancia del servidor.</span><span class="sxs-lookup"><span data-stu-id="a20d3-104">This can be an issue particularly with servers that process large volumes of requests; in this case, a long garbage collection can cause a request time-out. To prevent a full collection from occurring during a critical period, you can be notified that a full garbage collection is approaching and then take action to redirect the workload to another server instance.</span></span> <span data-ttu-id="a20d3-105">También puede incluir una recolección por su cuenta, siempre que la instancia de servidor actual no necesite procesar solicitudes.</span><span class="sxs-lookup"><span data-stu-id="a20d3-105">You can also induce a collection yourself, provided that the current server instance does not need to process requests.</span></span>  
  
 <span data-ttu-id="a20d3-106">El método <xref:System.GC.RegisterForFullGCNotification%2A> registra una notificación que se genera si el tiempo de ejecución detecta que una recolección de elementos no utilizados completa está próxima.</span><span class="sxs-lookup"><span data-stu-id="a20d3-106">The <xref:System.GC.RegisterForFullGCNotification%2A> method registers for a notification to be raised when the runtime senses that a full garbage collection is approaching.</span></span> <span data-ttu-id="a20d3-107">Esta notificación consta de dos partes: cuando se está aproximando la recolección de elementos no utilizados completa y cuando finaliza la recolección de elementos no utilizados completa.</span><span class="sxs-lookup"><span data-stu-id="a20d3-107">There are two parts to this notification: when the full garbage collection is approaching and when the full garbage collection has completed.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="a20d3-108">Solo las recolecciones de elementos no utilizados bloqueadas generarán notificaciones.</span><span class="sxs-lookup"><span data-stu-id="a20d3-108">Only blocking garbage collections raise notifications.</span></span> <span data-ttu-id="a20d3-109">Cuando el elemento de configuración [\<gcConcurrent>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) está habilitado, las recolecciones de elementos no utilizados en segundo plano no generarán notificaciones.</span><span class="sxs-lookup"><span data-stu-id="a20d3-109">When the [\<gcConcurrent>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) configuration element is enabled, background garbage collections will not raise notifications.</span></span>  
  
 <span data-ttu-id="a20d3-110">Para determinar cuándo se ha generado una notificación, use los métodos <xref:System.GC.WaitForFullGCApproach%2A> y <xref:System.GC.WaitForFullGCComplete%2A>.</span><span class="sxs-lookup"><span data-stu-id="a20d3-110">To determine when a notification has been raised, use the <xref:System.GC.WaitForFullGCApproach%2A> and <xref:System.GC.WaitForFullGCComplete%2A> methods.</span></span> <span data-ttu-id="a20d3-111">Por lo general, utilice estos métodos en un bucle `while` para obtener continuamente una enumeración <xref:System.GCNotificationStatus> que muestra el estado de la notificación.</span><span class="sxs-lookup"><span data-stu-id="a20d3-111">Typically, you use these methods in a `while` loop to continually obtain a <xref:System.GCNotificationStatus> enumeration that shows the status of the notification.</span></span> <span data-ttu-id="a20d3-112">Si el valor es <xref:System.GCNotificationStatus.Succeeded>, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a20d3-112">If that value is <xref:System.GCNotificationStatus.Succeeded>, you can do the following:</span></span>  
  
- <span data-ttu-id="a20d3-113">En respuesta a una notificación obtenida con el método <xref:System.GC.WaitForFullGCApproach%2A>, puede redirigir la carga de trabajo y posiblemente inducir una recolección.</span><span class="sxs-lookup"><span data-stu-id="a20d3-113">In response to a notification obtained with the <xref:System.GC.WaitForFullGCApproach%2A> method, you can redirect the workload and possibly induce a collection yourself.</span></span>  
  
- <span data-ttu-id="a20d3-114">En respuesta a una notificación obtenida con el método <xref:System.GC.WaitForFullGCComplete%2A>, puede habilitar la instancia de servidor actual para volver a procesar las solicitudes.</span><span class="sxs-lookup"><span data-stu-id="a20d3-114">In response to a notification obtained with the <xref:System.GC.WaitForFullGCComplete%2A> method, you can make the current server instance available to process requests again.</span></span> <span data-ttu-id="a20d3-115">También puede recopilar información.</span><span class="sxs-lookup"><span data-stu-id="a20d3-115">You can also gather information.</span></span> <span data-ttu-id="a20d3-116">Por ejemplo, puede usar el método <xref:System.GC.CollectionCount%2A> para registrar el número de recolecciones.</span><span class="sxs-lookup"><span data-stu-id="a20d3-116">For example, you can use the <xref:System.GC.CollectionCount%2A> method to record the number of collections.</span></span>  
  
 <span data-ttu-id="a20d3-117">Los métodos <xref:System.GC.WaitForFullGCApproach%2A> y <xref:System.GC.WaitForFullGCComplete%2A> están diseñados para que funcionen de forma conjunta.</span><span class="sxs-lookup"><span data-stu-id="a20d3-117">The <xref:System.GC.WaitForFullGCApproach%2A> and the <xref:System.GC.WaitForFullGCComplete%2A> methods are designed to work together.</span></span> <span data-ttu-id="a20d3-118">Utilizar un método sin el otro puede producir resultados indeterminados.</span><span class="sxs-lookup"><span data-stu-id="a20d3-118">Using one without the other can produce indeterminate results.</span></span>  
  
## <a name="full-garbage-collection"></a><span data-ttu-id="a20d3-119">Recolección de elementos no utilizados completa</span><span class="sxs-lookup"><span data-stu-id="a20d3-119">Full Garbage Collection</span></span>  
 <span data-ttu-id="a20d3-120">El tiempo de ejecución produce una recolección de elementos no utilizados completa cuando se cumple alguna de las situaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="a20d3-120">The runtime causes a full garbage collection when any of the following scenarios are true:</span></span>  
  
- <span data-ttu-id="a20d3-121">Se ha promocionado suficiente memoria en la generación 2 para generar la siguiente recolección de la generación 2.</span><span class="sxs-lookup"><span data-stu-id="a20d3-121">Enough memory has been promoted into generation 2 to cause the next generation 2 collection.</span></span>  
  
- <span data-ttu-id="a20d3-122">Se ha promocionado suficiente memoria en el montón de objetos grandes para generar la siguiente recolección de la generación 2.</span><span class="sxs-lookup"><span data-stu-id="a20d3-122">Enough memory has been promoted into the large object heap to cause the next generation 2 collection.</span></span>  
  
- <span data-ttu-id="a20d3-123">Una recolección de la generación 1 se escala a una recolección de la generación 2 debido a dos factores.</span><span class="sxs-lookup"><span data-stu-id="a20d3-123">A collection of generation 1 is escalated to a collection of generation 2 due to other factors.</span></span>  
  
 <span data-ttu-id="a20d3-124">Los umbrales especificados en el método <xref:System.GC.RegisterForFullGCNotification%2A> se aplican a los dos primeros escenarios.</span><span class="sxs-lookup"><span data-stu-id="a20d3-124">The thresholds you specify in the <xref:System.GC.RegisterForFullGCNotification%2A> method apply to the first two scenarios.</span></span> <span data-ttu-id="a20d3-125">Sin embargo, en el primer escenario no siempre recibirá la notificación en el tiempo proporcional a los valores de umbral especificados por dos motivos:</span><span class="sxs-lookup"><span data-stu-id="a20d3-125">However, in the first scenario you will not always receive the notification at the time proportional to the threshold values you specify for two reasons:</span></span>  
  
- <span data-ttu-id="a20d3-126">El tiempo de ejecución no comprueba cada asignación de objetos pequeños (por motivos de rendimiento).</span><span class="sxs-lookup"><span data-stu-id="a20d3-126">The runtime does not check each small object allocation (for performance reasons).</span></span>  
  
- <span data-ttu-id="a20d3-127">Solo las recolecciones de la generación 1 promueven la memoria a la generación 2.</span><span class="sxs-lookup"><span data-stu-id="a20d3-127">Only generation 1 collections promote memory into generation 2.</span></span>  
  
 <span data-ttu-id="a20d3-128">El tercer escenario también contribuye a la incertidumbre de cuándo recibirá la notificación.</span><span class="sxs-lookup"><span data-stu-id="a20d3-128">The third scenario also contributes to the uncertainty of when you will receive the notification.</span></span> <span data-ttu-id="a20d3-129">Aunque esto no es una garantía, demuestra ser útil para mitigar los efectos de una recolección de elementos no utilizados completa inoportuna redirigiendo las solicitudes durante este tiempo o induciendo la recolección por su cuenta cuando sea más apropiado.</span><span class="sxs-lookup"><span data-stu-id="a20d3-129">Although this is not a guarantee, it does prove to be a useful way to mitigate the effects of an inopportune full garbage collection by redirecting the requests during this time or inducing the collection yourself when it can be better accommodated.</span></span>  
  
## <a name="notification-threshold-parameters"></a><span data-ttu-id="a20d3-130">Parámetros del umbral de notificación</span><span class="sxs-lookup"><span data-stu-id="a20d3-130">Notification Threshold Parameters</span></span>  
 <span data-ttu-id="a20d3-131">El método <xref:System.GC.RegisterForFullGCNotification%2A> tiene dos parámetros para especificar los valores de umbral de los objetos de generación 2 y del montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="a20d3-131">The <xref:System.GC.RegisterForFullGCNotification%2A> method has two parameters to specify the threshold values of the generation 2 objects and the large object heap.</span></span> <span data-ttu-id="a20d3-132">Cuando se alcanza dichos valores, debe generarse una notificación de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="a20d3-132">When those values are met, a garbage collection notification should be raised.</span></span> <span data-ttu-id="a20d3-133">En la siguiente tabla se describen estos parámetros.</span><span class="sxs-lookup"><span data-stu-id="a20d3-133">The following table describes these parameters.</span></span>  
  
|<span data-ttu-id="a20d3-134">Parámetro</span><span class="sxs-lookup"><span data-stu-id="a20d3-134">Parameter</span></span>|<span data-ttu-id="a20d3-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="a20d3-135">Description</span></span>|  
|---------------|-----------------|  
|`maxGenerationThreshold`|<span data-ttu-id="a20d3-136">Número comprendido entre 1 y 99 que especifica cuándo debe emitirse la notificación basándose en los objetos promocionados en la generación 2.</span><span class="sxs-lookup"><span data-stu-id="a20d3-136">A number between 1 and 99 that specifies when the notification should be raised based on the objects promoted in generation 2.</span></span>|  
|`largeObjectHeapThreshold`|<span data-ttu-id="a20d3-137">Un número comprendido entre 1 y 99 que especifica cuándo debe emitirse la notificación basándose en los objetos asignados en el montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="a20d3-137">A number between 1 and 99 that specifies when the notification should be raised based on the objects that are allocated in the large object heap.</span></span>|  
  
 <span data-ttu-id="a20d3-138">Si especifica un valor que es demasiado alto, hay una alta probabilidad de recibir una notificación, pero podría producirse un tiempo de espera demasiado largo antes de que el tiempo de ejecución genere una recolección.</span><span class="sxs-lookup"><span data-stu-id="a20d3-138">If you specify a value that is too high, there is a high probability that you will receive a notification, but it could be too long a period to wait before the runtime causes a collection.</span></span> <span data-ttu-id="a20d3-139">Si induce una recolección, puede reclamar más objetos de los que reclamarían si el tiempo de ejecución genera la recolección.</span><span class="sxs-lookup"><span data-stu-id="a20d3-139">If you induce a collection yourself, you may reclaim more objects than would be reclaimed if the runtime causes the collection.</span></span>  
  
 <span data-ttu-id="a20d3-140">Si especifica un valor que es demasiado bajo, el tiempo de ejecución puede provocar la recolección antes de que haya tenido tiempo suficiente para recibir la notificación.</span><span class="sxs-lookup"><span data-stu-id="a20d3-140">If you specify a value that is too low, the runtime may cause the collection before you have had sufficient time to be notified.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a20d3-141">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a20d3-141">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="a20d3-142">Descripción</span><span class="sxs-lookup"><span data-stu-id="a20d3-142">Description</span></span>  
 <span data-ttu-id="a20d3-143">En el ejemplo siguiente, un grupo de solicitudes web entrantes del servicio de servidores.</span><span class="sxs-lookup"><span data-stu-id="a20d3-143">In the following example, a group of servers service incoming Web requests.</span></span> <span data-ttu-id="a20d3-144">Para simular la carga de trabajo de procesamiento de solicitudes, se agregan matrices de bytes a una colección <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="a20d3-144">To simulate the workload of processing requests, byte arrays are added to a <xref:System.Collections.Generic.List%601> collection.</span></span> <span data-ttu-id="a20d3-145">Cada servidor registra una notificación de la recolección de elementos no utilizados y luego inicia un subproceso en el método del usuario `WaitForFullGCProc` para supervisar continuamente la enumeración <xref:System.GCNotificationStatus> devuelta por los métodos <xref:System.GC.WaitForFullGCApproach%2A> y <xref:System.GC.WaitForFullGCComplete%2A>.</span><span class="sxs-lookup"><span data-stu-id="a20d3-145">Each server registers for a garbage collection notification and then starts a thread on the `WaitForFullGCProc` user method to continuously monitor the <xref:System.GCNotificationStatus> enumeration that is returned by the <xref:System.GC.WaitForFullGCApproach%2A> and the <xref:System.GC.WaitForFullGCComplete%2A> methods.</span></span>  
  
 <span data-ttu-id="a20d3-146">Los métodos <xref:System.GC.WaitForFullGCApproach%2A> y <xref:System.GC.WaitForFullGCComplete%2A> llaman a sus respectivos métodos de usuario de control de eventos cuando se emite una notificación:</span><span class="sxs-lookup"><span data-stu-id="a20d3-146">The <xref:System.GC.WaitForFullGCApproach%2A> and the <xref:System.GC.WaitForFullGCComplete%2A> methods call their respective event-handling user methods when a notification is raised:</span></span>  
  
- `OnFullGCApproachNotify`  
  
     <span data-ttu-id="a20d3-147">Este método llama al método de usuario `RedirectRequests`, que indica al servidor de puesta en cola de solicitudes que suspenda el envío de solicitudes al servidor.</span><span class="sxs-lookup"><span data-stu-id="a20d3-147">This method calls the `RedirectRequests` user method, which instructs the request queuing server to suspend sending requests to the server.</span></span> <span data-ttu-id="a20d3-148">Esto se simula con la definición de la variable de nivel de clase `bAllocate` en `false`, para que no se asignen más objetos.</span><span class="sxs-lookup"><span data-stu-id="a20d3-148">This is simulated by setting the class-level variable `bAllocate` to `false` so that no more objects are allocated.</span></span>  
  
     <span data-ttu-id="a20d3-149">Después, se llama al método de usuario `FinishExistingRequests` para finalizar el procesamiento de las solicitudes de servidor pendientes.</span><span class="sxs-lookup"><span data-stu-id="a20d3-149">Next, the `FinishExistingRequests` user method is called to finish processing the pending server requests.</span></span> <span data-ttu-id="a20d3-150">Esto se simula mediante la desactivación de la recolección <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="a20d3-150">This is simulated by clearing the <xref:System.Collections.Generic.List%601> collection.</span></span>  
  
     <span data-ttu-id="a20d3-151">Por último, se indujo una recolección de elementos no utilizados porque la carga de trabajo es ligera.</span><span class="sxs-lookup"><span data-stu-id="a20d3-151">Finally, a garbage collection is induced because the workload is light.</span></span>  
  
- `OnFullGCCompleteNotify`  
  
     <span data-ttu-id="a20d3-152">Este método llama al método de usuario `AcceptRequests` para reanudar la aceptación de solicitudes porque el servidor ya no es susceptible a una recolección de elementos no utilizados completa.</span><span class="sxs-lookup"><span data-stu-id="a20d3-152">This method calls the user method `AcceptRequests` to resume accepting requests because the server is no longer susceptible to a full garbage collection.</span></span> <span data-ttu-id="a20d3-153">Esta acción se simula estableciendo la variable `bAllocate` en `true`, para que se reanude la adición de los objetos a la recolección <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="a20d3-153">This action is simulated by setting the `bAllocate` variable to `true` so that objects can resume being added to the <xref:System.Collections.Generic.List%601> collection.</span></span>  
  
 <span data-ttu-id="a20d3-154">El código siguiente contiene el método `Main` del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a20d3-154">The following code contains the `Main` method of the example.</span></span>  
  
 [!code-cpp[GCNotification#2](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#2)]
 [!code-csharp[GCNotification#2](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#2)]
 [!code-vb[GCNotification#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#2)]  
  
 <span data-ttu-id="a20d3-155">El siguiente código contiene el método de usuario `WaitForFullGCProc`, que incluye un bucle while continuo para comprobar las notificaciones de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="a20d3-155">The following code contains the `WaitForFullGCProc` user method, that contains a continuous while loop to check for garbage collection notifications.</span></span>  
  
 [!code-cpp[GCNotification#8](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#8)]
 [!code-csharp[GCNotification#8](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#8)]
 [!code-vb[GCNotification#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#8)]  
  
 <span data-ttu-id="a20d3-156">El código siguiente contiene el método `OnFullGCApproachNotify` tras realizar la llamada al</span><span class="sxs-lookup"><span data-stu-id="a20d3-156">The following code contains the `OnFullGCApproachNotify` method as called from the</span></span>  
  
 <span data-ttu-id="a20d3-157">Método `WaitForFullGCProc`.</span><span class="sxs-lookup"><span data-stu-id="a20d3-157">`WaitForFullGCProc` method.</span></span>  
  
 [!code-cpp[GCNotification#5](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#5)]
 [!code-csharp[GCNotification#5](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#5)]
 [!code-vb[GCNotification#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#5)]  
  
 <span data-ttu-id="a20d3-158">El código siguiente contiene el método `OnFullGCApproachComplete` tras realizar la llamada al</span><span class="sxs-lookup"><span data-stu-id="a20d3-158">The following code contains the `OnFullGCApproachComplete` method as called from the</span></span>  
  
 <span data-ttu-id="a20d3-159">Método `WaitForFullGCProc`.</span><span class="sxs-lookup"><span data-stu-id="a20d3-159">`WaitForFullGCProc` method.</span></span>  
  
 [!code-cpp[GCNotification#6](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#6)]
 [!code-csharp[GCNotification#6](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#6)]
 [!code-vb[GCNotification#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#6)]  
  
 <span data-ttu-id="a20d3-160">El código siguiente contiene los métodos de usuario tras realizar la llamada a los métodos `OnFullGCApproachNotify` y `OnFullGCCompleteNotify`.</span><span class="sxs-lookup"><span data-stu-id="a20d3-160">The following code contains the user methods that are called from the `OnFullGCApproachNotify` and `OnFullGCCompleteNotify` methods.</span></span> <span data-ttu-id="a20d3-161">Los métodos de usuario redirigen las solicitudes, finalizan las solicitudes existentes y reanudan las solicitudes después de que se produzca una recolección de elementos no utilizados completa.</span><span class="sxs-lookup"><span data-stu-id="a20d3-161">The user methods redirect requests, finish existing requests, and then resume requests after a full garbage collection has occurred.</span></span>  
  
 [!code-cpp[GCNotification#9](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#9)]
 [!code-csharp[GCNotification#9](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#9)]
 [!code-vb[GCNotification#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#9)]  
  
 <span data-ttu-id="a20d3-162">El ejemplo de código completo es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="a20d3-162">The entire code sample is as follows:</span></span>  
  
 [!code-cpp[GCNotification#1](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#1)]
 [!code-csharp[GCNotification#1](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#1)]
 [!code-vb[GCNotification#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="a20d3-163">Vea también</span><span class="sxs-lookup"><span data-stu-id="a20d3-163">See also</span></span>

- [<span data-ttu-id="a20d3-164">Recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="a20d3-164">Garbage Collection</span></span>](index.md)
