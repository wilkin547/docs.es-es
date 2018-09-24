---
title: AutoResetEvent
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], AutoResetEvent class
- AutoResetEvent class
ms.assetid: 6d39c48d-6b37-4a9b-8631-f2924cfd9c18
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38efbe0ecd88c02752d610de4b1eec8b62eca1f8
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2018
ms.locfileid: "46540822"
---
# <a name="autoresetevent"></a><span data-ttu-id="f0c8f-102">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="f0c8f-102">AutoResetEvent</span></span>
<span data-ttu-id="f0c8f-103">La clase <xref:System.Threading.AutoResetEvent> representa un evento de identificador de espera local que se restablece automáticamente cuando se le señala, después de liberar un subproceso en espera único.</span><span class="sxs-lookup"><span data-stu-id="f0c8f-103">The <xref:System.Threading.AutoResetEvent> class represents a local wait handle event that resets automatically when signaled, after releasing a single waiting thread.</span></span> <span data-ttu-id="f0c8f-104">Esta clase representa un caso especial de su clase base, <xref:System.Threading.EventWaitHandle>.</span><span class="sxs-lookup"><span data-stu-id="f0c8f-104">This class represents a special case of its base class, <xref:System.Threading.EventWaitHandle>.</span></span> <span data-ttu-id="f0c8f-105">Consulte la documentación conceptual [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) para información sobre el uso y las características de los eventos de restablecimiento automático.</span><span class="sxs-lookup"><span data-stu-id="f0c8f-105">See the [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) conceptual documentation for the use and features of automatic reset events.</span></span>  
  
 <span data-ttu-id="f0c8f-106">Un objeto <xref:System.Threading.AutoResetEvent> se restablece automáticamente a no señalado por el sistema una vez que se ha liberado un subproceso en espera único.</span><span class="sxs-lookup"><span data-stu-id="f0c8f-106">An <xref:System.Threading.AutoResetEvent> object is automatically reset to non-signaled by the system after a single waiting thread has been released.</span></span> <span data-ttu-id="f0c8f-107">Si no hay subprocesos en espera, el objeto del evento sigue teniendo el estado señalizado.</span><span class="sxs-lookup"><span data-stu-id="f0c8f-107">If no threads are waiting, the event object's state remains signaled.</span></span>
  
 <span data-ttu-id="f0c8f-108">Para obtener un ejemplo en el que se usa <xref:System.Threading.AutoResetEvent>, vea <xref:System.Threading.Monitor>.</span><span class="sxs-lookup"><span data-stu-id="f0c8f-108">For an example that uses <xref:System.Threading.AutoResetEvent>, see <xref:System.Threading.Monitor>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0c8f-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0c8f-109">See also</span></span>

- <xref:System.Threading.ManualResetEvent>  
- <xref:System.Threading.Monitor>  
- [<span data-ttu-id="f0c8f-110">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="f0c8f-110">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
- [<span data-ttu-id="f0c8f-111">Subprocesamiento</span><span class="sxs-lookup"><span data-stu-id="f0c8f-111">Threading</span></span>](../../../docs/standard/threading/index.md)  
- [<span data-ttu-id="f0c8f-112">Objetos y características de subprocesos</span><span class="sxs-lookup"><span data-stu-id="f0c8f-112">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)  
- <span data-ttu-id="f0c8f-113">[Wait Handles](https://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489) (Clases WaitHandle)</span><span class="sxs-lookup"><span data-stu-id="f0c8f-113">[Wait Handles](https://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)</span></span>
