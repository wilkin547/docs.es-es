---
title: EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- wait handles
- threading [.NET Framework], EventWaitHandle class
- event wait handles [.NET Framework]
ms.assetid: cd94fc34-ac15-427f-b723-a1240a4fab7d
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5c0bcb27ed9c8981665a50c129dfbd824c9612f5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="eventwaithandle-autoresetevent-countdownevent-manualresetevent"></a><span data-ttu-id="5c369-102">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="5c369-102">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>
<span data-ttu-id="5c369-103">Los identificadores de espera de evento permiten a los subprocesos sincronizar actividades mediante señales entre sí y mediante la espera de señales de los demás.</span><span class="sxs-lookup"><span data-stu-id="5c369-103">Event wait handles allow threads to synchronize activities by signaling each other and by waiting on each other's signals.</span></span> <span data-ttu-id="5c369-104">Estos eventos de sincronización se basan en identificadores de espera Win32 y puede dividirse en dos tipos: los que se restablecen automáticamente cuando reciben señales y los que se restablecen manualmente.</span><span class="sxs-lookup"><span data-stu-id="5c369-104">These synchronization events are based on Win32 wait handles and can be divided into two types: those that reset automatically when signaled and those that are reset manually.</span></span>  
  
 <span data-ttu-id="5c369-105">Identificadores de espera de evento son útiles en muchos de los mismos escenarios de sincronización como el <xref:System.Threading.Monitor> clase.</span><span class="sxs-lookup"><span data-stu-id="5c369-105">Event wait handles are useful in many of the same synchronization scenarios as the <xref:System.Threading.Monitor> class.</span></span> <span data-ttu-id="5c369-106">Identificadores de espera de evento son a menudo más fáciles de usar que los <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> y <xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType> métodos y proporcionan un mayor control sobre la señalización.</span><span class="sxs-lookup"><span data-stu-id="5c369-106">Event wait handles are often easier to use than the <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> and <xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType> methods, and they offer more control over signaling.</span></span> <span data-ttu-id="5c369-107">Los identificadores de espera de evento con nombre pueden usarse también para sincronizar actividades entre dominios de aplicación y procesos, mientras que los monitores son locales a un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="5c369-107">Named event wait handles can also be used to synchronize activities across application domains and processes, whereas monitors are local to an application domain.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5c369-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="5c369-108">In This Section</span></span>  
 [<span data-ttu-id="5c369-109">EventWaitHandle</span><span class="sxs-lookup"><span data-stu-id="5c369-109">EventWaitHandle</span></span>](../../../docs/standard/threading/eventwaithandle.md)  
 <span data-ttu-id="5c369-110">La <xref:System.Threading.EventWaitHandle> clase puede representar cualquier automático o manual de restablecimiento de eventos y eventos locales o con el nombre de eventos del sistema.</span><span class="sxs-lookup"><span data-stu-id="5c369-110">The <xref:System.Threading.EventWaitHandle> class can represent either automatic or manual reset events and either local events or named system events.</span></span>  
  
 [<span data-ttu-id="5c369-111">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="5c369-111">AutoResetEvent</span></span>](../../../docs/standard/threading/autoresetevent.md)  
 <span data-ttu-id="5c369-112">El <xref:System.Threading.AutoResetEvent> clase se deriva de <xref:System.Threading.EventWaitHandle> y representa un evento local que se restablece automáticamente.</span><span class="sxs-lookup"><span data-stu-id="5c369-112">The <xref:System.Threading.AutoResetEvent> class derives from <xref:System.Threading.EventWaitHandle> and represents a local event that resets automatically.</span></span>  
  
 [<span data-ttu-id="5c369-113">ManualResetEvent y ManualResetEventSlim</span><span class="sxs-lookup"><span data-stu-id="5c369-113">ManualResetEvent and ManualResetEventSlim</span></span>](../../../docs/standard/threading/manualresetevent-and-manualreseteventslim.md)  
 <span data-ttu-id="5c369-114">El <xref:System.Threading.ManualResetEvent> clase se deriva de <xref:System.Threading.EventWaitHandle> y representa un evento local que se debe restablecer manualmente.</span><span class="sxs-lookup"><span data-stu-id="5c369-114">The <xref:System.Threading.ManualResetEvent> class derives from <xref:System.Threading.EventWaitHandle> and represents a local event that must be reset manually.</span></span> <span data-ttu-id="5c369-115">La <xref:System.Threading.ManualResetEventSlim> clase es una versión ligera y más rápida que puede usarse para los eventos dentro del mismo proceso.</span><span class="sxs-lookup"><span data-stu-id="5c369-115">The <xref:System.Threading.ManualResetEventSlim> class is a lightweight, faster version that can be used for events within the same process.</span></span>  
  
 [<span data-ttu-id="5c369-116">CountdownEvent</span><span class="sxs-lookup"><span data-stu-id="5c369-116">CountdownEvent</span></span>](../../../docs/standard/threading/countdownevent.md)  
 <span data-ttu-id="5c369-117">La <xref:System.Threading.CountdownEvent> clase proporciona una manera simplificada de implementar modelos de paralelismo de bifurcación/combinación en código que usa identificadores de espera.</span><span class="sxs-lookup"><span data-stu-id="5c369-117">The <xref:System.Threading.CountdownEvent> class provides a simplified way to implement fork/join parallelism patterns in code that uses wait handles.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5c369-118">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="5c369-118">Related Sections</span></span>  
 <span data-ttu-id="5c369-119">[Wait Handles](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489) (Clases WaitHandle)</span><span class="sxs-lookup"><span data-stu-id="5c369-119">[Wait Handles](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)</span></span>  
 <span data-ttu-id="5c369-120">El <xref:System.Threading.WaitHandle> clase es la clase base para la <xref:System.Threading.EventWaitHandle>, <xref:System.Threading.Semaphore>, y <xref:System.Threading.Mutex> clases.</span><span class="sxs-lookup"><span data-stu-id="5c369-120">The <xref:System.Threading.WaitHandle> class is the base class for the <xref:System.Threading.EventWaitHandle>, <xref:System.Threading.Semaphore>, and <xref:System.Threading.Mutex> classes.</span></span> <span data-ttu-id="5c369-121">Contiene métodos estáticos como <xref:System.Threading.WaitHandle.SignalAndWait%2A> y <xref:System.Threading.WaitHandle.WaitAll%2A> que son útiles cuando se trabaja con todos los tipos de identificadores de espera.</span><span class="sxs-lookup"><span data-stu-id="5c369-121">It contains static methods such as <xref:System.Threading.WaitHandle.SignalAndWait%2A> and <xref:System.Threading.WaitHandle.WaitAll%2A> that are useful when working with all types of wait handles.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c369-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c369-122">See Also</span></span>  
 <xref:System.Threading.EventWaitHandle>  
 <xref:System.Threading.WaitHandle>  
 <xref:System.Threading.AutoResetEvent>  
 <xref:System.Threading.ManualResetEvent>  
 [<span data-ttu-id="5c369-123">Objetos y características de subprocesos</span><span class="sxs-lookup"><span data-stu-id="5c369-123">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)  
 [<span data-ttu-id="5c369-124">Principios básicos del subprocesamiento administrado</span><span class="sxs-lookup"><span data-stu-id="5c369-124">Managed Threading Basics</span></span>](../../../docs/standard/threading/managed-threading-basics.md)
