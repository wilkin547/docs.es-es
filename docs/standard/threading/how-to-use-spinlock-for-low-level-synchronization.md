---
title: "Cómo: Utilizar SpinLock para la sincronización de bajo nivel"
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
helpviewer_keywords: SpinLock, how to use
ms.assetid: a9ed3e4e-4f29-4207-b730-ed0a51ecbc19
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 30ddc7d340b210aaad4a04ea43e89555d2701f20
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-use-spinlock-for-low-level-synchronization"></a><span data-ttu-id="c8d17-102">Cómo: Utilizar SpinLock para la sincronización de bajo nivel</span><span class="sxs-lookup"><span data-stu-id="c8d17-102">How to: Use SpinLock for Low-Level Synchronization</span></span>
<span data-ttu-id="c8d17-103">En el ejemplo siguiente se muestra cómo utilizar un <xref:System.Threading.SpinLock>.</span><span class="sxs-lookup"><span data-stu-id="c8d17-103">The following example demonstrates how to use a <xref:System.Threading.SpinLock>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8d17-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c8d17-104">Example</span></span>  
 <span data-ttu-id="c8d17-105">En este ejemplo, la sección crítica realiza una cantidad mínima de trabajo, lo que resulta una buena candidata para una <xref:System.Threading.SpinLock>.</span><span class="sxs-lookup"><span data-stu-id="c8d17-105">In this example, the critical section performs a minimal amount of work, which makes it a good candidate for a <xref:System.Threading.SpinLock>.</span></span> <span data-ttu-id="c8d17-106">Al aumentar el trabajo una pequeña cantidad aumenta el rendimiento de la <xref:System.Threading.SpinLock> en comparación con un bloqueo estándar.</span><span class="sxs-lookup"><span data-stu-id="c8d17-106">Increasing the work a small amount increases the performance of the <xref:System.Threading.SpinLock> compared to a standard lock.</span></span> <span data-ttu-id="c8d17-107">Sin embargo, existe un punto en el que un elemento SpinLock es más caro que un bloqueo estándar.</span><span class="sxs-lookup"><span data-stu-id="c8d17-107">However, there is a point at which a SpinLock becomes more expensive than a standard lock.</span></span> <span data-ttu-id="c8d17-108">Puede usar la funcionalidad de generación de perfiles de simultaneidad de las herramientas de generación de perfiles para ver qué tipo de bloqueo proporciona mejor rendimiento en su programa.</span><span class="sxs-lookup"><span data-stu-id="c8d17-108">You can use the concurrency profiling functionality in the profiling tools to see which type of lock provides better performance in your program.</span></span> <span data-ttu-id="c8d17-109">Para más información, consulte [Visualizador de simultaneidad](/visualstudio/profiling/concurrency-visualizer).</span><span class="sxs-lookup"><span data-stu-id="c8d17-109">For more information, see [Concurrency Visualizer](/visualstudio/profiling/concurrency-visualizer).</span></span>  
  
 [!code-csharp[CDS_SpinLock#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#02)]
 [!code-vb[CDS_SpinLock#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_vb.vb#02)]  
  
 <span data-ttu-id="c8d17-110"><xref:System.Threading.SpinLock>puede ser útil cuando un bloqueo en un recurso compartido no va a ser dure mucho.</span><span class="sxs-lookup"><span data-stu-id="c8d17-110"><xref:System.Threading.SpinLock> might be useful when a lock on a shared resource is not going to be held for very long.</span></span> <span data-ttu-id="c8d17-111">En estos casos, puede resultar eficaz en los equipos de varios núcleos que el subproceso bloqueado gire durante algunos ciclos hasta que se libere el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="c8d17-111">In such cases, on multi-core computers it can be efficient for the blocked thread to spin for a few cycles until the lock is released.</span></span> <span data-ttu-id="c8d17-112">Al girar, el subproceso no se bloquea, lo cual es un proceso intensivo de la CPU.</span><span class="sxs-lookup"><span data-stu-id="c8d17-112">By spinning, the thread does not become blocked, which is a CPU-intensive process.</span></span> <span data-ttu-id="c8d17-113"><xref:System.Threading.SpinLock>dejará de girar en ciertas condiciones para evitar el colapso de los procesadores lógicos o la inversión de prioridad en sistemas con Hyper-Threading.</span><span class="sxs-lookup"><span data-stu-id="c8d17-113"><xref:System.Threading.SpinLock> will stop spinning under certain conditions to prevent starvation of logical processors or priority inversion on systems with Hyper-Threading.</span></span>  
  
 <span data-ttu-id="c8d17-114">Este ejemplo se utiliza la <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType> (clase), que requiere la sincronización de usuario para el acceso multiproceso.</span><span class="sxs-lookup"><span data-stu-id="c8d17-114">This example uses the <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType> class, which requires user synchronization for multi-threaded access.</span></span> <span data-ttu-id="c8d17-115">En las aplicaciones que tienen como destino .NET Framework versión 4, otra opción es usar la <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>, que no requiere ningún bloqueo de usuario.</span><span class="sxs-lookup"><span data-stu-id="c8d17-115">In applications that target the .NET Framework version 4, another option is to use the <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>, which does not require any user locks.</span></span>  
  
 <span data-ttu-id="c8d17-116">Tenga en cuenta el uso de `false` (`False` en Visual Basic) en la llamada a <xref:System.Threading.SpinLock.Exit%2A>.</span><span class="sxs-lookup"><span data-stu-id="c8d17-116">Note the use of `false` (`False` in Visual Basic) in the call to <xref:System.Threading.SpinLock.Exit%2A>.</span></span> <span data-ttu-id="c8d17-117">Esto proporciona el mejor rendimiento.</span><span class="sxs-lookup"><span data-stu-id="c8d17-117">This provides the best performance.</span></span> <span data-ttu-id="c8d17-118">Especifique `true` (`True`) en las arquitecturas IA64 para usar la barrera de memoria, que vacía los búferes de escritura para garantizar que ahora el bloqueo esté disponible para que salgan otros subprocesos.</span><span class="sxs-lookup"><span data-stu-id="c8d17-118">Specify `true` (`True`)on IA64 architectures to use the memory fence, which flushes the write buffers to ensure that the lock is now available for other threads to exit.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8d17-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="c8d17-119">See Also</span></span>  
 [<span data-ttu-id="c8d17-120">Objetos y características de subprocesos</span><span class="sxs-lookup"><span data-stu-id="c8d17-120">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)
