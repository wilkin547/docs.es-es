---
title: "Notificaciones de recolección de elementos no utilizados"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords: garbage collection, notifications
ms.assetid: e12d8e74-31e3-4035-a87d-f3e66f0a9b89
caps.latest.revision: "23"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 41a2ed9c5d239f1570955e87bb5b749e29830bc3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="garbage-collection-notifications"></a><span data-ttu-id="2b7f3-102">Notificaciones de recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="2b7f3-102">Garbage Collection Notifications</span></span>
<span data-ttu-id="2b7f3-103">Hay situaciones en que una colección de elementos no utilizados completa (es decir, una recolección de generación 2) por common language runtime puede afectar negativamente al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="2b7f3-103">There are situations in which a full garbage collection (that is, a generation 2 collection) by the common language runtime may adversely affect performance.</span></span> <span data-ttu-id="2b7f3-104">Esto puede ser un problema especialmente con servidores que procesan grandes volúmenes de solicitudes; en este caso, una recolección largo puede provocar un tiempo de espera de solicitud. Para evitar que una recolección completa de la que se producen durante un período crítico, puede recibir una notificación que una colección de elementos no utilizados completa se está aproximando a y, a continuación, tome medidas para redirigir la carga de trabajo a otra instancia del servidor.</span><span class="sxs-lookup"><span data-stu-id="2b7f3-104">This can be an issue particularly with servers that process large volumes of requests; in this case, a long garbage collection can cause a request time-out. To prevent a full collection from occurring during a critical period, you can be notified that a full garbage collection is approaching and then take action to redirect the workload to another server instance.</span></span> <span data-ttu-id="2b7f3-105">También puede inducir una recolección usted mismo, siempre que la instancia del servidor actual no es necesario procesar las solicitudes.</span><span class="sxs-lookup"><span data-stu-id="2b7f3-105">You can also induce a collection yourself, provided that the current server instance does not need to process requests.</span></span>  
  
 <span data-ttu-id="2b7f3-106">El <xref:System.GC.RegisterForFullGCNotification%2A> método registra una notificación que se genera si el tiempo de ejecución detecta que una recolección de elementos no utilizados completa está próxima.</span><span class="sxs-lookup"><span data-stu-id="2b7f3-106">The <xref:System.GC.RegisterForFullGCNotification%2A> method registers for a notification to be raised when the runtime senses that a full garbage collection is approaching.</span></span> <span data-ttu-id="2b7f3-107">Esta notificación consta de dos partes: cuando se está aproximando la colección de elementos no utilizados completa y cuando ha completado la recolección de elementos no utilizados completa.</span><span class="sxs-lookup"><span data-stu-id="2b7f3-107">There are two parts to this notification: when the full garbage collection is approaching and when the full garbage collection has completed.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="2b7f3-108">Colecciones de elementos no utilizados de bloqueo solo genera notificaciones.</span><span class="sxs-lookup"><span data-stu-id="2b7f3-108">Only blocking garbage collections raise notifications.</span></span> <span data-ttu-id="2b7f3-109">Cuando el [ \<gcConcurrent >](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) elemento de configuración está habilitado, las recolecciones de elementos no utilizados de fondo no generará notificaciones.</span><span class="sxs-lookup"><span data-stu-id="2b7f3-109">When the [\<gcConcurrent>](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) configuration element is enabled, background garbage collections will not raise notifications.</span></span>  
  
 <span data-ttu-id="2b7f3-110">Para determinar cuándo se ha producido una notificación, utilice el <xref:System.GC.WaitForFullGCApproach%2A> y <xref:System.GC.WaitForFullGCComplete%2A> métodos.</span><span class="sxs-lookup"><span data-stu-id="2b7f3-110">To determine when a notification has been raised, use the <xref:System.GC.WaitForFullGCApproach%2A> and <xref:System.GC.WaitForFullGCComplete%2A> methods.</span></span> <span data-ttu-id="2b7f3-111">Por lo general, utilice estos métodos en un `while` bucle continuamente obtener un <xref:System.GCNotificationStatus> enumeración que muestra el estado de la notificación.</span><span class="sxs-lookup"><span data-stu-id="2b7f3-111">Typically, you use these methods in a `while` loop to continually obtain a <xref:System.GCNotificationStatus> enumeration that shows the status of the notification.</span></span> <span data-ttu-id="2b7f3-112">Si el valor es <xref:System.GCNotificationStatus.Succeeded>, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2b7f3-112">If that value is <xref:System.GCNotificationStatus.Succeeded>, you can do the following:</span></span>  
  
