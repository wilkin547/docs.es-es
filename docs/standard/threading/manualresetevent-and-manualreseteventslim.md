---
title: ManualResetEvent y ManualResetEventSlim
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], ManualResetEvent class
- ManualResetEvent class, about ManualResetEvent class
ms.assetid: 465fdcf9-ba24-4d8d-a43f-d983b7cb0cc6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4949540b9f61e71301647a83a1c05d8b4c941412
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2018
ms.locfileid: "46581277"
---
# <a name="manualresetevent-and-manualreseteventslim"></a><span data-ttu-id="0a455-102">ManualResetEvent y ManualResetEventSlim</span><span class="sxs-lookup"><span data-stu-id="0a455-102">ManualResetEvent and ManualResetEventSlim</span></span>
<span data-ttu-id="0a455-103">La clase <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> representa un evento de identificador de espera local que se debe restablecer manualmente después de que se le señale.</span><span class="sxs-lookup"><span data-stu-id="0a455-103">The <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> class represents a local wait handle event that must be reset manually after it is signaled.</span></span> <span data-ttu-id="0a455-104">Esta clase representa un caso especial de su clase base, <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0a455-104">This class represents a special case of its base class, <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0a455-105">Consulte la documentación conceptual [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) para información sobre el uso las características de los eventos de restablecimiento manual.</span><span class="sxs-lookup"><span data-stu-id="0a455-105">See the [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) conceptual documentation for the use and features of manual reset events.</span></span>  
  
 <span data-ttu-id="0a455-106">Un objeto <xref:System.Threading.ManualResetEvent> permanece señalado hasta que se llama a su método <xref:System.Threading.EventWaitHandle.Reset%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0a455-106">A <xref:System.Threading.ManualResetEvent> object remains signaled until its <xref:System.Threading.EventWaitHandle.Reset%2A?displayProperty=nameWithType> method is called.</span></span> <span data-ttu-id="0a455-107">Se puede liberar cualquier número de subprocesos en espera, o subprocesos que esperan el evento una vez señalado, mientras se señala el estado del objeto.</span><span class="sxs-lookup"><span data-stu-id="0a455-107">Any number of waiting threads, or threads that wait on the event after it has been signaled, can be released while the object's state is signaled.</span></span>
  
 <span data-ttu-id="0a455-108">En [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], puede usar la clase <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> para mejorar el rendimiento cuando se espera que los tiempos de espera sean breves y cuando el evento no cruza un límite de proceso.</span><span class="sxs-lookup"><span data-stu-id="0a455-108">In the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], you can use the <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> class for better performance when wait times are expected to be very short, and when the event does not cross a process boundary.</span></span> <span data-ttu-id="0a455-109"><xref:System.Threading.ManualResetEventSlim> usa giros de ocupado durante un breve tiempo mientras se espera que se señale el evento.</span><span class="sxs-lookup"><span data-stu-id="0a455-109"><xref:System.Threading.ManualResetEventSlim> uses busy spinning for a short time while it waits for the event to become signaled.</span></span> <span data-ttu-id="0a455-110">Cuando los tiempos de espera son breves, los giros pueden ser mucho más económicos que si se espera con identificadores de espera.</span><span class="sxs-lookup"><span data-stu-id="0a455-110">When wait times are short, spinning can be much less expensive than waiting by using wait handles.</span></span> <span data-ttu-id="0a455-111">Sin embargo, si no se señala el evento dentro de cierto período de tiempo, <xref:System.Threading.ManualResetEventSlim> recurre a una espera de controlador de evento habitual.</span><span class="sxs-lookup"><span data-stu-id="0a455-111">However, if the event does not become signaled within a certain period of time, <xref:System.Threading.ManualResetEventSlim> resorts to a regular event handle wait.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a455-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="0a455-112">See also</span></span>

- [<span data-ttu-id="0a455-113">Subprocesamiento</span><span class="sxs-lookup"><span data-stu-id="0a455-113">Threading</span></span>](../../../docs/standard/threading/index.md)  
- [<span data-ttu-id="0a455-114">Objetos y características de subprocesos</span><span class="sxs-lookup"><span data-stu-id="0a455-114">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)  
- <span data-ttu-id="0a455-115">[Wait Handles](https://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489) (Clases WaitHandle)</span><span class="sxs-lookup"><span data-stu-id="0a455-115">[Wait Handles](https://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)</span></span>  
- [<span data-ttu-id="0a455-116">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="0a455-116">AutoResetEvent</span></span>](../../../docs/standard/threading/autoresetevent.md)  
- [<span data-ttu-id="0a455-117">SpinWait</span><span class="sxs-lookup"><span data-stu-id="0a455-117">SpinWait</span></span>](../../../docs/standard/threading/spinwait.md)  
- <span data-ttu-id="0a455-118">[Semaphore and SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md) (Clases Semaphore y SemaphoreSlim)</span><span class="sxs-lookup"><span data-stu-id="0a455-118">[Semaphore and SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md)</span></span>
