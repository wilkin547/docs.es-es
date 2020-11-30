---
title: CountdownEvent
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- synchronization primitives, CountdownEvent
ms.assetid: eec3812a-e20f-4ecd-bfef-6921d508b708
ms.openlocfilehash: 15ff3ee8f4ea18b243f5c3070f1c59df4646a1a4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676483"
---
# <a name="countdownevent"></a><span data-ttu-id="51876-102">CountdownEvent</span><span class="sxs-lookup"><span data-stu-id="51876-102">CountdownEvent</span></span>

<span data-ttu-id="51876-103"><xref:System.Threading.CountdownEvent?displayProperty=nameWithType> es un primitivo de sincronización que desbloquea los subprocesos de espera después de haber sido señalado un número de veces determinado.</span><span class="sxs-lookup"><span data-stu-id="51876-103"><xref:System.Threading.CountdownEvent?displayProperty=nameWithType> is a synchronization primitive that unblocks its waiting threads after it has been signaled a certain number of times.</span></span> <span data-ttu-id="51876-104"><xref:System.Threading.CountdownEvent> está diseñado para escenarios en los que de lo contrario se tendría que usar <xref:System.Threading.ManualResetEvent> o <xref:System.Threading.ManualResetEventSlim> y disminuir manualmente una variable antes de señalar el evento.</span><span class="sxs-lookup"><span data-stu-id="51876-104"><xref:System.Threading.CountdownEvent> is designed for scenarios in which you would otherwise have to use a <xref:System.Threading.ManualResetEvent> or <xref:System.Threading.ManualResetEventSlim> and manually decrement a variable before signaling the event.</span></span> <span data-ttu-id="51876-105">Por ejemplo, en un escenario de bifurcación/combinación, puede crear simplemente una clase <xref:System.Threading.CountdownEvent> que tiene un recuento de señal de 5 y, a continuación, iniciar cinco elementos de trabajo del grupo de subprocesos y realizar cada llamada <xref:System.Threading.CountdownEvent.Signal%2A> del elemento de trabajo cuando se completa.</span><span class="sxs-lookup"><span data-stu-id="51876-105">For example, in a fork/join scenario, you can just create a <xref:System.Threading.CountdownEvent> that has a signal count of 5, and then start five work items on the thread pool and have each work item call <xref:System.Threading.CountdownEvent.Signal%2A> when it completes.</span></span> <span data-ttu-id="51876-106">Cada llamada a <xref:System.Threading.CountdownEvent.Signal%2A> disminuye el recuento de señales en 1.</span><span class="sxs-lookup"><span data-stu-id="51876-106">Each call to <xref:System.Threading.CountdownEvent.Signal%2A> decrements the signal count by 1.</span></span> <span data-ttu-id="51876-107">En el subproceso principal, la llamada a <xref:System.Threading.CountdownEvent.Wait%2A> se bloqueará hasta que el recuento de señales sea cero.</span><span class="sxs-lookup"><span data-stu-id="51876-107">On the main thread, the call to <xref:System.Threading.CountdownEvent.Wait%2A> will block until the signal count is zero.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="51876-108">Para el código que no tiene que interactuar con las API de sincronización de .NET Framework heredadas, considere el uso de objetos <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> o del método <xref:System.Threading.Tasks.Parallel.Invoke%2A> para disponer de un método más sencillo para expresar el paralelismo bifurcación-combinación.</span><span class="sxs-lookup"><span data-stu-id="51876-108">For code that does not have to interact with legacy .NET Framework synchronization APIs, consider using <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> objects or the <xref:System.Threading.Tasks.Parallel.Invoke%2A> method for an even easier approach to expressing fork-join parallelism.</span></span>  
  
 <span data-ttu-id="51876-109"><xref:System.Threading.CountdownEvent> tiene estas características adicionales:</span><span class="sxs-lookup"><span data-stu-id="51876-109"><xref:System.Threading.CountdownEvent> has these additional features:</span></span>  
  
- <span data-ttu-id="51876-110">La operación de espera puede cancelarse mediante el uso de tokens de cancelación.</span><span class="sxs-lookup"><span data-stu-id="51876-110">The wait operation can be canceled by using cancellation tokens.</span></span>  
  
- <span data-ttu-id="51876-111">Una vez creada la instancia, se puede incrementar su recuento de señales.</span><span class="sxs-lookup"><span data-stu-id="51876-111">Its signal count can be incremented after the instance is created.</span></span>  
  