-   <span data-ttu-id="2b7f3-113">En respuesta a una notificación obtenida con el <xref:System.GC.WaitForFullGCApproach%2A> método, puede redirigir la carga de trabajo y posiblemente inducir una recolección.</span><span class="sxs-lookup"><span data-stu-id="2b7f3-113">In response to a notification obtained with the <xref:System.GC.WaitForFullGCApproach%2A> method, you can redirect the workload and possibly induce a collection yourself.</span></span>  
  
-   <span data-ttu-id="2b7f3-114">En respuesta a una notificación obtenida con el <xref:System.GC.WaitForFullGCComplete%2A> método, hacer que la instancia del servidor actual disponible para procesar las solicitudes de nuevo.</span><span class="sxs-lookup"><span data-stu-id="2b7f3-114">In response to a notification obtained with the <xref:System.GC.WaitForFullGCComplete%2A> method, you can make the current server instance available to process requests again.</span></span> <span data-ttu-id="2b7f3-115">También puede recopilar información.</span><span class="sxs-lookup"><span data-stu-id="2b7f3-115">You can also gather information.</span></span> <span data-ttu-id="2b7f3-116">Por ejemplo, puede usar el <xref:System.GC.CollectionCount%2A> método para registrar el número de colecciones.</span><span class="sxs-lookup"><span data-stu-id="2b7f3-116">For example, you can use the <xref:System.GC.CollectionCount%2A> method to record the number of collections.</span></span>  
  
 <span data-ttu-id="2b7f3-117">El <xref:System.GC.WaitForFullGCApproach%2A> y <xref:System.GC.WaitForFullGCComplete%2A> métodos están diseñados para trabajar conjuntamente.</span><span class="sxs-lookup"><span data-stu-id="2b7f3-117">The <xref:System.GC.WaitForFullGCApproach%2A> and the <xref:System.GC.WaitForFullGCComplete%2A> methods are designed to work together.</span></span> <span data-ttu-id="2b7f3-118">Utiliza un método sin el otro puede producirse resultados indeterminados.</span><span class="sxs-lookup"><span data-stu-id="2b7f3-118">Using one without the other can produce indeterminate results.</span></span>  
  
## <a name="full-garbage-collection"></a><span data-ttu-id="2b7f3-119">Colección de elementos no utilizados completa</span><span class="sxs-lookup"><span data-stu-id="2b7f3-119">Full Garbage Collection</span></span>  
 <span data-ttu-id="2b7f3-120">El tiempo de ejecución produce una recolección completa cuando se cumple alguna de las situaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="2b7f3-120">The runtime causes a full garbage collection when any of the following scenarios are true:</span></span>  
  
-   <span data-ttu-id="2b7f3-121">Se ha promocionado suficiente memoria a la generación 2 para producir la recolección de generación 2 siguiente.</span><span class="sxs-lookup"><span data-stu-id="2b7f3-121">Enough memory has been promoted into generation 2 to cause the next generation 2 collection.</span></span>  
  
-   <span data-ttu-id="2b7f3-122">Se ha promocionado suficiente memoria en el montón de objetos grandes para hacer que la recolección de generación 2 siguiente.</span><span class="sxs-lookup"><span data-stu-id="2b7f3-122">Enough memory has been promoted into the large object heap to cause the next generation 2 collection.</span></span>  
  
-   <span data-ttu-id="2b7f3-123">Una recolección de generación 1 se remite a una recolección de generación 2 debido a otros factores.</span><span class="sxs-lookup"><span data-stu-id="2b7f3-123">A collection of generation 1 is escalated to a collection of generation 2 due to other factors.</span></span>  
  
 <span data-ttu-id="2b7f3-124">Los umbrales que especifique en el <xref:System.GC.RegisterForFullGCNotification%2A> método se aplica a los dos primeros escenarios.</span><span class="sxs-lookup"><span data-stu-id="2b7f3-124">The thresholds you specify in the <xref:System.GC.RegisterForFullGCNotification%2A> method apply to the first two scenarios.</span></span> <span data-ttu-id="2b7f3-125">Sin embargo, en el primer escenario no siempre recibirá la notificación en el tiempo proporcional a los valores de umbral especificados por dos motivos:</span><span class="sxs-lookup"><span data-stu-id="2b7f3-125">However, in the first scenario you will not always receive the notification at the time proportional to the threshold values you specify for two reasons:</span></span>  
  
