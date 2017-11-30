---
title: SpinLock
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: synchronization primitives, SpinLock
ms.assetid: f9af93bb-7a0d-4ba5-afe8-74f48b6b6958
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: efe9b3126b3c952ab156f9ca40752ad8d3fddcd1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="spinlock"></a><span data-ttu-id="bb834-102">SpinLock</span><span class="sxs-lookup"><span data-stu-id="bb834-102">SpinLock</span></span>
<span data-ttu-id="bb834-103">El <xref:System.Threading.SpinLock> estructura es una bajo nivel, la exclusión mutua primitiva de sincronización que itera en ciclos mientras espera adquirir un bloqueo.</span><span class="sxs-lookup"><span data-stu-id="bb834-103">The <xref:System.Threading.SpinLock> structure is a low-level, mutual-exclusion synchronization primitive that spins while it waits to acquire a lock.</span></span> <span data-ttu-id="bb834-104">En los equipos con varios núcleos, cuando se prevea que los tiempos de espera deben ser breves y contención es mínima, <xref:System.Threading.SpinLock> puede funcionan mejor que otros tipos de bloqueos.</span><span class="sxs-lookup"><span data-stu-id="bb834-104">On multicore computers, when wait times are expected to be short and when contention is minimal, <xref:System.Threading.SpinLock> can perform better than other kinds of locks.</span></span> <span data-ttu-id="bb834-105">Sin embargo, recomendamos que use <xref:System.Threading.SpinLock> sólo cuando determinar mediante la generación de perfiles que la <xref:System.Threading.Monitor?displayProperty=nameWithType> método o el <xref:System.Threading.Interlocked> métodos reducen significativamente el rendimiento del programa.</span><span class="sxs-lookup"><span data-stu-id="bb834-105">However, we recommend that you use <xref:System.Threading.SpinLock> only when you determine by profiling that the <xref:System.Threading.Monitor?displayProperty=nameWithType> method or the <xref:System.Threading.Interlocked> methods are significantly slowing the performance of your program.</span></span>  
  
 <span data-ttu-id="bb834-106"><xref:System.Threading.SpinLock>incluso si aún no ha adquirido el bloqueo se puede obtener el intervalo de tiempo del subproceso.</span><span class="sxs-lookup"><span data-stu-id="bb834-106"><xref:System.Threading.SpinLock> may yield the time slice of the thread even if it has not yet acquired the lock.</span></span> <span data-ttu-id="bb834-107">Esto consigue para evitar la inversión de prioridad del subproceso y para habilitar el recolector de elementos no utilizados avanzar.</span><span class="sxs-lookup"><span data-stu-id="bb834-107">It does this to avoid thread-priority inversion, and to enable the garbage collector to make progress.</span></span> <span data-ttu-id="bb834-108">Cuando se usa un <xref:System.Threading.SpinLock>, asegúrese de que ningún subproceso mantenga el bloqueo durante más de un intervalo de tiempo muy breve y que ningún subproceso puede bloquearse mientras mantiene el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="bb834-108">When you use a <xref:System.Threading.SpinLock>, ensure that no thread can hold the lock for more than a very brief time span, and that no thread can block while it holds the lock.</span></span>  
  
 <span data-ttu-id="bb834-109">Como SpinLock es un tipo de valor, explícitamente debe pasarlo por referencia si piensa que las dos copias para hacer referencia al mismo bloqueo.</span><span class="sxs-lookup"><span data-stu-id="bb834-109">Because SpinLock is a value type, you must explicitly pass it by reference if you intend the two copies to refer to the same lock.</span></span>  
  
 <span data-ttu-id="bb834-110">Para obtener más información acerca de cómo usar este tipo, consulte <xref:System.Threading.SpinLock?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bb834-110">For more information about how to use this type, see <xref:System.Threading.SpinLock?displayProperty=nameWithType>.</span></span> <span data-ttu-id="bb834-111">Para obtener un ejemplo, vea [Cómo: utilizar SpinLock para la sincronización de bajo nivel](../../../docs/standard/threading/how-to-use-spinlock-for-low-level-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="bb834-111">For an example, see [How to: Use SpinLock for Low-Level Synchronization](../../../docs/standard/threading/how-to-use-spinlock-for-low-level-synchronization.md).</span></span>  
  
 <span data-ttu-id="bb834-112"><xref:System.Threading.SpinLock>admite un *subproceso*-*seguimiento* modo que puede usar durante la fase de desarrollo para ayudar a realizar un seguimiento del subproceso que está reteniendo el bloqueo en un momento determinado.</span><span class="sxs-lookup"><span data-stu-id="bb834-112"><xref:System.Threading.SpinLock> supports a *thread*-*tracking* mode that you can use during the development phase to help track the thread that is holding the lock at a specific time.</span></span> <span data-ttu-id="bb834-113">Modo de seguimiento de subprocesos es muy útil para la depuración, pero se recomienda que apagarlo en la versión de lanzamiento del programa porque puede ralentizar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="bb834-113">Thread-tracking mode is very useful for debugging, but we recommend that you turn it off in the release version of your program because it may slow performance.</span></span> <span data-ttu-id="bb834-114">Para obtener más información, consulte [Cómo: modo de seguimiento habilitar de subprocesos en el bloqueo SpinLock](../../../docs/standard/threading/how-to-enable-thread-tracking-mode-in-spinlock.md).</span><span class="sxs-lookup"><span data-stu-id="bb834-114">For more information, see [How to: Enable Thread-Tracking Mode in SpinLock](../../../docs/standard/threading/how-to-enable-thread-tracking-mode-in-spinlock.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb834-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="bb834-115">See Also</span></span>  
 [<span data-ttu-id="bb834-116">Objetos y características de subprocesos</span><span class="sxs-lookup"><span data-stu-id="bb834-116">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)
