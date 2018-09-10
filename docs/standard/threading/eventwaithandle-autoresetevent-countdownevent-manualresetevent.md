---
title: EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- wait handles
- threading [.NET Framework], EventWaitHandle class
- event wait handles [.NET Framework]
ms.assetid: cd94fc34-ac15-427f-b723-a1240a4fab7d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2f61e614696e731a85a030e34aa4356137d9000d
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2018
ms.locfileid: "44260154"
---
# <a name="eventwaithandle-autoresetevent-countdownevent-manualresetevent"></a><span data-ttu-id="6c56f-102">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="6c56f-102">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>
<span data-ttu-id="6c56f-103">Los identificadores de espera de evento permiten a los subprocesos sincronizar actividades mediante señales entre sí y mediante la espera de señales de los demás.</span><span class="sxs-lookup"><span data-stu-id="6c56f-103">Event wait handles allow threads to synchronize activities by signaling each other and by waiting on each other's signals.</span></span> <span data-ttu-id="6c56f-104">Estos eventos de sincronización se basan en identificadores de espera Win32 y puede dividirse en dos tipos: los que se restablecen automáticamente cuando reciben señales y los que se restablecen manualmente.</span><span class="sxs-lookup"><span data-stu-id="6c56f-104">These synchronization events are based on Win32 wait handles and can be divided into two types: those that reset automatically when signaled and those that are reset manually.</span></span>  
  
 <span data-ttu-id="6c56f-105">Los identificadores de espera de evento son útiles en muchos de los mismos escenarios de sincronización que la clase <xref:System.Threading.Monitor>.</span><span class="sxs-lookup"><span data-stu-id="6c56f-105">Event wait handles are useful in many of the same synchronization scenarios as the <xref:System.Threading.Monitor> class.</span></span> <span data-ttu-id="6c56f-106">Los identificadores de espera de eventos suelen ser más fáciles de utilizar que los métodos <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> y <xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType>, y ofrecen mayor control de la señalización.</span><span class="sxs-lookup"><span data-stu-id="6c56f-106">Event wait handles are often easier to use than the <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> and <xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType> methods, and they offer more control over signaling.</span></span> <span data-ttu-id="6c56f-107">Los identificadores de espera de evento con nombre pueden usarse también para sincronizar actividades entre dominios de aplicación y procesos, mientras que los monitores son locales a un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="6c56f-107">Named event wait handles can also be used to synchronize activities across application domains and processes, whereas monitors are local to an application domain.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6c56f-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="6c56f-108">In This Section</span></span>  
 [<span data-ttu-id="6c56f-109">EventWaitHandle</span><span class="sxs-lookup"><span data-stu-id="6c56f-109">EventWaitHandle</span></span>](../../../docs/standard/threading/eventwaithandle.md)  
 <span data-ttu-id="6c56f-110">La clase <xref:System.Threading.EventWaitHandle> puede representar eventos de restablecimiento automático o manual, así como eventos locales o eventos del sistema con nombre.</span><span class="sxs-lookup"><span data-stu-id="6c56f-110">The <xref:System.Threading.EventWaitHandle> class can represent either automatic or manual reset events and either local events or named system events.</span></span>  
  
 [<span data-ttu-id="6c56f-111">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="6c56f-111">AutoResetEvent</span></span>](../../../docs/standard/threading/autoresetevent.md)  
 <span data-ttu-id="6c56f-112">La clase <xref:System.Threading.AutoResetEvent> deriva de <xref:System.Threading.EventWaitHandle> y representa un evento local que se restablece automáticamente.</span><span class="sxs-lookup"><span data-stu-id="6c56f-112">The <xref:System.Threading.AutoResetEvent> class derives from <xref:System.Threading.EventWaitHandle> and represents a local event that resets automatically.</span></span>  
  
 [<span data-ttu-id="6c56f-113">ManualResetEvent y ManualResetEventSlim</span><span class="sxs-lookup"><span data-stu-id="6c56f-113">ManualResetEvent and ManualResetEventSlim</span></span>](../../../docs/standard/threading/manualresetevent-and-manualreseteventslim.md)  
 <span data-ttu-id="6c56f-114">La clase <xref:System.Threading.ManualResetEvent> deriva de <xref:System.Threading.EventWaitHandle> y representa un evento local que se debe restablecer manualmente.</span><span class="sxs-lookup"><span data-stu-id="6c56f-114">The <xref:System.Threading.ManualResetEvent> class derives from <xref:System.Threading.EventWaitHandle> and represents a local event that must be reset manually.</span></span> <span data-ttu-id="6c56f-115">La clase <xref:System.Threading.ManualResetEventSlim> es una versión ligera y más rápida que se puede usar en eventos de un mismo proceso.</span><span class="sxs-lookup"><span data-stu-id="6c56f-115">The <xref:System.Threading.ManualResetEventSlim> class is a lightweight, faster version that can be used for events within the same process.</span></span>  
  
 [<span data-ttu-id="6c56f-116">CountdownEvent</span><span class="sxs-lookup"><span data-stu-id="6c56f-116">CountdownEvent</span></span>](../../../docs/standard/threading/countdownevent.md)  
 <span data-ttu-id="6c56f-117">La clase <xref:System.Threading.CountdownEvent> ofrece una forma simplificada de implementar patrones de paralelismo de bifurcación/combinación en código que usa identificadores de espera.</span><span class="sxs-lookup"><span data-stu-id="6c56f-117">The <xref:System.Threading.CountdownEvent> class provides a simplified way to implement fork/join parallelism patterns in code that uses wait handles.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="6c56f-118">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="6c56f-118">Related Sections</span></span>  
 <span data-ttu-id="6c56f-119">[Wait Handles](https://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489) (Clases WaitHandle)</span><span class="sxs-lookup"><span data-stu-id="6c56f-119">[Wait Handles](https://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)</span></span>  
 <span data-ttu-id="6c56f-120">La clase <xref:System.Threading.WaitHandle> es la clase base para las clases <xref:System.Threading.EventWaitHandle>, <xref:System.Threading.Semaphore> y <xref:System.Threading.Mutex>.</span><span class="sxs-lookup"><span data-stu-id="6c56f-120">The <xref:System.Threading.WaitHandle> class is the base class for the <xref:System.Threading.EventWaitHandle>, <xref:System.Threading.Semaphore>, and <xref:System.Threading.Mutex> classes.</span></span> <span data-ttu-id="6c56f-121">Contiene métodos estáticos como <xref:System.Threading.WaitHandle.SignalAndWait%2A> y <xref:System.Threading.WaitHandle.WaitAll%2A> que son útiles cuando se trabaja con todos los tipos de identificadores de espera.</span><span class="sxs-lookup"><span data-stu-id="6c56f-121">It contains static methods such as <xref:System.Threading.WaitHandle.SignalAndWait%2A> and <xref:System.Threading.WaitHandle.WaitAll%2A> that are useful when working with all types of wait handles.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c56f-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="6c56f-122">See also</span></span>

- <xref:System.Threading.EventWaitHandle>  
- <xref:System.Threading.WaitHandle>  
- <xref:System.Threading.AutoResetEvent>  
- <xref:System.Threading.ManualResetEvent>  
- [<span data-ttu-id="6c56f-123">Objetos y características de subprocesos</span><span class="sxs-lookup"><span data-stu-id="6c56f-123">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)  
- [<span data-ttu-id="6c56f-124">Principios básicos del subprocesamiento administrado</span><span class="sxs-lookup"><span data-stu-id="6c56f-124">Managed Threading Basics</span></span>](../../../docs/standard/threading/managed-threading-basics.md)
