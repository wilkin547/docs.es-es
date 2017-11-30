---
title: AutoResetEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], AutoResetEvent class
- AutoResetEvent class
ms.assetid: 6d39c48d-6b37-4a9b-8631-f2924cfd9c18
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 69d16e8c6491b4c66ab5a5452762e73172ebbb77
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="autoresetevent"></a><span data-ttu-id="1e67f-102">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="1e67f-102">AutoResetEvent</span></span>
<span data-ttu-id="1e67f-103">La <xref:System.Threading.AutoResetEvent> clase representa un evento de identificador de espera local que se restablece automáticamente cuando se señala, después de liberar un único subproceso en espera.</span><span class="sxs-lookup"><span data-stu-id="1e67f-103">The <xref:System.Threading.AutoResetEvent> class represents a local wait handle event that resets automatically when signaled, after releasing a single waiting thread.</span></span> <span data-ttu-id="1e67f-104">Esta clase representa un caso especial de su clase base, <xref:System.Threading.EventWaitHandle>.</span><span class="sxs-lookup"><span data-stu-id="1e67f-104">This class represents a special case of its base class, <xref:System.Threading.EventWaitHandle>.</span></span> <span data-ttu-id="1e67f-105">Consulte la documentación conceptual [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) para información sobre el uso y las características de los eventos de restablecimiento automático.</span><span class="sxs-lookup"><span data-stu-id="1e67f-105">See the [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) conceptual documentation for the use and features of automatic reset events.</span></span>  
  
 <span data-ttu-id="1e67f-106">Un <xref:System.Threading.AutoResetEvent> objeto se restablece automáticamente a no señalado por el sistema después de que se ha liberado un único subproceso en espera.</span><span class="sxs-lookup"><span data-stu-id="1e67f-106">An <xref:System.Threading.AutoResetEvent> object is automatically reset to non-signaled by the system after a single waiting thread has been released.</span></span> <span data-ttu-id="1e67f-107">Si no hay subprocesos en espera, el objeto del evento sigue teniendo el estado señalizado.</span><span class="sxs-lookup"><span data-stu-id="1e67f-107">If no threads are waiting, the event object's state remains signaled.</span></span> <span data-ttu-id="1e67f-108"><xref:System.Threading.AutoResetEvent>corresponde a Win32 `CreateEvent` llamar, especificar `false` para el `bManualReset` argumento.</span><span class="sxs-lookup"><span data-stu-id="1e67f-108"><xref:System.Threading.AutoResetEvent> corresponds to a Win32 `CreateEvent` call, specifying `false` for the `bManualReset` argument.</span></span>  
  
 <span data-ttu-id="1e67f-109">Para obtener un ejemplo que usa <xref:System.Threading.AutoResetEvent>, consulte [Monitor](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db).</span><span class="sxs-lookup"><span data-stu-id="1e67f-109">For an example that uses <xref:System.Threading.AutoResetEvent>, see [Monitor](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e67f-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e67f-110">See Also</span></span>  
 <xref:System.Threading.ManualResetEvent>  
 <xref:System.Threading.Monitor>  
 [<span data-ttu-id="1e67f-111">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="1e67f-111">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
 [<span data-ttu-id="1e67f-112">Subprocesamiento</span><span class="sxs-lookup"><span data-stu-id="1e67f-112">Threading</span></span>](../../../docs/standard/threading/index.md)  
 [<span data-ttu-id="1e67f-113">Objetos y características de subprocesos</span><span class="sxs-lookup"><span data-stu-id="1e67f-113">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)  
 <span data-ttu-id="1e67f-114">[Wait Handles](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489) (Clases WaitHandle)</span><span class="sxs-lookup"><span data-stu-id="1e67f-114">[Wait Handles](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)</span></span>