-   <span data-ttu-id="2b7f3-126">El tiempo de ejecución no comprueba cada asignación de objetos pequeños (por motivos de rendimiento).</span><span class="sxs-lookup"><span data-stu-id="2b7f3-126">The runtime does not check each small object allocation (for performance reasons).</span></span>  
  
-   <span data-ttu-id="2b7f3-127">Solo generación 1 colecciones promueven la memoria a la generación 2.</span><span class="sxs-lookup"><span data-stu-id="2b7f3-127">Only generation 1 collections promote memory into generation 2.</span></span>  
  
 <span data-ttu-id="2b7f3-128">El tercer escenario también contribuye a la incertidumbre de cuando reciba la notificación.</span><span class="sxs-lookup"><span data-stu-id="2b7f3-128">The third scenario also contributes to the uncertainty of when you will receive the notification.</span></span> <span data-ttu-id="2b7f3-129">Aunque esto no es una garantía, siendo una forma útil de mitigar los efectos de una recolección completa inoportuno al redirigir las solicitudes durante este tiempo o induce la colección al que se puede incluir mejor.</span><span class="sxs-lookup"><span data-stu-id="2b7f3-129">Although this is not a guarantee, it does prove to be a useful way to mitigate the effects of an inopportune full garbage collection by redirecting the requests during this time or inducing the collection yourself when it can be better accommodated.</span></span>  
  
## <a name="notification-threshold-parameters"></a><span data-ttu-id="2b7f3-130">Parámetros de umbral de notificación</span><span class="sxs-lookup"><span data-stu-id="2b7f3-130">Notification Threshold Parameters</span></span>  
 <span data-ttu-id="2b7f3-131">El <xref:System.GC.RegisterForFullGCNotification%2A> método tiene dos parámetros para especificar los valores de umbral de los objetos de generación 2 y el montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="2b7f3-131">The <xref:System.GC.RegisterForFullGCNotification%2A> method has two parameters to specify the threshold values of the generation 2 objects and the large object heap.</span></span> <span data-ttu-id="2b7f3-132">Cuando se cumplen esos valores, debe emitirse una notificación de recolección.</span><span class="sxs-lookup"><span data-stu-id="2b7f3-132">When those values are met, a garbage collection notification should be raised.</span></span> <span data-ttu-id="2b7f3-133">En la tabla siguiente se describe estos parámetros.</span><span class="sxs-lookup"><span data-stu-id="2b7f3-133">The following table describes these parameters.</span></span>  
  
