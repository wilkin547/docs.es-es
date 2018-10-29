---
title: EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent
ms.date: 09/14/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- wait handles
- threading [.NET Framework], EventWaitHandle class
- event wait handles [.NET Framework]
ms.assetid: cd94fc34-ac15-427f-b723-a1240a4fab7d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: be9c858d7c76fdcc1b3e02485eb0b459f4e7555c
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "48583157"
---
# <a name="eventwaithandle-autoresetevent-countdownevent-manualresetevent"></a><span data-ttu-id="310cb-102">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="310cb-102">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>

<span data-ttu-id="310cb-103">Los identificadores de espera de evento permiten a los subprocesos sincronizar actividades mediante señales entre sí y mediante la espera de señales de los demás.</span><span class="sxs-lookup"><span data-stu-id="310cb-103">Event wait handles allow threads to synchronize activities by signaling each other and by waiting on each other's signals.</span></span> <span data-ttu-id="310cb-104">Estos eventos de sincronización se basan en identificadores de espera del sistema operativo y pueden dividirse en dos tipos: los que se restablecen automáticamente cuando reciben señales y los que se restablecen manualmente.</span><span class="sxs-lookup"><span data-stu-id="310cb-104">These synchronization events are based on operating system wait handles and can be divided into two types: those that reset automatically when signaled and those that are reset manually.</span></span>  
  
<span data-ttu-id="310cb-105">Los identificadores de espera de evento son útiles en muchos de los mismos escenarios de sincronización que la clase <xref:System.Threading.Monitor>.</span><span class="sxs-lookup"><span data-stu-id="310cb-105">Event wait handles are useful in many of the same synchronization scenarios as the <xref:System.Threading.Monitor> class.</span></span> <span data-ttu-id="310cb-106">Los identificadores de espera de eventos suelen ser más fáciles de utilizar que los métodos <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> y <xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType>, y ofrecen mayor control de la señalización.</span><span class="sxs-lookup"><span data-stu-id="310cb-106">Event wait handles are often easier to use than the <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> and <xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType> methods, and they offer more control over signaling.</span></span> <span data-ttu-id="310cb-107">Los identificadores de espera de evento con nombre pueden usarse también para sincronizar actividades entre dominios de aplicación y procesos, mientras que los monitores son locales a un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="310cb-107">Named event wait handles can also be used to synchronize activities across application domains and processes, whereas monitors are local to an application domain.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="310cb-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="310cb-108">In this section</span></span>

 [<span data-ttu-id="310cb-109">EventWaitHandle</span><span class="sxs-lookup"><span data-stu-id="310cb-109">EventWaitHandle</span></span>](eventwaithandle.md)  
 <span data-ttu-id="310cb-110">La clase <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType> puede representar eventos de restablecimiento automático o manual, así como eventos locales o eventos del sistema con nombre.</span><span class="sxs-lookup"><span data-stu-id="310cb-110">The <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType> class can represent either automatic or manual reset events and either local events or named system events.</span></span>  
  
 [<span data-ttu-id="310cb-111">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="310cb-111">AutoResetEvent</span></span>](autoresetevent.md)  
 <span data-ttu-id="310cb-112">La clase <xref:System.Threading.AutoResetEvent?displayProperty=nameWithType> deriva de <xref:System.Threading.EventWaitHandle> y representa un evento local que se restablece automáticamente.</span><span class="sxs-lookup"><span data-stu-id="310cb-112">The <xref:System.Threading.AutoResetEvent?displayProperty=nameWithType> class derives from <xref:System.Threading.EventWaitHandle> and represents a local event that resets automatically.</span></span>  
  
 [<span data-ttu-id="310cb-113">ManualResetEvent y ManualResetEventSlim</span><span class="sxs-lookup"><span data-stu-id="310cb-113">ManualResetEvent and ManualResetEventSlim</span></span>](manualresetevent-and-manualreseteventslim.md)  
 <span data-ttu-id="310cb-114">La clase <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> deriva de <xref:System.Threading.EventWaitHandle> y representa un evento local que se debe restablecer manualmente.</span><span class="sxs-lookup"><span data-stu-id="310cb-114">The <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> class derives from <xref:System.Threading.EventWaitHandle> and represents a local event that must be reset manually.</span></span> <span data-ttu-id="310cb-115">La clase <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> es una versión ligera y más rápida que se puede usar en eventos de un mismo proceso.</span><span class="sxs-lookup"><span data-stu-id="310cb-115">The <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> class is a lightweight, faster version that can be used for events within the same process.</span></span>  
  
 [<span data-ttu-id="310cb-116">CountdownEvent</span><span class="sxs-lookup"><span data-stu-id="310cb-116">CountdownEvent</span></span>](countdownevent.md)  
 <span data-ttu-id="310cb-117">La clase <xref:System.Threading.CountdownEvent?displayProperty=nameWithType> ofrece una forma simplificada de implementar patrones de paralelismo de bifurcación/combinación en código que usa identificadores de espera.</span><span class="sxs-lookup"><span data-stu-id="310cb-117">The <xref:System.Threading.CountdownEvent?displayProperty=nameWithType> class provides a simplified way to implement fork/join parallelism patterns in code that uses wait handles.</span></span>  

## <a name="see-also"></a><span data-ttu-id="310cb-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="310cb-118">See also</span></span>

- <xref:System.Threading.WaitHandle?displayProperty=nameWithType>
- <xref:System.Threading.Barrier?displayProperty=nameWithType>
- [<span data-ttu-id="310cb-119">Objetos y características de subprocesos</span><span class="sxs-lookup"><span data-stu-id="310cb-119">Threading objects and features</span></span>](threading-objects-and-features.md)
- [<span data-ttu-id="310cb-120">Principios básicos del subprocesamiento administrado</span><span class="sxs-lookup"><span data-stu-id="310cb-120">Managed threading basics</span></span>](managed-threading-basics.md)
