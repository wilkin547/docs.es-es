---
title: CountdownEvent
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
helpviewer_keywords: synchronization primitives, CountdownEvent
ms.assetid: eec3812a-e20f-4ecd-bfef-6921d508b708
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9f953f6477abf1f4e0d6aaf79e67005172ff1144
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="countdownevent"></a><span data-ttu-id="df6c4-102">CountdownEvent</span><span class="sxs-lookup"><span data-stu-id="df6c4-102">CountdownEvent</span></span>
<span data-ttu-id="df6c4-103"><xref:System.Threading.CountdownEvent?displayProperty=nameWithType>es una primitiva de sincronización que desbloquea los subprocesos en espera una vez señala un número determinado de veces.</span><span class="sxs-lookup"><span data-stu-id="df6c4-103"><xref:System.Threading.CountdownEvent?displayProperty=nameWithType> is a synchronization primitive that unblocks its waiting threads after it has been signaled a certain number of times.</span></span> <span data-ttu-id="df6c4-104"><xref:System.Threading.CountdownEvent>está diseñado para escenarios en los que de lo contrario tendría que usar un <xref:System.Threading.ManualResetEvent> o <xref:System.Threading.ManualResetEventSlim> y disminuir manualmente una variable antes de señalar el evento.</span><span class="sxs-lookup"><span data-stu-id="df6c4-104"><xref:System.Threading.CountdownEvent> is designed for scenarios in which you would otherwise have to use a <xref:System.Threading.ManualResetEvent> or <xref:System.Threading.ManualResetEventSlim> and manually decrement a variable before signaling the event.</span></span> <span data-ttu-id="df6c4-105">Por ejemplo, en un escenario de bifurcación/combinación, puede simplemente crear un <xref:System.Threading.CountdownEvent> que tiene un recuento de señal de 5 y, a continuación, iniciar cinco elementos de trabajo en el subproceso de grupo y tienen cada llamada de elemento de trabajo <xref:System.Threading.CountdownEvent.Signal%2A> cuando termina.</span><span class="sxs-lookup"><span data-stu-id="df6c4-105">For example, in a fork/join scenario, you can just create a <xref:System.Threading.CountdownEvent> that has a signal count of 5, and then start five work items on the thread pool and have each work item call <xref:System.Threading.CountdownEvent.Signal%2A> when it completes.</span></span> <span data-ttu-id="df6c4-106">Cada llamada a <xref:System.Threading.CountdownEvent.Signal%2A> disminuye el recuento señalado en 1.</span><span class="sxs-lookup"><span data-stu-id="df6c4-106">Each call to <xref:System.Threading.CountdownEvent.Signal%2A> decrements the signal count by 1.</span></span> <span data-ttu-id="df6c4-107">En el subproceso principal, la llamada a <xref:System.Threading.CountdownEvent.Wait%2A> se bloqueará hasta que el recuento de señal es cero.</span><span class="sxs-lookup"><span data-stu-id="df6c4-107">On the main thread, the call to <xref:System.Threading.CountdownEvent.Wait%2A> will block until the signal count is zero.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="df6c4-108">Para el código que no tienen que interactuar con la API de sincronización de .NET Framework heredada, considere el uso de <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> objetos o <xref:System.Threading.Tasks.Parallel.Invoke%2A> método para obtener un enfoque para expresar el paralelismo del tipo bifurcar-recombinar con mayor facilidad.</span><span class="sxs-lookup"><span data-stu-id="df6c4-108">For code that does not have to interact with legacy .NET Framework synchronization APIs, consider using <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> objects or the <xref:System.Threading.Tasks.Parallel.Invoke%2A> method for an even easier approach to expressing fork-join parallelism.</span></span>  
  
 <span data-ttu-id="df6c4-109"><xref:System.Threading.CountdownEvent>tiene las siguientes características adicionales:</span><span class="sxs-lookup"><span data-stu-id="df6c4-109"><xref:System.Threading.CountdownEvent> has these additional features:</span></span>  
  
-   <span data-ttu-id="df6c4-110">La operación de espera puede cancelarse mediante el uso de tokens de cancelación.</span><span class="sxs-lookup"><span data-stu-id="df6c4-110">The wait operation can be canceled by using cancellation tokens.</span></span>  
  
-   <span data-ttu-id="df6c4-111">Una vez creada la instancia, se puede incrementar su recuento de señal.</span><span class="sxs-lookup"><span data-stu-id="df6c4-111">Its signal count can be incremented after the instance is created.</span></span>  
  