- <span data-ttu-id="51876-112">Las instancias se pueden reutilizar después de que se devuelva <xref:System.Threading.CountdownEvent.Wait%2A> tras una llamada al método <xref:System.Threading.CountdownEvent.Reset%2A>.</span><span class="sxs-lookup"><span data-stu-id="51876-112">Instances can be reused after <xref:System.Threading.CountdownEvent.Wait%2A> has returned by calling the <xref:System.Threading.CountdownEvent.Reset%2A> method.</span></span>  
  
- <span data-ttu-id="51876-113">Las instancias exponen <xref:System.Threading.WaitHandle> para la integración con otras API de sincronización de .NET como <xref:System.Threading.WaitHandle.WaitAll%2A>.</span><span class="sxs-lookup"><span data-stu-id="51876-113">Instances expose a <xref:System.Threading.WaitHandle> for integration with other .NET synchronization APIs, such as <xref:System.Threading.WaitHandle.WaitAll%2A>.</span></span>  
  
## <a name="basic-usage"></a><span data-ttu-id="51876-114">Uso básico</span><span class="sxs-lookup"><span data-stu-id="51876-114">Basic Usage</span></span>  

 <span data-ttu-id="51876-115">En el siguiente ejemplo se muestra cómo se usa <xref:System.Threading.CountdownEvent> con los elementos de trabajo <xref:System.Threading.ThreadPool>.</span><span class="sxs-lookup"><span data-stu-id="51876-115">The following example demonstrates how to use a <xref:System.Threading.CountdownEvent> with <xref:System.Threading.ThreadPool> work items.</span></span>  
  
 [!code-csharp[CDS_CountdownEvent#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_countdownevent/cs/countdownevent.cs#01)]
 [!code-vb[CDS_CountdownEvent#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_countdownevent/vb/module1.vb#01)]  
  
## <a name="countdownevent-with-cancellation"></a><span data-ttu-id="51876-116">CountdownEvent con cancelación</span><span class="sxs-lookup"><span data-stu-id="51876-116">CountdownEvent With Cancellation</span></span>  

 <span data-ttu-id="51876-117">En el ejemplo siguiente se muestra cómo cancelar la operación de espera en <xref:System.Threading.CountdownEvent> utilizando un token de cancelación.</span><span class="sxs-lookup"><span data-stu-id="51876-117">The following example shows how to cancel the wait operation on <xref:System.Threading.CountdownEvent> by using a cancellation token.</span></span> <span data-ttu-id="51876-118">El patrón básico sigue el modelo de cancelación unificada, que se presentó en .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="51876-118">The basic pattern follows the model for unified cancellation, which was introduced in .NET Framework 4.</span></span> <span data-ttu-id="51876-119">Para más información, consulte el tema sobre la [cancelación en subprocesos administrados](cancellation-in-managed-threads.md).</span><span class="sxs-lookup"><span data-stu-id="51876-119">For more information, see [Cancellation in Managed Threads](cancellation-in-managed-threads.md).</span></span>  
  
 [!code-csharp[CDS_CountdownEvent#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_countdownevent/cs/countdownevent.cs#02)]
 [!code-vb[CDS_CountdownEvent#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_countdownevent/vb/canceleventwait.vb#02)]  
  
 <span data-ttu-id="51876-120">Tenga en cuenta que la operación de espera no cancela los subprocesos que la señalan.</span><span class="sxs-lookup"><span data-stu-id="51876-120">Note that the wait operation does not cancel the threads that are signaling it.</span></span> <span data-ttu-id="51876-121">Normalmente, la cancelación se aplica a una operación lógica que puede incluir la espera del evento, así como todos los elementos de trabajo que la espera sincroniza.</span><span class="sxs-lookup"><span data-stu-id="51876-121">Typically, cancellation is applied to a logical operation, and that can include waiting on the event as well as all the work items that the wait is synchronizing.</span></span> <span data-ttu-id="51876-122">En este ejemplo, a cada elemento de trabajo se le pasa una copia del mismo token de cancelación, para que pueda responder a la solicitud de cancelación.</span><span class="sxs-lookup"><span data-stu-id="51876-122">In this example, each work item is passed a copy of the same cancellation token so that it can respond to the cancellation request.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51876-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="51876-123">See also</span></span>

- <xref:System.Threading.Semaphore?displayProperty=nameWithType>
