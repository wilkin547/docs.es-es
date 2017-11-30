---
title: ManualResetEvent y ManualResetEventSlim
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], ManualResetEvent class
- ManualResetEvent class, about ManualResetEvent class
ms.assetid: 465fdcf9-ba24-4d8d-a43f-d983b7cb0cc6
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f663dd17b063f77e2f9ce6bd4bbd0f8859ba4116
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="manualresetevent-and-manualreseteventslim"></a><span data-ttu-id="b1b89-102">ManualResetEvent y ManualResetEventSlim</span><span class="sxs-lookup"><span data-stu-id="b1b89-102">ManualResetEvent and ManualResetEventSlim</span></span>
<span data-ttu-id="b1b89-103">La <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> clase representa un evento de identificador de espera local que se debe restablecer manualmente después de que se envía una señal.</span><span class="sxs-lookup"><span data-stu-id="b1b89-103">The <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> class represents a local wait handle event that must be reset manually after it is signaled.</span></span> <span data-ttu-id="b1b89-104">Esta clase representa un caso especial de su clase base, <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b1b89-104">This class represents a special case of its base class, <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b1b89-105">Consulte la documentación conceptual [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) para información sobre el uso las características de los eventos de restablecimiento manual.</span><span class="sxs-lookup"><span data-stu-id="b1b89-105">See the [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) conceptual documentation for the use and features of manual reset events.</span></span>  
  
 <span data-ttu-id="b1b89-106">A <xref:System.Threading.ManualResetEvent> objeto permanece señalado hasta que su <xref:System.Threading.EventWaitHandle.Reset%2A?displayProperty=nameWithType> se llama al método.</span><span class="sxs-lookup"><span data-stu-id="b1b89-106">A <xref:System.Threading.ManualResetEvent> object remains signaled until its <xref:System.Threading.EventWaitHandle.Reset%2A?displayProperty=nameWithType> method is called.</span></span> <span data-ttu-id="b1b89-107">Se puede liberar cualquier número de subprocesos en espera, o subprocesos que esperan el evento una vez señalado, mientras se señala el estado del objeto.</span><span class="sxs-lookup"><span data-stu-id="b1b89-107">Any number of waiting threads, or threads that wait on the event after it has been signaled, can be released while the object's state is signaled.</span></span> <span data-ttu-id="b1b89-108"><xref:System.Threading.ManualResetEvent>corresponde a Win32 `CreateEvent` llamar, especificar `true` para el `bManualReset` argumento.</span><span class="sxs-lookup"><span data-stu-id="b1b89-108"><xref:System.Threading.ManualResetEvent> corresponds to a Win32 `CreateEvent` call, specifying `true` for the `bManualReset` argument.</span></span>  
  
 <span data-ttu-id="b1b89-109">En el [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], puede utilizar el <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> de clase para mejorar el rendimiento cuando se espera que los tiempos de espera sean muy cortos y cuando el evento no atraviesa un límite de proceso.</span><span class="sxs-lookup"><span data-stu-id="b1b89-109">In the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], you can use the <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> class for better performance when wait times are expected to be very short, and when the event does not cross a process boundary.</span></span> <span data-ttu-id="b1b89-110"><xref:System.Threading.ManualResetEventSlim>usa ocupado girando durante un período corto mientras se espera que se señaliza el evento.</span><span class="sxs-lookup"><span data-stu-id="b1b89-110"><xref:System.Threading.ManualResetEventSlim> uses busy spinning for a short time while it waits for the event to become signaled.</span></span> <span data-ttu-id="b1b89-111">Cuando los tiempos de espera son breves, los giros pueden ser mucho más económicos que si se espera con identificadores de espera.</span><span class="sxs-lookup"><span data-stu-id="b1b89-111">When wait times are short, spinning can be much less expensive than waiting by using wait handles.</span></span> <span data-ttu-id="b1b89-112">Sin embargo, si no se señaliza el evento en un período determinado de tiempo, <xref:System.Threading.ManualResetEventSlim> recurre a una espera de identificador de evento habitual.</span><span class="sxs-lookup"><span data-stu-id="b1b89-112">However, if the event does not become signaled within a certain period of time, <xref:System.Threading.ManualResetEventSlim> resorts to a regular event handle wait.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1b89-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="b1b89-113">See Also</span></span>  
 [<span data-ttu-id="b1b89-114">Subprocesamiento</span><span class="sxs-lookup"><span data-stu-id="b1b89-114">Threading</span></span>](../../../docs/standard/threading/index.md)  
 [<span data-ttu-id="b1b89-115">Objetos y características de subprocesos</span><span class="sxs-lookup"><span data-stu-id="b1b89-115">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)  
 <span data-ttu-id="b1b89-116">[Wait Handles](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489) (Clases WaitHandle)</span><span class="sxs-lookup"><span data-stu-id="b1b89-116">[Wait Handles](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)</span></span>  
 [<span data-ttu-id="b1b89-117">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="b1b89-117">AutoResetEvent</span></span>](../../../docs/standard/threading/autoresetevent.md)  
 [<span data-ttu-id="b1b89-118">SpinWait</span><span class="sxs-lookup"><span data-stu-id="b1b89-118">SpinWait</span></span>](../../../docs/standard/threading/spinwait.md)  
 <span data-ttu-id="b1b89-119">[Semaphore and SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md) (Clases Semaphore y SemaphoreSlim)</span><span class="sxs-lookup"><span data-stu-id="b1b89-119">[Semaphore and SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md)</span></span>