-   <span data-ttu-id="df6c4-112">Pueden reutilizar las instancias después de <xref:System.Threading.CountdownEvent.Wait%2A> ha devuelto mediante una llamada a la <xref:System.Threading.CountdownEvent.Reset%2A> método.</span><span class="sxs-lookup"><span data-stu-id="df6c4-112">Instances can be reused after <xref:System.Threading.CountdownEvent.Wait%2A> has returned by calling the <xref:System.Threading.CountdownEvent.Reset%2A> method.</span></span>  
  
-   <span data-ttu-id="df6c4-113">Las instancias exponen un <xref:System.Threading.WaitHandle> para la integración con otra API de sincronización de .NET Framework como <xref:System.Threading.WaitHandle.WaitAll%2A>.</span><span class="sxs-lookup"><span data-stu-id="df6c4-113">Instances expose a <xref:System.Threading.WaitHandle> for integration with other .NET Framework synchronization APIs such as <xref:System.Threading.WaitHandle.WaitAll%2A>.</span></span>  
  
## <a name="basic-usage"></a><span data-ttu-id="df6c4-114">Uso básico</span><span class="sxs-lookup"><span data-stu-id="df6c4-114">Basic Usage</span></span>  
 <span data-ttu-id="df6c4-115">En el ejemplo siguiente se muestra cómo utilizar un <xref:System.Threading.CountdownEvent> con <xref:System.Threading.ThreadPool> los elementos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="df6c4-115">The following example demonstrates how to use a <xref:System.Threading.CountdownEvent> with <xref:System.Threading.ThreadPool> work items.</span></span>  
  
 [!code-csharp[CDS_CountdownEvent#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_countdownevent/cs/countdownevent.cs#01)]
 [!code-vb[CDS_CountdownEvent#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_countdownevent/vb/module1.vb#01)]  
  
## <a name="countdownevent-with-cancellation"></a><span data-ttu-id="df6c4-116">CountdownEvent con cancelación</span><span class="sxs-lookup"><span data-stu-id="df6c4-116">CountdownEvent With Cancellation</span></span>  
 <span data-ttu-id="df6c4-117">En el ejemplo siguiente se muestra cómo cancelar la operación de espera en <xref:System.Threading.CountdownEvent> utilizando un token de cancelación.</span><span class="sxs-lookup"><span data-stu-id="df6c4-117">The following example shows how to cancel the wait operation on <xref:System.Threading.CountdownEvent> by using a cancellation token.</span></span> <span data-ttu-id="df6c4-118">El patrón básico sigue el modelo de cancelación unificado, que se introdujo en [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="df6c4-118">The basic pattern follows the model for unified cancellation, which is introduced in [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="df6c4-119">Para obtener más información, consulte [cancelación en subprocesos administrados](../../../docs/standard/threading/cancellation-in-managed-threads.md).</span><span class="sxs-lookup"><span data-stu-id="df6c4-119">For more information, see [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md).</span></span>  
  
 [!code-csharp[CDS_CountdownEvent#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_countdownevent/cs/countdownevent.cs#02)]
 [!code-vb[CDS_CountdownEvent#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_countdownevent/vb/canceleventwait.vb#02)]  
  
 <span data-ttu-id="df6c4-120">Tenga en cuenta que la operación de espera no cancela los subprocesos que señalan.</span><span class="sxs-lookup"><span data-stu-id="df6c4-120">Note that the wait operation does not cancel the threads that are signaling it.</span></span> <span data-ttu-id="df6c4-121">Normalmente, la cancelación se aplica a una operación lógica y que puede incluir esperar en el evento, así como todos los elementos de trabajo que está sincronizando la espera.</span><span class="sxs-lookup"><span data-stu-id="df6c4-121">Typically, cancellation is applied to a logical operation, and that can include waiting on the event as well as all the work items that the wait is synchronizing.</span></span> <span data-ttu-id="df6c4-122">En este ejemplo, cada elemento de trabajo se pasa una copia del mismo token de cancelación para que puedan responder a la solicitud de cancelación.</span><span class="sxs-lookup"><span data-stu-id="df6c4-122">In this example, each work item is passed a copy of the same cancellation token so that it can respond to the cancellation request.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df6c4-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="df6c4-123">See Also</span></span>  
 [<span data-ttu-id="df6c4-124">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="df6c4-124">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)