|<span data-ttu-id="2b7f3-134">Parámetro</span><span class="sxs-lookup"><span data-stu-id="2b7f3-134">Parameter</span></span>|<span data-ttu-id="2b7f3-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="2b7f3-135">Description</span></span>|  
|---------------|-----------------|  
|`maxGenerationThreshold`|<span data-ttu-id="2b7f3-136">Un número entre 1 y 99 que especifica cuándo debe emitirse la notificación basándose en los objetos que se promocionan de la generación 2.</span><span class="sxs-lookup"><span data-stu-id="2b7f3-136">A number between 1 and 99 that specifies when the notification should be raised based on the objects promoted in generation 2.</span></span>|  
|`largeObjectHeapThreshold`|<span data-ttu-id="2b7f3-137">Un número entre 1 y 99 que especifica cuándo debe emitirse la notificación basándose en los objetos que se asignan en el montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="2b7f3-137">A number between 1 and 99 that specifies when the notification should be raised based on the objects that are allocated in the large object heap.</span></span>|  
  
 <span data-ttu-id="2b7f3-138">Si especifica un valor que es demasiado alto, hay una alta probabilidad de que recibirá una notificación, pero podría ser demasiado un período de espera antes de que el tiempo de ejecución hace que una colección.</span><span class="sxs-lookup"><span data-stu-id="2b7f3-138">If you specify a value that is too high, there is a high probability that you will receive a notification, but it could be too long a period to wait before the runtime causes a collection.</span></span> <span data-ttu-id="2b7f3-139">Si induce una colección, puede reclamar más objetos que se reclame si el tiempo de ejecución hace que la colección.</span><span class="sxs-lookup"><span data-stu-id="2b7f3-139">If you induce a collection yourself, you may reclaim more objects than would be reclaimed if the runtime causes the collection.</span></span>  
  
 <span data-ttu-id="2b7f3-140">Si especifica un valor que es demasiado bajo, el tiempo de ejecución puede provocar la colección antes de que haya tiempo suficiente para recibir una notificación.</span><span class="sxs-lookup"><span data-stu-id="2b7f3-140">If you specify a value that is too low, the runtime may cause the collection before you have had sufficient time to be notified.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b7f3-141">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2b7f3-141">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="2b7f3-142">Descripción</span><span class="sxs-lookup"><span data-stu-id="2b7f3-142">Description</span></span>  
 <span data-ttu-id="2b7f3-143">En el ejemplo siguiente, un grupo de servidores de servicio de las solicitudes Web entrantes.</span><span class="sxs-lookup"><span data-stu-id="2b7f3-143">In the following example, a group of servers service incoming Web requests.</span></span> <span data-ttu-id="2b7f3-144">Para simular la carga de trabajo de procesamiento de solicitudes, matrices de bytes se agregan a un <xref:System.Collections.Generic.List%601> colección.</span><span class="sxs-lookup"><span data-stu-id="2b7f3-144">To simulate the workload of processing requests, byte arrays are added to a <xref:System.Collections.Generic.List%601> collection.</span></span> <span data-ttu-id="2b7f3-145">Cada servidor se registra para una notificación de la colección de elementos no utilizados y, a continuación, inicia un subproceso en el `WaitForFullGCProc` método de usuario para supervisar continuamente el <xref:System.GCNotificationStatus> enumeración devuelto por la <xref:System.GC.WaitForFullGCApproach%2A> y <xref:System.GC.WaitForFullGCComplete%2A> métodos.</span><span class="sxs-lookup"><span data-stu-id="2b7f3-145">Each server registers for a garbage collection notification and then starts a thread on the `WaitForFullGCProc` user method to continuously monitor the <xref:System.GCNotificationStatus> enumeration that is returned by the <xref:System.GC.WaitForFullGCApproach%2A> and the <xref:System.GC.WaitForFullGCComplete%2A> methods.</span></span>  
  
 <span data-ttu-id="2b7f3-146">El <xref:System.GC.WaitForFullGCApproach%2A> y <xref:System.GC.WaitForFullGCComplete%2A> métodos llamar a sus respectivos métodos de usuario de control de eventos cuando se produce una notificación:</span><span class="sxs-lookup"><span data-stu-id="2b7f3-146">The <xref:System.GC.WaitForFullGCApproach%2A> and the <xref:System.GC.WaitForFullGCComplete%2A> methods call their respective event-handling user methods when a notification is raised:</span></span>  
  
-   `OnFullGCApproachNotify`  
  
     <span data-ttu-id="2b7f3-147">Este método llama a la `RedirectRequests` método de usuario, que indica al servidor de puesta en cola de solicitud para suspender el envío de solicitudes al servidor.</span><span class="sxs-lookup"><span data-stu-id="2b7f3-147">This method calls the `RedirectRequests` user method, which instructs the request queuing server to suspend sending requests to the server.</span></span> <span data-ttu-id="2b7f3-148">Esto se simula estableciendo la variable de nivel de clase `bAllocate` a `false` para que no hay más objetos se asignan.</span><span class="sxs-lookup"><span data-stu-id="2b7f3-148">This is simulated by setting the class-level variable `bAllocate` to `false` so that no more objects are allocated.</span></span>  
  
     <span data-ttu-id="2b7f3-149">Después, el `FinishExistingRequests` se denomina método de usuario para finalizar el procesamiento de las solicitudes del servidor pendientes.</span><span class="sxs-lookup"><span data-stu-id="2b7f3-149">Next, the `FinishExistingRequests` user method is called to finish processing the pending server requests.</span></span> <span data-ttu-id="2b7f3-150">Esto se simula desactivando el <xref:System.Collections.Generic.List%601> colección.</span><span class="sxs-lookup"><span data-stu-id="2b7f3-150">This is simulated by clearing the <xref:System.Collections.Generic.List%601> collection.</span></span>  
  
     <span data-ttu-id="2b7f3-151">Por último, se indujo una recolección porque la carga de trabajo está claro.</span><span class="sxs-lookup"><span data-stu-id="2b7f3-151">Finally, a garbage collection is induced because the workload is light.</span></span>  
  
