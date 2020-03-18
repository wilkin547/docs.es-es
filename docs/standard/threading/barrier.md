---
title: Barrier
ms.date: 09/14/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- synchronization primitives, Barrier
ms.assetid: 613a8bc7-6a28-4795-bd6c-1abd9050478f
ms.openlocfilehash: 5aa34f7f39f4b9b626bea29372cf984f3cefb361
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73138148"
---
# <a name="barrier"></a><span data-ttu-id="2c9d9-102">Barrier</span><span class="sxs-lookup"><span data-stu-id="2c9d9-102">Barrier</span></span>

<span data-ttu-id="2c9d9-103"><xref:System.Threading.Barrier?displayProperty=nameWithType> es un primitivo de sincronización que permite que varios subprocesos (conocidos como *participantes*) trabajen simultáneamente en un algoritmo por fases.</span><span class="sxs-lookup"><span data-stu-id="2c9d9-103">A <xref:System.Threading.Barrier?displayProperty=nameWithType> is a synchronization primitive that enables multiple threads (known as *participants*) to work concurrently on an algorithm in phases.</span></span> <span data-ttu-id="2c9d9-104">Cada participante se ejecuta hasta que alcanza el punto de barrera en el código.</span><span class="sxs-lookup"><span data-stu-id="2c9d9-104">Each participant executes until it reaches the barrier point in the code.</span></span> <span data-ttu-id="2c9d9-105">La barrera representa el final de una fase de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2c9d9-105">The barrier represents the end of one phase of work.</span></span> <span data-ttu-id="2c9d9-106">Cuando un participante alcanza la barrera, se bloquea hasta que todos los participantes alcancen la misma barrera.</span><span class="sxs-lookup"><span data-stu-id="2c9d9-106">When a participant reaches the barrier, it blocks until all participants have reached the same barrier.</span></span> <span data-ttu-id="2c9d9-107">Cuando todos los participantes alcanzan la barrera, opcionalmente puede invocar una acción posterior a la fase.</span><span class="sxs-lookup"><span data-stu-id="2c9d9-107">After all participants have reached the barrier, you can optionally invoke a post-phase action.</span></span> <span data-ttu-id="2c9d9-108">Esta acción posterior a la fase puede usarse para realizar acciones con un solo subproceso mientras todos los demás subprocesos siguen bloqueados.</span><span class="sxs-lookup"><span data-stu-id="2c9d9-108">This post-phase action can be used to perform actions by a single thread while all other threads are still blocked.</span></span> <span data-ttu-id="2c9d9-109">Una vez ejecutada la acción, se desbloquean todos los participantes.</span><span class="sxs-lookup"><span data-stu-id="2c9d9-109">After the action has been executed, the participants are all unblocked.</span></span>  
  
 <span data-ttu-id="2c9d9-110">El fragmento de código siguiente muestra un modelo de barrera básico.</span><span class="sxs-lookup"><span data-stu-id="2c9d9-110">The following code snippet shows a basic barrier pattern.</span></span>  
  
 [!code-csharp[CDS_Barrier#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_barrier/cs/barrier.cs#02)]
 [!code-vb[CDS_Barrier#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_barrier/vb/barrier_vb.vb#02)]  
  
 <span data-ttu-id="2c9d9-111">Para obtener un ejemplo completo, vea [Sincronizar operaciones simultáneas con una clase Barrier](how-to-synchronize-concurrent-operations-with-a-barrier.md).</span><span class="sxs-lookup"><span data-stu-id="2c9d9-111">For a complete example, see [How to: synchronize concurrent operations with a Barrier](how-to-synchronize-concurrent-operations-with-a-barrier.md).</span></span>  
  
## <a name="adding-and-removing-participants"></a><span data-ttu-id="2c9d9-112">Agregar y quitar participantes</span><span class="sxs-lookup"><span data-stu-id="2c9d9-112">Adding and removing participants</span></span>

 <span data-ttu-id="2c9d9-113">Cuando cree una instancia de <xref:System.Threading.Barrier>, especifique el número de participantes.</span><span class="sxs-lookup"><span data-stu-id="2c9d9-113">When you create a <xref:System.Threading.Barrier> instance, specify the number of participants.</span></span> <span data-ttu-id="2c9d9-114">También puede agregar o quitar participantes dinámicamente en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="2c9d9-114">You can also add or remove participants dynamically at any time.</span></span> <span data-ttu-id="2c9d9-115">Por ejemplo, si un participante resuelve su parte del problema, puede almacenar el resultado, detener la ejecución de ese subproceso y llamar a <xref:System.Threading.Barrier.RemoveParticipant%2A?displayProperty=nameWithType> para reducir el número de participantes en la barrera.</span><span class="sxs-lookup"><span data-stu-id="2c9d9-115">For example, if one participant solves its part of the problem, you can store the result, stop execution on that thread, and call <xref:System.Threading.Barrier.RemoveParticipant%2A?displayProperty=nameWithType> to decrement the number of participants in the barrier.</span></span> <span data-ttu-id="2c9d9-116">Cuando se agrega un participante mediante una llamada a <xref:System.Threading.Barrier.AddParticipant%2A?displayProperty=nameWithType>, el valor devuelto especifica el número de fase actual, que puede ser útil para inicializar el trabajo del nuevo participante.</span><span class="sxs-lookup"><span data-stu-id="2c9d9-116">When you add a participant by calling <xref:System.Threading.Barrier.AddParticipant%2A?displayProperty=nameWithType>, the return value specifies the current phase number, which may be useful in order to initialize the work of the new participant.</span></span>  
  
## <a name="broken-barriers"></a><span data-ttu-id="2c9d9-117">Barreras rotas</span><span class="sxs-lookup"><span data-stu-id="2c9d9-117">Broken barriers</span></span>

 <span data-ttu-id="2c9d9-118">Si un participante no consigue alcanzar la barrera, pueden producirse interbloqueos.</span><span class="sxs-lookup"><span data-stu-id="2c9d9-118">Deadlocks can occur if one participant fails to reach the barrier.</span></span> <span data-ttu-id="2c9d9-119">Para evitar estos interbloqueos, use las sobrecargas del método <xref:System.Threading.Barrier.SignalAndWait%2A?displayProperty=nameWithType> para especificar un período de tiempo de espera y un token de cancelación.</span><span class="sxs-lookup"><span data-stu-id="2c9d9-119">To avoid these deadlocks, use the overloads of the <xref:System.Threading.Barrier.SignalAndWait%2A?displayProperty=nameWithType> method to specify a time-out period and a cancellation token.</span></span> <span data-ttu-id="2c9d9-120">Estas sobrecargas devuelven un valor booleano que cada participante puede comprobar antes de continuar con la fase siguiente.</span><span class="sxs-lookup"><span data-stu-id="2c9d9-120">These overloads return a Boolean value that every participant can check before it continues to the next phase.</span></span>  
  
## <a name="post-phase-exceptions"></a><span data-ttu-id="2c9d9-121">Excepciones posteriores a la fase</span><span class="sxs-lookup"><span data-stu-id="2c9d9-121">Post-phase exceptions</span></span>

 <span data-ttu-id="2c9d9-122">Si el delegado posterior a la fase produce una excepción, se encapsula en un objeto <xref:System.Threading.BarrierPostPhaseException> que después se propaga a todos los participantes.</span><span class="sxs-lookup"><span data-stu-id="2c9d9-122">If the post-phase delegate throws an exception, it is wrapped in a <xref:System.Threading.BarrierPostPhaseException> object which is then propagated to all participants.</span></span>  
  
## <a name="barrier-versus-continuewhenall"></a><span data-ttu-id="2c9d9-123">Barrier frente a ContinueWhenAll</span><span class="sxs-lookup"><span data-stu-id="2c9d9-123">Barrier versus ContinueWhenAll</span></span>

 <span data-ttu-id="2c9d9-124">Las barreras resultan especialmente útiles cuando los subprocesos realizan varias fases en bucles.</span><span class="sxs-lookup"><span data-stu-id="2c9d9-124">Barriers are especially useful when the threads are performing multiple phases in loops.</span></span> <span data-ttu-id="2c9d9-125">Si el código solo requiere una o dos fases de trabajo, piense en usar objetos <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> con cualquier tipo de unión implícita, incluidas:</span><span class="sxs-lookup"><span data-stu-id="2c9d9-125">If your code requires only one or two phases of work, consider whether to use <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> objects with any kind of implicit join, including:</span></span>  
  
- <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A?displayProperty=nameWithType>  
  
- <xref:System.Threading.Tasks.Parallel.Invoke%2A?displayProperty=nameWithType>  
  
- <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>  
  
- <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="2c9d9-126">Para más información, consulte [Chaining Tasks by Using Continuation Tasks](../parallel-programming/chaining-tasks-by-using-continuation-tasks.md) (Encadenar tareas mediante tareas de continuación).</span><span class="sxs-lookup"><span data-stu-id="2c9d9-126">For more information, see [Chaining Tasks by Using Continuation Tasks](../parallel-programming/chaining-tasks-by-using-continuation-tasks.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c9d9-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="2c9d9-127">See also</span></span>

- [<span data-ttu-id="2c9d9-128">Objetos y características de subprocesos</span><span class="sxs-lookup"><span data-stu-id="2c9d9-128">Threading objects and features</span></span>](threading-objects-and-features.md)
- [<span data-ttu-id="2c9d9-129">Sincronizar operaciones simultáneas con una clase Barrier</span><span class="sxs-lookup"><span data-stu-id="2c9d9-129">How to: synchronize concurrent operations with a Barrier</span></span>](how-to-synchronize-concurrent-operations-with-a-barrier.md)
