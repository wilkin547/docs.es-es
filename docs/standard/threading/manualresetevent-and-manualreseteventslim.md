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
ms.openlocfilehash: 864c39aa6673537d66d8402896bce5b4fa92e5ac
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54602448"
---
# <a name="manualresetevent-and-manualreseteventslim"></a><span data-ttu-id="540c6-102">ManualResetEvent y ManualResetEventSlim</span><span class="sxs-lookup"><span data-stu-id="540c6-102">ManualResetEvent and ManualResetEventSlim</span></span>
<span data-ttu-id="540c6-103">La clase <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> representa un evento de identificador de espera local que se debe restablecer manualmente después de que se le señale.</span><span class="sxs-lookup"><span data-stu-id="540c6-103">The <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> class represents a local wait handle event that must be reset manually after it is signaled.</span></span> <span data-ttu-id="540c6-104">Esta clase representa un caso especial de su clase base, <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="540c6-104">This class represents a special case of its base class, <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType>.</span></span> <span data-ttu-id="540c6-105">Consulte la documentación conceptual [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) para información sobre el uso las características de los eventos de restablecimiento manual.</span><span class="sxs-lookup"><span data-stu-id="540c6-105">See the [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) conceptual documentation for the use and features of manual reset events.</span></span>  
  
 <span data-ttu-id="540c6-106">Un objeto <xref:System.Threading.ManualResetEvent> permanece señalado hasta que se llama a su método <xref:System.Threading.EventWaitHandle.Reset%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="540c6-106">A <xref:System.Threading.ManualResetEvent> object remains signaled until its <xref:System.Threading.EventWaitHandle.Reset%2A?displayProperty=nameWithType> method is called.</span></span> <span data-ttu-id="540c6-107">Se puede liberar cualquier número de subprocesos en espera, o subprocesos que esperan el evento una vez señalado, mientras se señala el estado del objeto.</span><span class="sxs-lookup"><span data-stu-id="540c6-107">Any number of waiting threads, or threads that wait on the event after it has been signaled, can be released while the object's state is signaled.</span></span>
  
 <span data-ttu-id="540c6-108">En [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], puede usar la clase <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> para mejorar el rendimiento cuando se espera que los tiempos de espera sean breves y cuando el evento no cruza un límite de proceso.</span><span class="sxs-lookup"><span data-stu-id="540c6-108">In the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], you can use the <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> class for better performance when wait times are expected to be very short, and when the event does not cross a process boundary.</span></span> <span data-ttu-id="540c6-109"><xref:System.Threading.ManualResetEventSlim> usa giros de ocupado durante un breve tiempo mientras se espera que se señale el evento.</span><span class="sxs-lookup"><span data-stu-id="540c6-109"><xref:System.Threading.ManualResetEventSlim> uses busy spinning for a short time while it waits for the event to become signaled.</span></span> <span data-ttu-id="540c6-110">Cuando los tiempos de espera son breves, los giros pueden ser mucho más económicos que si se espera con identificadores de espera.</span><span class="sxs-lookup"><span data-stu-id="540c6-110">When wait times are short, spinning can be much less expensive than waiting by using wait handles.</span></span> <span data-ttu-id="540c6-111">Sin embargo, si no se señala el evento dentro de cierto período de tiempo, <xref:System.Threading.ManualResetEventSlim> recurre a una espera de controlador de evento habitual.</span><span class="sxs-lookup"><span data-stu-id="540c6-111">However, if the event does not become signaled within a certain period of time, <xref:System.Threading.ManualResetEventSlim> resorts to a regular event handle wait.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="540c6-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="540c6-112">See also</span></span>

- <xref:System.Threading.WaitHandle?displayProperty=nameWithType>
- [<span data-ttu-id="540c6-113">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="540c6-113">AutoResetEvent</span></span>](autoresetevent.md)
- [<span data-ttu-id="540c6-114">SpinWait</span><span class="sxs-lookup"><span data-stu-id="540c6-114">SpinWait</span></span>](spinwait.md)
- <span data-ttu-id="540c6-115">[Semaphore and SemaphoreSlim](semaphore-and-semaphoreslim.md) (Clases Semaphore y SemaphoreSlim)</span><span class="sxs-lookup"><span data-stu-id="540c6-115">[Semaphore and SemaphoreSlim](semaphore-and-semaphoreslim.md)</span></span>
- [<span data-ttu-id="540c6-116">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="540c6-116">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>](eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)
- [<span data-ttu-id="540c6-117">Objetos y características de subprocesos</span><span class="sxs-lookup"><span data-stu-id="540c6-117">Threading objects and features</span></span>](threading-objects-and-features.md)
- [<span data-ttu-id="540c6-118">Subprocesamiento</span><span class="sxs-lookup"><span data-stu-id="540c6-118">Threading</span></span>](index.md)