-   `OnFullGCCompleteNotify`  
  
     <span data-ttu-id="2b7f3-152">Este método llama al método de usuario `AcceptRequests` para reanudar la aceptación de solicitudes porque el servidor ya no es susceptible a una colección de elementos no utilizados completa.</span><span class="sxs-lookup"><span data-stu-id="2b7f3-152">This method calls the user method `AcceptRequests` to resume accepting requests because the server is no longer susceptible to a full garbage collection.</span></span> <span data-ttu-id="2b7f3-153">Esta acción se simula estableciendo la `bAllocate` variable `true` para que pueden reanudar objetos que se va a agregar a la <xref:System.Collections.Generic.List%601> colección.</span><span class="sxs-lookup"><span data-stu-id="2b7f3-153">This action is simulated by setting the `bAllocate` variable to `true` so that objects can resume being added to the <xref:System.Collections.Generic.List%601> collection.</span></span>  
  
 <span data-ttu-id="2b7f3-154">El siguiente código contiene la `Main` método del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="2b7f3-154">The following code contains the `Main` method of the example.</span></span>  
  
 [!code-cpp[GCNotification#2](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#2)]
 [!code-csharp[GCNotification#2](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#2)]
 [!code-vb[GCNotification#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#2)]  
  
 <span data-ttu-id="2b7f3-155">El siguiente código contiene la `WaitForFullGCProc` método de usuario, que contiene un bucle while continuo para comprobar las notificaciones de recopilación de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="2b7f3-155">The following code contains the `WaitForFullGCProc` user method, that contains a continuous while loop to check for garbage collection notifications.</span></span>  
  
 [!code-cpp[GCNotification#8](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#8)]
 [!code-csharp[GCNotification#8](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#8)]
 [!code-vb[GCNotification#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#8)]  
  
 <span data-ttu-id="2b7f3-156">El siguiente código contiene la `OnFullGCApproachNotify` método cuando llame desde el</span><span class="sxs-lookup"><span data-stu-id="2b7f3-156">The following code contains the `OnFullGCApproachNotify` method as called from the</span></span>  
  
 <span data-ttu-id="2b7f3-157">Método `WaitForFullGCProc`.</span><span class="sxs-lookup"><span data-stu-id="2b7f3-157">`WaitForFullGCProc` method.</span></span>  
  
 [!code-cpp[GCNotification#5](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#5)]
 [!code-csharp[GCNotification#5](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#5)]
 [!code-vb[GCNotification#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#5)]  
  
 <span data-ttu-id="2b7f3-158">El siguiente código contiene la `OnFullGCApproachComplete` método cuando llame desde el</span><span class="sxs-lookup"><span data-stu-id="2b7f3-158">The following code contains the `OnFullGCApproachComplete` method as called from the</span></span>  
  
 <span data-ttu-id="2b7f3-159">Método `WaitForFullGCProc`.</span><span class="sxs-lookup"><span data-stu-id="2b7f3-159">`WaitForFullGCProc` method.</span></span>  
  
 [!code-cpp[GCNotification#6](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#6)]
 [!code-csharp[GCNotification#6](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#6)]
 [!code-vb[GCNotification#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#6)]  
  
 <span data-ttu-id="2b7f3-160">El código siguiente contiene los métodos de usuario que se llaman desde el `OnFullGCApproachNotify` y `OnFullGCCompleteNotify` métodos.</span><span class="sxs-lookup"><span data-stu-id="2b7f3-160">The following code contains the user methods that are called from the `OnFullGCApproachNotify` and `OnFullGCCompleteNotify` methods.</span></span> <span data-ttu-id="2b7f3-161">Los métodos de usuario redirigirán las solicitudes, finalizan las solicitudes existentes y, a continuación, reanudan las solicitudes después de que se ha producido una colección de elementos no utilizados completa.</span><span class="sxs-lookup"><span data-stu-id="2b7f3-161">The user methods redirect requests, finish existing requests, and then resume requests after a full garbage collection has occurred.</span></span>  
  
 [!code-cpp[GCNotification#9](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#9)]
 [!code-csharp[GCNotification#9](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#9)]
 [!code-vb[GCNotification#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#9)]  
  
 <span data-ttu-id="2b7f3-162">El ejemplo de código completo es como sigue:</span><span class="sxs-lookup"><span data-stu-id="2b7f3-162">The entire code sample is as follows:</span></span>  
  
 [!code-cpp[GCNotification#1](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#1)]
 [!code-csharp[GCNotification#1](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#1)]
 [!code-vb[GCNotification#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="2b7f3-163">Vea también</span><span class="sxs-lookup"><span data-stu-id="2b7f3-163">See Also</span></span>  
 [<span data-ttu-id="2b7f3-164">Recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="2b7f3-164">Garbage Collection</span></span>](../../../docs/standard/garbage-collection/index.md)
