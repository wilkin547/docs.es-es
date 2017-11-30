---
title: "Thread.Suspend, recolección de elementos no utilizados y puntos de seguridad"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- suspending threads
- safe points
- threading [.NET Framework], suspending
- threading [.NET Framework], garbage collection
- garbage collection, threads
ms.assetid: e8f58e17-2714-4821-802a-f8eb3b2baa62
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e47674ef8d1b1a7487e42765bcbce4b33cf98769
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="threadsuspend-garbage-collection-and-safe-points"></a><span data-ttu-id="4179d-102">Thread.Suspend, recolección de elementos no utilizados y puntos de seguridad</span><span class="sxs-lookup"><span data-stu-id="4179d-102">Thread.Suspend, Garbage Collection, and Safe Points</span></span>
<span data-ttu-id="4179d-103">Cuando se llama a <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> en un subproceso, el sistema detecta que la suspensión de un subproceso se ha solicitado y permite al subproceso de ejecución hasta que ha alcanzado un punto seguro antes de suspenderlo el subproceso.</span><span class="sxs-lookup"><span data-stu-id="4179d-103">When you call <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> on a thread, the system notes that a thread suspension has been requested and allows the thread to execute until it has reached a safe point before actually suspending the thread.</span></span> <span data-ttu-id="4179d-104">Un punto de seguridad para un subproceso es un punto en su ejecución y en qué elementos no utilizados puede realizarse la colección.</span><span class="sxs-lookup"><span data-stu-id="4179d-104">A safe point for a thread is a point in its execution at which garbage collection can be performed.</span></span>  
  
 <span data-ttu-id="4179d-105">Una vez que se alcanza un punto seguro, el tiempo de ejecución garantiza que el subproceso suspendido no realizará ningún progreso adicional en código administrado.</span><span class="sxs-lookup"><span data-stu-id="4179d-105">Once a safe point is reached, the runtime guarantees that the suspended thread will not make any further progress in managed code.</span></span> <span data-ttu-id="4179d-106">Un subproceso que se ejecuta fuera de código administrado siempre es seguro para la recolección y su ejecución continúa hasta que intenta reanudar la ejecución del código administrado.</span><span class="sxs-lookup"><span data-stu-id="4179d-106">A thread executing outside managed code is always safe for garbage collection, and its execution continues until it attempts to resume execution of managed code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4179d-107">Para realizar una recolección de elementos no utilizados, el tiempo de ejecución debe suspender todos los subprocesos salvo el subproceso que realiza la recolección.</span><span class="sxs-lookup"><span data-stu-id="4179d-107">In order to perform a garbage collection, the runtime must suspend all the threads except the thread performing the collection.</span></span> <span data-ttu-id="4179d-108">Cada subproceso debe llevarse a un punto de seguridad antes de que se pueda suspender.</span><span class="sxs-lookup"><span data-stu-id="4179d-108">Each thread must be brought to a safe point before it can be suspended.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4179d-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="4179d-109">See Also</span></span>  
 <xref:System.Threading.Thread>  
 <xref:System.GC>  
 [<span data-ttu-id="4179d-110">Subprocesamiento</span><span class="sxs-lookup"><span data-stu-id="4179d-110">Threading</span></span>](../../../docs/standard/threading/index.md)  
 [<span data-ttu-id="4179d-111">Administración automática de la memoria</span><span class="sxs-lookup"><span data-stu-id="4179d-111">Automatic Memory Management</span></span>](../../../docs/standard/automatic-memory-management.md)
